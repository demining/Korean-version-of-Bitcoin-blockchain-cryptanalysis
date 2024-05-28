# Bitcoin-PUBKEY HEX 공개 키를 Base58 비트코인 ​​주소로 변환하고 BTC 코인의 잔액을 확인하는 방법

<!-- wp:embed {"url":"https://www.youtube.com/embed/Hsk6QIzb7oY","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Hsk6QIzb7oY
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py">이번 글에서는 이를 위해 bitcoin-checker.py&nbsp;</a><em>파이썬 스크립트를</em>&nbsp;&nbsp;이용하여 대용량 데이터에서 비트코인 ​​코인의 잔고를 확인하는 방법에 대해 알아보도록 하겠습니다&nbsp; .<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/115/c50/ab8/115c50ab8b21651ae63d3cd8d3ecb98d.png" alt="Python 스크립트 bitcoin-checker.py를 확인한 결과" title="Python 스크립트 bitcoin-checker.py를 확인한 결과"/><figcaption class="wp-element-caption">Python 스크립트 bitcoin-checker.py를 확인한 결과</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><br><code>PUBKEY (HEX)</code>&nbsp;우리는 또한 비트코인의 공개 키를 비트코인 ​​주소로&nbsp;&nbsp;변환하는 방법을 배웁니다.&nbsp;&nbsp;<code>(Base58)</code>&nbsp;이 모든 큰 작업은&nbsp;&nbsp;<em>Python 스크립트&nbsp;</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/pubtoaddr.py" target="_blank" rel="noreferrer noopener">pubtoaddr.py 에 의해 수행됩니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>결과적으로 Google Colab 터미널&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab] 에서 Blockchain을 스캔하여 Bitcoin의 잔액을 특히 쉽게 확인할 수 있습니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이전에 비디오 자습서를 녹화했습니다.&nbsp;&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener">"GITHUB에서 작업하기 위한 모든 편의를 만드는 Google Colab의 터미널"</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance" target="_blank" rel="noreferrer noopener">"CryptoDeepTools"</a>&nbsp;리포지토리 로 이동하여&nbsp;&nbsp;<em>Bash 스크립트의 작동</em>&nbsp;&nbsp;방식을 자세히 살펴보겠습니다&nbsp; .&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/getbalance.sh" target="_blank" rel="noreferrer noopener">getbalance.sh</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>명령:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/03CheckBitcoinAddressBalance/

sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip3 install -r requirements.txt

chmod +x getbalance.sh

./getbalance.sh
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d45/57e/1ae/d4557e1ae1a44f4c54e688da3a4882c7.png" alt="파일" title="파일"/><figcaption class="wp-element-caption">파일</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4ff/051/a09/4ff051a0999975eca9beb0b3f349896f.png" alt="Bash 스크립트 코드: getbalance.sh" title="Bash 스크립트 코드: getbalance.sh"/><figcaption class="wp-element-caption">Bash 스크립트 코드: getbalance.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>grep 'PUBKEY = ' signatures.json &gt; pubkeyall.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 유틸리티는&nbsp;&nbsp;<code>grep</code>&nbsp;모든 공개 키를 하나의 공통 파일로 수집합니다.&nbsp;<code>pubkeyall.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sort -u pubkeyall.json &gt; pubkey.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 유틸리티는&nbsp;&nbsp;<code>sort</code>&nbsp;중복 항목을 정렬 및 제거하고 고유한 공개 키를 선택하여 결과를 파일에 저장합니다.&nbsp;<code>pubkey.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>rm pubkeyall.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>유틸리티&nbsp;&nbsp;<code>rm</code>&nbsp;는&nbsp;<code>pubkeyall.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sed -i 's/PUBKEY = //g' pubkey.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>유틸리티는&nbsp;&nbsp;<code>sed</code>&nbsp;접두사를 지웁니다.&nbsp;<code>PUBKEY =</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 pubtoaddr.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>우리는&nbsp;&nbsp;<em>Python 스크립트&nbsp;</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/pubtoaddr.py" target="_blank" rel="noreferrer noopener">pubtoaddr.py를</a><code>pubkey.json</code>&nbsp;실행하고 &nbsp;공개 비트코인 ​​키가 저장된&nbsp;&nbsp;<code>PUBKEY (HEX)</code>&nbsp;파일&nbsp;&nbsp;&nbsp;에서 파일로 변환하여&nbsp;&nbsp;<code>addresses.json</code>&nbsp;결과가 비트코인 ​​주소로 저장되도록 합니다.&nbsp;<code>(Base58)</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>import</strong> hashlib
<strong>import</strong> base58
 
<strong>def</strong> <strong>hash160</strong>(hex_str):
    sha = hashlib.sha256()
    rip = hashlib.new('ripemd160')
    sha.update(hex_str)
    rip.update(sha.digest())
    <strong>return</strong> rip.hexdigest()  # .hexdigest() is hex ASCII
 
 
pub_keys = open('pubkey.json', 'r', encoding='utf-8')
new_file = open('addresses.json', 'a', encoding='utf-8')
compress_pubkey = False
 
<strong>for</strong> pub_key <strong>in</strong> pub_keys:
    pub_key = pub_key.replace('\n', '')
    <strong>if</strong> compress_pubkey:
        <strong>if</strong> (ord(bytearray.fromhex(pub_key&#91;-2:])) % 2 == 0):
            pubkey_compressed = '02'
        <strong>else</strong>:
            pubkey_compressed = '03'
        pubkey_compressed += pub_key&#91;2:66]
        hex_str = bytearray.fromhex(pubkey_compressed)
    <strong>else</strong>:
        hex_str = bytearray.fromhex(pub_key)
 
 
    key_hash = '00' + hash160(hex_str)
 
 
    sha = hashlib.sha256()
    sha.update(bytearray.fromhex(key_hash))
    checksum = sha.digest()
    sha = hashlib.sha256()
    sha.update(checksum)
    checksum = sha.hexdigest()&#91;0:8]
 
#   new_file.write("" + (base58.b58encode(bytes(bytearray.fromhex(key_hash + checksum)))).decode('utf-8'))
    new_file.write((base58.b58encode(bytes(bytearray.fromhex(key_hash + checksum)))).decode('utf-8') + "\n")
pub_keys.close()
new_file.close()</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>파일을 받았으니&nbsp; 이제&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py" target="_blank" rel="noreferrer noopener">bitcoin-checker.py&nbsp;</a><em>Python 스크립트를</em><code>addresses.json</code>&nbsp;&nbsp;사용&nbsp; 하여 비트코인 ​​코인의 잔액을 확인하겠습니다.<em></em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/03CheckBitcoinAddressBalance/bitcoin-checker.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>Python 스크립트</em>&nbsp;실행&nbsp;&nbsp;:&nbsp;<code>python2 bitcoin-checker.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>import</strong> sys
<strong>import</strong> re
<strong>from</strong> time <strong>import</strong> sleep

<strong>try</strong>:    # if is python3
    <strong>from</strong> urllib.request <strong>import</strong> urlopen
<strong>except</strong>: # if is python2
    <strong>from</strong> urllib2 <strong>import</strong> urlopen


<strong>def</strong> <strong>check_balance</strong>(address):

    #Modify the value of the variable below to False if you do not want Bell Sound when the Software finds balance.
    SONG_BELL = True

    #Add time different of 0 if you need more security on the checks
    WARN_WAIT_TIME = 0

    blockchain_tags_json = &#91; 
        'total_received',
        'final_balance',
        ]

    SATOSHIS_PER_BTC = 1e+8

    check_address = address

    parse_address_structure = re.match(r' *(&#91;a-zA-Z1-9]{1,34})', check_address)
    <strong>if</strong> ( parse_address_structure <strong>is</strong> <strong>not</strong> None ):
        check_address = parse_address_structure.group(1)
    <strong>else</strong>:
        print( "\nThis Bitcoin Address is invalid" + check_address )
        exit(1)

    #Read info from Blockchain about the Address
    reading_state=1
    <strong>while</strong> (reading_state):
        <strong>try</strong>:
            htmlfile = urlopen("https://blockchain.info/address/%s?format=json" % check_address, timeout = 10)
            htmltext = htmlfile.read().decode('utf-8')
            reading_state  = 0
        <strong>except</strong>:
            reading_state+=1
            print( "Checking... " + str(reading_state) )
            sleep(60*reading_state)

    print( "\nBitcoin Address = " + check_address )

    blockchain_info_array = &#91;]
    tag = ''
    <strong>try</strong>:
        <strong>for</strong> tag <strong>in</strong> blockchain_tags_json:
            blockchain_info_array.append (
                float( re.search( r'%s":(\d+),' % tag, htmltext ).group(1) ) )
    <strong>except</strong>:
        print( "Error '%s'." % tag );
        exit(1)

    <strong>for</strong> i, btc_tokens <strong>in</strong> enumerate(blockchain_info_array):

        sys.stdout.write ("%s \t= " % blockchain_tags_json&#91;i])
        <strong>if</strong> btc_tokens &gt; 0.0:
            print( "%.8f Bitcoin" % (btc_tokens/SATOSHIS_PER_BTC) );
        <strong>else</strong>:
            print( "0 Bitcoin" );

        <strong>if</strong> (SONG_BELL <strong>and</strong> blockchain_tags_json&#91;i] == 'final_balance' <strong>and</strong> btc_tokens &gt; 0.0): 
            
            #If you have a balance greater than 0 you will hear the bell
            sys.stdout.write ('\a\a\a')
            sys.stdout.flush()

            arq1.write("Bitcoin Address: %s" % check_address)
            arq1.write("\t Balance: %.8f Bitcoin" % (btc_tokens/SATOSHIS_PER_BTC))
            arq1.write("\n")
            arq1.close()
            <strong>if</strong> (WARN_WAIT_TIME &gt; 0):
                sleep(WARN_WAIT_TIME)

#Add the filename of your list of Bitcoin Addresses for check all.
<strong>with</strong> open("addresses.json") <strong>as</strong> file:
    <strong>for</strong> line <strong>in</strong> file:

    	arq1 = open('balance.json', 'a')
        address = str.strip(line)
        <strong>print</strong> ("__________________________________________________\n")
        
        check_balance(address)
<strong>print</strong> "__________________________________________________\n"
arq1.close()</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>결과적으로 결과가 파일에 저장됩니다.&nbsp;<code>balance.json</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/93a/f82/c34/93af82c3468566ef9f495d0732c9731c.png" alt="파일: balance.json" title="파일: balance.json"/><figcaption class="wp-element-caption">파일: balance.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>이제 우리는 다음을 배웠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>비트코인 공개 키를&nbsp;&nbsp;<code>PUBKEY (HEX)</code>&nbsp;비트코인 ​​주소로&nbsp; 변환<code>(Base58)</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비트코인 코인에 대한 모든 비트코인 ​​주소(Base58) 확인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>암호 분석에 적용</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>소스 코드:&nbsp;&nbsp;</strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance" target="_blank" rel="noreferrer noopener"><strong>https://github.com/demining/CryptoDeepTools/tree/main/03CheckBitcoinAddressBalance</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>텔레그램:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>https://t.me/cryptodeeptech</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>동영상 자료:&nbsp;&nbsp;</strong><a href="https://youtu.be/Hsk6QIzb7oY" target="_blank" rel="noreferrer noopener"><strong>https://youtu.be/Hsk6QIzb7oY</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Hsk6QIzb7oY","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Hsk6QIzb7oY
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
