# Endomorphism 으로 secp256k1 속도 향상

<!-- wp:embed {"url":"https://www.youtube.com/embed/DH6FyNY-Gh0","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/DH6FyNY-Gh0
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><code>secp256k1</code>&nbsp;이 기사에서는 비트코인 ​​암호화폐에 대한 검증을 최적화하는 데 도움이 되는 엔도모피즘&nbsp;&nbsp;가속 기능을&nbsp; 살펴보지만&nbsp;<code>ECDSA</code>&nbsp;먼저 약간의 역사를 살펴보겠습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>12 января 2009 года</code>&nbsp;<a href="https://ru.wikipedia.org/wiki/%D0%A1%D0%B0%D1%82%D0%BE%D1%81%D0%B8_%D0%9D%D0%B0%D0%BA%D0%B0%D0%BC%D0%BE%D1%82%D0%BE" target="_blank" rel="noreferrer noopener">Satoshi Nakamoto는</a>&nbsp;&nbsp;초기 비트코인 ​​거래에서&nbsp;&nbsp;<a href="https://ru.wikipedia.org/wiki/%D0%93%D0%B0%D1%80%D0%BE%D0%BB%D1%8C%D0%B4_%D0%A2%D0%BE%D0%BC%D0%B0%D1%81_%D0%A4%D0%B8%D0%BD%D0%BD%D0%B8_II" target="_blank" rel="noreferrer noopener">Hal Finney를</a>&nbsp;<code>10 BTC</code>&nbsp;보냈습니다 .</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>Satoshi Nakamoto가 Bitcoins의 첫 수령인으로 Hal을 선택한 사실은 놀라운 일이 아닙니다.&nbsp;<a href="https://ru.wikipedia.org/wiki/PGP" target="_blank" rel="noreferrer noopener">Satoshi는 PGP</a>&nbsp;암호화 시스템 을 개발하여 세계에서 가장 뛰어난 프로그래머이자 암호 작성자 중 한 명으로 자리매김한 Hal을 매우 존경했습니다&nbsp;&nbsp;.&nbsp;Hal은 또한 Satoshi가 비트코인 ​​개발에 사용할 재사용 가능한 작업 증명을 위한 중요한 토대를 마련했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>세계 최고의 암호학자 중 한 명인 Hal은 비트코인을 우연히 발견한 직후 엄청난 돌파구라는 것을 깨달았습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그는 또한&nbsp;&nbsp;<code>2008 году</code>&nbsp;Bitcoin을&nbsp;&nbsp;<strong><em>"매우 유망한 아이디어"</em></strong>&nbsp;라고 불렀습니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w780/getpro/habr/upload_files/e90/c19/48e/e90c1948ecdd67427ca6fd6eb0fe7b24.jpg" alt="endomorphism으로 secp256k1 속도 향상"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>에서 게시한&nbsp;&nbsp;이&nbsp;&nbsp;<em>트윗은</em>&nbsp;&nbsp;많은 사람들이 비트코인이 무엇인지 알기도 전에&nbsp;<code>11 января 2009 года</code>Hal이&nbsp;&nbsp;<em><u>비트코인의 성공을 예측했다는 충분한 증거입니다.</u></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>2년이 지났고&nbsp;&nbsp;<code>2011 году</code>&nbsp;개발자이자 비트코인 ​​애호가인 Hal Finney는&nbsp;&nbsp;<a href="https://bitcointalk.org/index.php?topic=3238.msg45565#msg45565" target="_blank" rel="noreferrer noopener"><strong>Bitcointalk 포럼에서&nbsp;</strong></a><em><u>secp256k1 엔도모피즘 기능을 사용하여 ECDSA 서명 확인 속도를 높일 수 있다고</u></em>&nbsp;썼습니다&nbsp; .<em><u></u></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>LAMBDA 및 BETA는 secp256k1 곡선의 값입니다.</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/9a4/ce6/3af/9a4ce63afa2c39ded280bea637d2ba70.svg" alt="λ^3(mod n) = 1  "/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/df4/4d7/5ce/df44d75ceb126764e40606ad336f26e3.svg" alt="b ^ 3(mod p) = 1"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>secp256k1은 x 및 y 좌표에 다음 소수를 사용합니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>p = 0xffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffffc2f</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>곡선의 순서:</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>n = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>첫 번째 단계는 곡선의 모든 지점에 대해 다음과 같이&nbsp;&nbsp;<code>LAMBDA</code>&nbsp;값&nbsp;&nbsp;을 계산하는 것입니다&nbsp;&nbsp;.<code>BETA</code><code>Q = (x, y)</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>LAMBDA * Q = (BETA*х mod р, у)</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이것은 소위 효율적으로 계산 가능한 엔도&nbsp;&nbsp;<em><u>모피즘(Effectively Computable Endomorphism)</u></em>&nbsp;이며, 한 번의 곱셈을 수행하여&nbsp;&nbsp;곡선의 모든 지점에&nbsp;&nbsp;<code>secp256k1</code>&nbsp;이 특수 값을&nbsp; 매우 빠르게 곱할 수 있음을 의미합니다&nbsp;.<code>LAMBDA</code><code>mod p</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>Hal Finney가 발견하고 출판한 의미:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>LAMBDA = 0x5363ad4cc05c30e0a5261c028812645a122e22ea20816678df02967c1b23bd72

BETA = 0x7ae96a2b657c07106e64479eac3434e99cf0497512f58995c1396c28719501ee</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>우리가 빠르게 곱할 수 있다는 점을 감안할 때&nbsp;&nbsp;<code>LAMBDA,</code>&nbsp;요령은 를 계산하는 것입니다&nbsp;&nbsp;<code>kQ</code><em>.&nbsp;</em>먼저 계산을 사용합시다&nbsp;.&nbsp;그런 다음&nbsp; 두 부분&nbsp;&nbsp;및&nbsp;&nbsp;&nbsp;로 분할해야 합니다&nbsp;&nbsp;. 각 부분은 너비의 약 절반입니다&nbsp;&nbsp;.<em>&nbsp;</em><code>Q' = lambdaQ</code><code>k</code><code>k1</code><code>k2</code><code>n</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>k = k1 + k2*LAMBDA  mod  n</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>그 다음에</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>k*Q = (k1 + k2*LAMBDA)*Q = k1*Q + k2*LAMBDA*Q = k1*Q + k2*Q'</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 마지막 표현식은 이중 곱셈 알고리즘을 사용하여 효율적으로 계산할 수 있으며&nbsp;&nbsp;&nbsp;길이가 절반이므로 속도가 향상됩니다&nbsp;<code>k1</code>&nbsp;.&nbsp;<code>k2</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>누락된 부분은&nbsp;&nbsp;&nbsp;과&nbsp;&nbsp;<code>k</code>&nbsp;로&nbsp; 나뉩니다&nbsp;.&nbsp;<em><u>이를 위해 다음 4가지 값이</u></em>&nbsp;사용됩니다&nbsp;&nbsp;.<code>k1</code><code>k2</code><em><u></u></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>а1 = 0x3086d221a7d46bcde86c90e49284eb15
b1 = -0xe4437ed6010e88286f547fa90abfe4c3
а2 = 0x114ca50f7a8e2f3f657c1108d9d44cfd8
b2 = 0x3086d221a7d46bcde86c90e49284eb15</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>(a1 = b2이면 괜찮습니다)</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>k를 나누기 위해 다음과 같이 사용합니다.</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>c1 = RoundToNearestInteger(b2*k/n)
c2 = RoundToNearestInteger(-b1*k/n)

k1 = k - c1*a1 - c2*a2
k2 = -c1*b1 - c2*b2</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>20%-е</code>&nbsp;더블링 횟수가 절반으로 줄어&nbsp;대략적으로 속도가 빨라집니다&nbsp; .이것은 여러 지점에서 그룹화할 수 있는 많은 알고리즘에 두 배의 공개 키로 가질 수 있는 성능을 제공합니다.<br><em>동등한 최적화 수준에서 이러한 속도 향상은&nbsp;&nbsp;</em><code>secp256k1</code><em>&nbsp;일반적으로 사용되는 모든 곡선 중에서 테스트하기에 가장 빠른 곡선입니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3>우리는 개발자이자 연구원인 Jean Luc Pons의 저장소에 대한 보다 자세한 연구에서 내형성의 존재에 대해 배웠습니다.</h3>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/53a/a41/46a/53aa4146a4d43ac9279e96b8e403216d.png" alt="endomorphism으로 secp256k1 속도 향상"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">우리는 이전에 Jean Luc Pons가</a>&nbsp;&nbsp;Kangaroo&nbsp;&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">를</a>&nbsp;구축하기 위해 소스 코드를 사용했던&nbsp;&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"><strong><em>"Pollard의 Kangaroo는 알려진 범위에서 secp256k1 PRIVATE KEY + NONCES의 이산 로그에 대한 솔루션을 찾습니다"라는</em></strong></a><strong><em>&nbsp;&nbsp;기사&nbsp;</em></strong>&nbsp;를 게시했습니다&nbsp;&nbsp;.<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>가속 메커니즘 기반 Jean Luc Pons 지적 VanitySearch</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L255" target="_blank" rel="noreferrer noopener"><strong>main.cpp</strong></a>&nbsp;열기&nbsp;<a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L255" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/605/fca/301/605fca301a5eef1f215250562ff4e039.png" alt="메인.cpp" title="메인.cpp"/><figcaption class="wp-element-caption">메인.cpp</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L255" target="_blank" rel="noreferrer noopener">255</a>&nbsp;행 &nbsp;과&nbsp;&nbsp;<a href="https://github.com/JeanLucPons/VanitySearch/blob/c8d48ce5f03f5357c0e87cbdb3e1e93cd50af88b/main.cpp#L256" target="_blank" rel="noreferrer noopener">256</a>&nbsp;행에서&nbsp; Jean Luc Pons가&nbsp;<em><u>엔도모피즘을</u></em><code>secp256k1</code>&nbsp;&nbsp;사용하여&nbsp;&nbsp;&nbsp;타원 곡선 가속 함수를 적용한 것을 볼 수 있습니다&nbsp;&nbsp;.<em><u></u></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>  lambda.SetBase16("5363ad4cc05c30e0a5261c028812645a122e22ea20816678df02967c1b23bd72");
  lambda2.SetBase16("ac9c52b33fa3cf1f5ad9e3fd77ed9ba4a880b9fc8ec739c2e0cfc810b51283ce");</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>실험적인 부분으로 넘어 갑시다.</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/7df/255/c08/7df255c08ea1fb0e498b76bf4a431873.png" alt="endomorphism으로 secp256k1 속도 향상"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">기사</a>&nbsp;에서 기억하듯이&nbsp; , 우리는&nbsp;<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong>Bitcoin Rich List</strong></a>&nbsp;의&nbsp;&nbsp;&nbsp;비트코인 ​​주소&nbsp;&nbsp;<a href="https://www.blockchain.com/ru/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</strong></a>&nbsp;의 트랜잭션을 &nbsp;총&nbsp;&nbsp;<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong>1,000만 달러</strong></a>&nbsp;이상 분석했습니다 . 이 비트코인 ​​주소를 예로 들어 보겠습니다.<a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong></strong></a><a href="https://bitinfocharts.com/top-100-richest-bitcoin-addresses.html" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>터미널에서 Google Colab&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]을</strong></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/07EndomorphismSecp256k1" target="_blank" rel="noreferrer noopener">&nbsp;열고 "07EndomorphismSecp256k1"</a>&nbsp;&nbsp;저장소를 사용합니다.&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/07EndomorphismSecp256k1" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/07EndomorphismSecp256k1/

pip3 install base58</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/928/66f/34b/92866f34b1dcfbce80b23fd56a913744.png" alt="endomorphism으로 secp256k1 속도 향상"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener">145&nbsp;</a><em>행에서</em>&nbsp;코드&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener">endomorphism.py를</a>&nbsp;&nbsp;엽니다 &nbsp;. 우리는 모든 짧은 값을 사용하여&nbsp;&nbsp;<em>endomorphism</em>&nbsp;&nbsp;으로&nbsp; 속도를 높입니다.<em></em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/9dfd594126117e07fc51a77a7c613180eb662f18/07EndomorphismSecp256k1/endomorphism.py#L145" target="_blank" rel="noreferrer noopener"></a><code>secp256k1</code><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def</strong> <strong>split_scalar_endo</strong>(k):
    n = N
    a1 = 0x3086d221a7d46bcde86c90e49284eb15
    b1 = -0xe4437ed6010e88286f547fa90abfe4c3
    a2 = 0x114ca50f7a8e2f3f657c1108d9d44cfd8
    b2 = a1
    c1 = div_nearest(b2 * k, n)
    c2 = div_nearest(-b1 * k, n)
    k1 = mod(k - c1 * a1 - c2 * a2, n)
    k2 = mod(-c1 * b1 - c2 * b2, n)
    k1neg = k1 &gt; POW_2_128
    k2neg = k2 &gt; POW_2_128
    <strong>if</strong> k1neg:
        k1 = n - k1
    <strong>if</strong> k2neg:
        k2 = n - k2
    <strong>return</strong> (k1neg, k1, k2neg, k2)</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener">기사</a><code>HEX</code>&nbsp;에서 게시한 형식&nbsp;&nbsp;의 개인 키를 복사합니다.&nbsp;<a href="https://cryptodeep.ru/kangaroo/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":4} -->
<h4>개인 키를 지정하는 Python 스크립트 endomorphism.py를 실행해 보겠습니다.</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 endomorphism.py 23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b &gt; pubkey.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3c5/6f1/3d7/3c56f13d77ef80024a8cfb16f80943fc.png" alt="endomorphism으로 secp256k1 속도 향상"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>공개 키의 결과는 pubkey.txt 파일에 저장됩니다.</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Откроем файл: pubkey.txt и проверим:

cat pubkey.txt

04ca5606a1e820e7a2f6bb3ab090e8ade7b04a7e0b5909a68dda2744ae3b8ecbfa280a47639c811134d648e8ee8096c33b41611be509ebca837fbda10baaa1eb15
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/448/529/511/4485295113ba74f334a01f4ed2b54bd4.png" alt="endomorphism으로 secp256k1 속도 향상"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>다음으로 Python 스크립트 pubtoaddr.py를 실행하여 비트코인 ​​주소를 가져옵니다.</h4>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 pubtoaddr.py

Откроем файл: BitcoinAddress.txt и проверим:

cat BitcoinAddress.txt

14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/1a4/805/542/1a480554216e020e1c53a9370661274a.png" alt="endomorphism으로 secp256k1 속도 향상"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
WIF:  5J64pq77XjeacCezwmAr2V1s7snvvJkuAz8sENxw7xCkikceV6e
HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d8c/78d/8eb/d8c78d8eb14e5246b495e09f59631e44.png" alt="bitaddress 웹 사이트에서 개인 키 확인" title="bitaddress 웹 사이트에서 개인 키 확인"/><figcaption class="wp-element-caption">bitaddress 웹 사이트에서 개인 키 확인</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>블록체인:</h3>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ed9/7da/c1d/ed97dac1dc07e2bce09fe0951d9f64de.png" alt="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" title="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE"/><figcaption class="wp-element-caption">www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>이 주제에 대해 다음 문헌을 읽을 수 있습니다.</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>Gallant, Robert P., Robert J. Lambert, Scott A. Wanston.&nbsp;</em><strong><em>"효과적인 엔도모피즘을 사용한 타원 곡선의 더 빠른 점 곱셈"</em></strong><em>&nbsp;.&nbsp;암호학에 관한 연례 국제 회의, pp. 190–200.&nbsp;스프링거, 베를린, 하이델베르크, (2001)</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>Hankerson, Darrell, Alfred J. Menezes 및 Scott Wanston.&nbsp;</em><strong><em>"타원 곡선 암호화에 대한 가이드"</em></strong><em>&nbsp;.&nbsp;컴퓨터 리뷰 46, 아니오.&nbsp;1 (2005)</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>할 피니.&nbsp;bitcointalk -&nbsp;&nbsp;</em><strong><em>"서명 확인 가속화"</em></strong><em>&nbsp;.&nbsp;(2011)&nbsp;</em>&nbsp;<a href="https://bitcointalk.org/index.php?topic=3238.0" target="_blank" rel="noreferrer noopener">https://bitcointalk.org/index.php?topic=3238.0</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>Blahut, Richard E.&nbsp;&nbsp;</em><strong><em>"암호화 및 보안 통신"</em></strong><em>&nbsp;.&nbsp;캠브리지 대학 출판부, (2014)</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>&nbsp;이 비디오는 암호 화폐의&nbsp;&nbsp;&nbsp;약한 서명에 대한&nbsp;&nbsp;&nbsp;타원 곡선의 데이터 및 암호화의 재정적 보안을 보장하기 위해&nbsp;&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>&nbsp;포털용 으로 제작되었습니다.&nbsp;<code>secp256k1</code><code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/07EndomorphismSecp256k1" target="_blank" rel="noreferrer noopener"><strong><u>원천</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>텔레그램</strong></a><strong>&nbsp;:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong><u>https://t.me/cryptodeeptech</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/DH6FyNY-Gh0" target="_blank" rel="noreferrer noopener"><strong>영상자료</strong></a><strong>&nbsp;:&nbsp;&nbsp;<u><a href="https://youtu.be/DH6FyNY-Gh0" target="_blank" rel="noreferrer noopener">https://youtu.be/DH6FyNY-Gh0</a></u></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/endomorphism"><strong>출처</strong></a><strong>&nbsp;:&nbsp;&nbsp;</strong><a href="https://cryptodeep.ru/endomorphism" target="_blank" rel="noreferrer noopener"><strong>https://cryptodeep.ru/endomorphism</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2404} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/011-1024x576.png" alt="Ускорение secp256k1 с помощью эндоморфизма" class="wp-image-2404"/></figure>
<!-- /wp:image -->
