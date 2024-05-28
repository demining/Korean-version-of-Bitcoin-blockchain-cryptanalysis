# ECDSA 짧은 서명을 통한 비트코인 ​​지갑 복구

<!-- wp:embed {"url":"https://www.youtube.com/embed/xBgjWE5tA7Y","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/xBgjWE5tA7Y
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>우리 모두는 ECDSA 서명의 비밀 키 공개가 비트코인 ​​지갑의 완전한 복구로 이어질 수 있다는 것을 알고 있습니다.&nbsp;이전 기사에서 우리는 블록체인 거래의&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener">약점과 취약점을</a>&nbsp;살펴보았지만 비트코인 ​​지갑의 완전한 복구로 이어지는 ECDSA 짧은 서명도 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>이러한 ECDSA 서명이 짧은 이유는 무엇입니까?</h3>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>논의 중인 주제에서 이 질문에 대한 답을 얻을 수 있습니다.&nbsp;<a href="https://bitcoin.stackexchange.com/questions/38513/the-shortest-ecdsa-signature" target="_blank" rel="noreferrer noopener"><strong>"가장 짧은 ECDSA 서명" [가장 짧은 ECDSA 서명]</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>지난 기사:&nbsp;<a href="https://cryptodeep.ru/reduce-private-key/" target="_blank" rel="noreferrer noopener"><em>"ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"에서</em></a>&nbsp;우리 는 다소 흥미로운 공개 키를 생성하는&nbsp;<em>Python</em>&nbsp;스크립트&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">maxwell.py를</a>&nbsp;만들었습니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/69a/7a0/b32/69a7a0b324ac3b1f3e0dc27f0f4130bf.png" alt="ECDSA 짧은 서명을 통한 비트코인 ​​지갑 복구"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63 , 0xc0c686408d517dfd67c2367651380d00d126e4229631fd03f8ff35eef1a61e3c)</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>우리는 서명의 값을 알고 있으므로&nbsp;<code>"R"</code>이것은 개인 키에서 공개 키입니다.<code>(Nonce)</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://btc.exan.tech/tx/11e6b169701a9047f3ddbb9bc4d4ab1a148c430ba4a5929764e97e76031f4ee3" target="_blank" rel="noreferrer noopener"><strong>블록 체인</strong></a>&nbsp;거래를 살펴보십시오.<a href="https://btc.exan.tech/tx/11e6b169701a9047f3ddbb9bc4d4ab1a148c430ba4a5929764e97e76031f4ee3" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>RawTX:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001afddd5c9f05bd937b24a761606581c0cddd6696e05a25871279f75b7f6cf891f250000005f3c303902153b78ce563f89a0ed9414f5aa28ad0d96d6795f9c6302200a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8012103151033d660dc0ef657f379065cab49932ce4fb626d92e50d4194e026328af853ffffffff010000000000000000016a00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이 트랜잭션의 크기는 다음과 같습니다.<code>156 байт</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>ECDSA 약식 서명을 통해 비트코인 ​​지갑을 어떻게 복원할 수 있습니까?</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>비트코인 블록체인의 암호화 분석에서 우리는 자체&nbsp;<em>B</em>&nbsp;h 스크립트를 사용합니다.<code>btcrecover.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/299/fa2/616/299fa2616cbdb8e6df9304862f441ba2.gif" alt="비트코인 지갑 복구 프로세스" title="비트코인 지갑 복구 프로세스"/><figcaption class="wp-element-caption">비트코인 지갑 복구 프로세스</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>Bash 스크립트: btcrecover.sh</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt

chmod +x btcrecover.sh


 ./btcrecover.sh 12yysAMhagEm67QCX85p3WQnTUrqcvYVuk


 ./btcrecover.sh 15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>결과:</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>| privkey : addr |</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a>&nbsp;열고&nbsp;&nbsp;&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ac8d0abda1d32aaabff56cb72bc39a998a98779632d7fee83ff452a86a849bc1:12yysAMhagEm67QCX85p3WQnTUrqcvYVuk
b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f:15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>실험 부분으로 이동하여 비트코인 ​​지갑 복원을 위한 모든 스크립트를 더 자세히 분석해 보겠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]을</strong></a>&nbsp;엽니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/09BitcoinWalletRecovery" target="_blank" rel="noreferrer noopener"><strong>"09BitcoinWalletRecovery"</strong></a>&nbsp;저장소를 사용합시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/09BitcoinWalletRecovery/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/4e3/7b8/f6c/4e37b8f6cefc8f8d0553f541a5eb8b98.png" alt="ECDSA 짧은 서명을 통한 비트코인 ​​지갑 복구"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>필요한 모든 모듈을 설치합니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>bitcoin
ecdsa
utils
base58</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/d5f/25e/5b1/d5f25e5b1b966ff43a48aaf0955ecfcd.png" alt="ECDSA 짧은 서명을 통한 비트코인 ​​지갑 복구"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/09BitcoinWalletRecovery/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py</a>&nbsp;스크립트를 사용하여&nbsp;<code>RawTX</code>서명 [R, S, Z]&nbsp;에서 가져옵니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001afddd5c9f05bd937b24a761606581c0cddd6696e05a25871279f75b7f6cf891f250000005f3c303902153b78ce563f89a0ed9414f5aa28ad0d96d6795f9c6302200a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8012103151033d660dc0ef657f379065cab49932ce4fb626d92e50d4194e026328af853ffffffff010000000000000000016a00000000 &gt; signatures.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>결과는 다음 파일에 저장됩니다: signatures.txt</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>파일을 열어봅시다:<code>PublicKeys.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat signatures.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/cd3/2b9/9e3/cd32b99e37cc600ddd3c35965e2a0288.png" alt="ECDSA 짧은 서명을 통한 비트코인 ​​지갑 복구"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://habr.com/ru/post/682220/">지난 기사</a>&nbsp;에서 알 수 있듯이&nbsp;<em>서명을</em>&nbsp;생성하는&nbsp;<em><u>비밀 키를</u></em>&nbsp;알고 있습니다.<em></em>&nbsp;<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/9df/b17/63d/9dfb1763d978473245abb6cab03e0e48.png" alt="ECDSA 짧은 서명을 통한 비트코인 ​​지갑 복구"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>우리의 경우&nbsp;<em><u>비밀 키는 다음과 같습니다</u></em>&nbsp;<code>(Nonce)</code>&nbsp;.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0 --&gt; 0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63, 0x3f3979bf72ae8202983dc989aec7f2ff2ed91bdd69ce02fc0700ca100e59ddf3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>서명:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0
R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이제 우리는 ]의 값을 알고 있으므로&nbsp;<code>[K, R, S, Z</code>공식을 사용하여 개인 키를 얻고 비트코인 ​​지갑을 복원할 수 있습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/2db/a14/ab5/2dba14ab5cb76228181c68a9403038a7.svg" alt="Privkey = ((((S * K) - Z) * ​​modinv(R,N)) % N)"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>개인 키를 얻기 위해 Python</em>&nbsp;스크립트:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/09BitcoinWalletRecovery/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py를</a>&nbsp;사용합니다.<a href="https://github.com/demining/CryptoDeepTools/blob/main/09BitcoinWalletRecovery/calculate.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0
R = 0x00000000000000000000003b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63
S = 0x0a963d693c008f0f8016cfc7861c7f5d8c4e11e11725f8be747bb77d8755f1b8
Z = 0x521a65420faa5386d91b8afcfab68defa02283240b25aeee958b20b36ddcb6de


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>Python 스크립트(calculate.py)를 실행해 봅시다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/502/645/324/502645324ec5666803f791ea3cc3a109.png" alt="PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f" title="PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f"/><figcaption class="wp-element-caption">PrivKey = b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a>&nbsp;열고&nbsp;&nbsp;&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 15HvLBX9auG2bJdLCTxSvjvWvdgsW7BvAT
WIF:  L3LxjEnwKQMFYNYmCGzM1TqnwxRDi8UyRzQpVfmDvk96fYN44oFG
HEX:  b6c1238de89e9defea3ea0712e08726e338928ac657c3409ebb93d9a0873797f</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/82b/5e1/157/82b5e115789ac3949bbe28bb975a2826.png" alt="ECDSA 짧은 서명을 통한 비트코인 ​​지갑 복구"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>개인 키를 찾았습니다!</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>비트코인 지갑 복구!</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/50f/e20/dbc/50fe20dbc6d9d6f4a4dbf43c6eaba268.png" alt="ECDSA 짧은 서명을 통한 비트코인 ​​지갑 복구"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>Короткие подписи ECDSA</code>는&nbsp;<em>코인 손실의 잠재적 위협</em>&nbsp;<code>BTC</code>&nbsp;이므로&nbsp;<em>모든 사람이 항상 소프트웨어를 업데이트하고 검증된 장치만 사용할 것을 강력히 권장합니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>&nbsp;이 비디오는 암호 화폐의&nbsp;&nbsp;&nbsp;약한 서명에 대한&nbsp;&nbsp;&nbsp;타원 곡선의 데이터 및 암호화의 재정적 보안을 보장하기 위해&nbsp;&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>&nbsp;포털용 으로 제작되었습니다.&nbsp;<code>secp256k1</code><code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/09BitcoinWalletRecovery" target="_blank" rel="noreferrer noopener"><strong>원천</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech"><strong>텔레그램</strong></a><strong>&nbsp;:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>https://t.me/cryptodeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/xBgjWE5tA7Y" target="_blank" rel="noreferrer noopener">영상 자료: https://youtu.be/xBgjWE5tA7Y</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/shortest-ecdsa-signature" target="_blank" rel="noreferrer noopener"><strong>출처: https://cryptodeep.ru/shortest-ecdsa-signature</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2408} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/013-1024x576.png" alt="Восстановление Биткоин Кошелька через короткие подписи ECDSA" class="wp-image-2408"/></figure>
<!-- /wp:image -->
