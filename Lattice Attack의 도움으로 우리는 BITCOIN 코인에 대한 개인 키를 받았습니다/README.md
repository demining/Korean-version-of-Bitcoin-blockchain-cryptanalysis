# Lattice Attack의 도움으로 우리는 BITCOIN 코인에 대한 개인 키를 받았습니다.

<!-- wp:embed {"url":"https://www.youtube.com/embed/YP4Xj6gUcf4","type":"rich","providerNameSlug":"","responsive":true,"align":"center","className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed aligncenter is-type-rich wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/YP4Xj6gUcf4
</div></figure>
<!-- /wp:embed -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>그리드 공격에 대해 무엇을 알고 있습니까?</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>먼저&nbsp;&nbsp;<em>타원 곡선 디지털 서명 알고리즘은</em>&nbsp;<code>(ECDSA)</code>&nbsp;&nbsp;많은 코드 리뷰에서 볼 수 있는 일반적인 디지털 서명 체계입니다.&nbsp;몇 가지 바람직한 속성이 있지만 비밀 난스의 1비트 미만을 드러내는 부채널 공격으로 개인 키를 복구하기에는 매우 취약할 수도 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>ECDSA</code>&nbsp;디지털 서명 알고리즘의 특별한 형식입니다&nbsp;&nbsp;<code>(DSA)</code>.&nbsp;<code>DSA</code>&nbsp;키 생성, 서명 및 확인의 세 가지 알고리즘으로 정의되는 상당히 일반적인 디지털 서명 체계입니다.&nbsp;<em>키 생성 알고리즘은 개인 및 공개 키를 생성합니다.&nbsp;</em>&nbsp;<em>개인 키는 서명 생성을 담당합니다.&nbsp;</em>&nbsp;<em>공개 키는 서명 확인을 담당합니다.&nbsp;</em>&nbsp;서명 알고리즘은 메시지와 개인 키를 입력으로 받아 서명을 생성합니다.&nbsp;확인 알고리즘은 메시지, 서명 및 공개 키를 입력으로 사용하고 서명이 유효한지 여부를 나타내는&nbsp;<code>true</code>&nbsp;또는&nbsp;&nbsp;의 값을 반환합니다&nbsp; .<code>false</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>DSA</code>&nbsp;는 모든 수학적 그룹에 대해 정의되며 이 체계는 이산 로그 문제가 해당 그룹에 대해 어려운 한 안전합니다.&nbsp;일반적으로 사용되는 그룹은 정수 모듈로 a 소수 p입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 그룹과 함께 우리는 그룹 생성기 g와 일부 암호화 보안&nbsp;&nbsp;<em>해시</em>&nbsp;&nbsp;함수를&nbsp; 갖게 됩니다&nbsp;<code>H</code>.&nbsp;우리는 그것을 가정할 수&nbsp;&nbsp;<code>p , g</code>&nbsp;있고&nbsp;&nbsp;<code>H</code>&nbsp;상식이 될 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>x</code>&nbsp;키 생성은 먼저 모듈로 정수에서&nbsp;&nbsp;값을 무작위로 선택하여 작동합니다&nbsp;&nbsp;<code>p</code>&nbsp;.&nbsp;그런 다음 값이 계산됩니다.&nbsp;<code>y = g^x mod p</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>서명의 개인 키는 이고&nbsp;&nbsp;<code>x</code>&nbsp;공개 키는 입니다&nbsp;&nbsp;<code>y</code>&nbsp;.&nbsp;서명 키는 서명을 만들 수 있는 키이므로 비밀로 유지해야 합니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>서명 알고리즘은 메시지&nbsp;&nbsp;<code>m</code>&nbsp;와 비밀 키 x에서 서명을 생성합니다.&nbsp;먼저 임의의 그룹 요소가 생성됩니다&nbsp;&nbsp;<code>k</code>&nbsp;.&nbsp;이것은 논스(nonce)로 알려져 있으며 공격에 있어 중요합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 값이 계산&nbsp;&nbsp;<code>r = g^k mod p</code>&nbsp;되고&nbsp;<code>s = ( k^-1 ( H ( m ) + xr )) mod p</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>여기서&nbsp;&nbsp;<code>k^- 1</code>&nbsp;는 역군이고&nbsp;&nbsp;<code>H ( m )</code>&nbsp;해시 m을 계산한 결과를 정수 모듈로 p로 해석한 결과이다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>서명은 한 쌍으로 정의됩니다&nbsp;&nbsp;<code>( r , s )</code>.&nbsp;(참고:&nbsp;&nbsp;<code>r</code>&nbsp;또는&nbsp; 값 중 하나가&nbsp;<code>s</code>와 같으면&nbsp;&nbsp;<code>0</code>알고리즘이 새 값 으로 다시 시작됩니다&nbsp;&nbsp;<code>k</code>&nbsp;.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>( r , s )</code>검증 알고리즘은 서명 , 메시지&nbsp; 및 공개 키 y를&nbsp;입력으로&nbsp; 받습니다&nbsp;<code>m</code>&nbsp;.&nbsp;Let&nbsp;&nbsp;<code>ŝ = s^-1</code>&nbsp;, 알고리즘은 true 를 반환하는 경우에만&nbsp;&nbsp;<code>r , s ≠ 0 и r = ( g H ( m ) y r ) ŝ</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 유효성 검사는 때문에 작동&nbsp;&nbsp;<code>g^H( m ) y^r = g^H(m)+ xr = g^ks</code>하므로&nbsp;<code>(g^H(m)y^r)^ŝ = g^k = r</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>디지털 서명 체계는 위조할 수 없는 경우 안전한 것으로 간주됩니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>불변성은 공식적인 암호화 의미를 갖지만 높은 수준에서 비밀 키를 모르면 서명을 만들 수 없음을 의미합니다(비밀 키에서 생성된 기존 서명을 복사하지 않는 한).&nbsp;<code>DSA</code>불연속 로그의 가정 하에서 위조가 불가능한&nbsp;것으로 입증되었습니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>디지털 서명은 수학적 그룹에 대해 정의됩니다.&nbsp;<code>DSA</code>&nbsp;이 수학적 그룹으로 타원 곡선 그룹과 함께 사용하면 이라고&nbsp;&nbsp;합니다&nbsp;&nbsp;<code>ECDSA</code>.&nbsp;<em>타원 곡선 그룹은 의</em>&nbsp;&nbsp;쌍인 타원 곡선 점으로 구성되며&nbsp;&nbsp;&nbsp;일부 에 대한&nbsp;&nbsp;<code>( x , y )</code>방정식을 만족합니다&nbsp;&nbsp;&nbsp;.&nbsp;<em>이 블로그 게시물에서 알아야 할 것은 타원 곡선을 사용하여 유한 그룹을 정의할 수 있다는 것입니다. 즉, 그룹 생성기(타원 곡선 점)와 덧셈 및 점</em>&nbsp;곱셈&nbsp;&nbsp;<em><u>연산을</u></em>&nbsp;&nbsp;정확히&nbsp;&nbsp;&nbsp;이와 동일하게&nbsp;<em><u>얻을</u></em>&nbsp;수 있음을 의미합니다.&nbsp;&nbsp;정수로 할 수 있습니다.&nbsp;그들은 유한한 그룹, 생성기,<code>y^2 = x^3 + ax + b</code><code>a , b</code><code>g</code>&nbsp;<em></em><em><u></u></em><em><u></u></em><code>g</code>&nbsp;, 유한 순서를 가질 것입니다&nbsp;&nbsp;<code>p</code>.&nbsp;<em>이 블로그 게시물에서는 이러한 타원 곡선</em>&nbsp;작업 이 어떻게 작동하는지 설명하거나 알 필요가 없습니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>비밀 키는</em>&nbsp;<code>x</code>&nbsp;&nbsp;여전히 임의의 값 modulo integers 입니다&nbsp;&nbsp;<code>p</code>&nbsp;.&nbsp;<code>ECDSA</code>&nbsp;와 동일&nbsp;&nbsp;<code>DSA</code>하지만 다른 그룹에서 작동합니다.&nbsp;이제 공개 키는&nbsp;&nbsp;&nbsp;g가 이제 타원 곡선의 한 점이라는 점을 제외하면&nbsp;<code>y</code>&nbsp;여전히 로 계산됩니다&nbsp; .&nbsp;<code>y = g^x</code>이는 y가 타원 곡선의 한 점이 될 수도 있음을 의미합니다(이전에는 y가 모듈로 p의 정수였습니다).&nbsp;또 다른 차이점은 r 값을 계산하는 방법입니다.&nbsp;우리는 여전히 이전과 같이 정수 모듈로 p로 임의의 nonce k를 생성합니다.&nbsp;우리는 계산할 것입니다&nbsp;&nbsp;<code>g^k</code>&nbsp;, 그러나 다시&nbsp;<code>g</code>&nbsp;타원 곡선의 한 점이므로&nbsp;&nbsp;<code>g^k</code>&nbsp;역시 마찬가지입니다.&nbsp;따라서 계산&nbsp;&nbsp;<code>( x^k , y^k ) = g^k</code>&nbsp;하고 설정할&nbsp; 수 있습니다&nbsp;<code>r = x^k</code>&nbsp;.&nbsp;이제 그 의미&nbsp;<code>s</code>&nbsp;이전과 같이 계산할 수 있으며&nbsp; 이전과 같이&nbsp;<code>( r , s )</code>여전히 모듈로 정수인&nbsp; 서명을 얻습니다&nbsp;<code>p</code>&nbsp;.&nbsp;<code>r</code>&nbsp;확인하려면 조금 다르게&nbsp;계산한 사실을 수정해야 합니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>따라서 이전과 마찬가지로&nbsp;&nbsp;&nbsp;의 값을&nbsp;&nbsp;<em>계산</em><code>( g^H(m)y^r)^ŝ</code>&nbsp;&nbsp;하지만 이제 그 값은 타원 곡선의 한 점이므로&nbsp;&nbsp;<code>x</code>해당 점의 -좌표를 가져와 의 값과 비교합니다&nbsp;&nbsp;<code>r</code>&nbsp;.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>&nbsp;재사용된 nonce에서&nbsp;&nbsp;<u>비밀 키</u>&nbsp;복구&nbsp;</em><code>NONCES</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 그것이 무엇인지, 어떻게 작동하는지 이해했으므로&nbsp;&nbsp;<em><u>취약성을</u></em><code>ECDSA</code>&nbsp;&nbsp;시연해 보겠습니다&nbsp;&nbsp;.&nbsp;다시 말하지만 이것은 디지털 서명 방식이므로&nbsp;&nbsp;<em>비밀 키는</em>&nbsp;&nbsp;메시지에 서명한 사람 외에는 누구에게도 공개되지 않아야 합니다.<em><u></u></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>그러나 서명자가 서명을 발행하고 사용된 nonce도 발행하면&nbsp;&nbsp;<em>공격자는</em>&nbsp;&nbsp;즉시&nbsp;&nbsp;<em><u>비밀 키를</u></em>&nbsp;복구할 수 있습니다 .</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>( r , s )</code>&nbsp;메시지에 대한&nbsp;&nbsp;서명을 해제&nbsp;&nbsp;<code>m</code>&nbsp;하고 실수로 nonce 를 사용했음을 발견했다고&nbsp; 가정해 보겠습니다&nbsp;<code>k</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s = ( k^-1 ( H ( m ) + xr )),</code>&nbsp;비밀 키를 쉽게 계산할 수&nbsp;있기 때문에&nbsp; :</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s = (k^-1(H(m) + xr))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ks = H(m) + xr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ks – H(m) = xr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>x = r^-1(ks – H(m))</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>따라서 서명자는 자신의&nbsp;&nbsp;<em><u>개인 키를</u></em>&nbsp;비밀로 유지해야 할 뿐만 아니라 자신이 생성한 모든 nonce도 비밀입니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>서명자가 각&nbsp;&nbsp;<em><u>nonce를&nbsp; 비밀로 유지하더라도 실수로 하나의&nbsp;</u></em><em><u>nonce를</u></em><code>NONCES</code>&nbsp;반복하면&nbsp;&nbsp;&nbsp;(다른 메시지에 대해서도)&nbsp;&nbsp;<em><u>비밀 키를</u></em><strong>&nbsp;즉시 복구</strong>&nbsp;&nbsp;할 수도 있습니다&nbsp;&nbsp;.<em><u></u></em>&nbsp;<code>NONCES</code><em><u></u></em><strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>&nbsp;메시지에 대해 그리고 (각각) 동일한 nonce에서 생성된 두 개의 서명을 허용합니다&nbsp;&nbsp;<code>( r , s 1 )</code>&nbsp;.&nbsp;&nbsp;&nbsp;동일한&nbsp;&nbsp;nonce&nbsp;&nbsp;&nbsp;를&nbsp;&nbsp;&nbsp;가지므로 r 값이 동일하므로 공격자가 탐지하기 매우 쉽습니다.<code>( r , s 2 )</code><code>m 1</code><code>m 2</code><code>k</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s1 = k^-1(H(m1) + xr) and s2 = k^-1(H(m2) + xr)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>s1 – s2 = k^-1(H(m1) – H(m2))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>k(s1 – s2) = H(m1) – H(m2)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>k = (s1 – s2)^-1(H(m1) – H(m2))</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>위의 공식을 사용하여 nonce를 복구하면&nbsp;&nbsp;<code>k</code>&nbsp;앞에서 설명한 공격을 수행하여 개인 키를 복구할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">잠시 이것을 소화해 봅시다.</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em><u>서명 nonce가&nbsp;</u></em><code>NONCES</code>&nbsp;&nbsp;공개되면&nbsp;&nbsp;비밀&nbsp;&nbsp;<em>키를 즉시&nbsp;</em><em><u>복구</u></em>&nbsp;할 수 있으므로&nbsp;&nbsp;<strong><u>전체 서명 체계가 손상</u></strong>&nbsp;됩니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>또한 두 개의 nonce가 반복되면 메시지가 무엇이든&nbsp;&nbsp;<em>공격자가</em>&nbsp;&nbsp;이를 쉽게 감지하고 즉시&nbsp;&nbsp;<strong>비밀 키를 복구하여</strong>&nbsp;전체 체계를 깨뜨릴 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그것은 꽤 연약하고 단지&nbsp;&nbsp;<em>가벼운 공격</em>&nbsp;입니다 !</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;그러나 매우 자세하게 설명된&nbsp;&nbsp;<em>새로운&nbsp;</em>&nbsp;<strong><a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">Lattice At&nbsp;</a></strong><a href="https://youtu.be/YP4Xj6gUcf4"><strong>tack</strong></a>&nbsp;이 있습니다&nbsp;&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener"><em>(Joachim Breitner 및 Nadia Heninger).</em></a><code>Йоахим Брайтнер и Надя Хенингер</code><a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">&nbsp;<em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>문서&nbsp;&nbsp;<a href="https://eprint.iacr.org/2019/023.pdf" target="_blank" rel="noreferrer noopener">[PDF]</a>&nbsp;:&nbsp;&nbsp;<em>Biased Nonce Sense: 암호화폐의 취약한 ECDSA 서명에 대한 격자 공격</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2 class="wp-block-heading">비트코인 블록체인에서 특정 거래를 발견했습니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>거래:&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/tx/08d917f0fee48b0d765006fa52d62dd3d704563200f2817046973e3bf6d11f1f" target="_blank" rel="noreferrer noopener">08d917f0fee48b0d765006fa52d62dd3d704563200f2817046973e3bf6d11f1f</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>비트코인 주소:&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E" target="_blank" rel="noreferrer noopener">15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E</a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>가짜 서명을 곱하고 그리드를 적용했습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>GOOGLE COLAB</strong>&nbsp;&nbsp;에서 패키지 설치와 함께&nbsp;&nbsp;<em>Python 스크립트&nbsp;</em>&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">algorithmLLL.py를</a>&nbsp;사용하는 경우&nbsp;<strong></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>설치 &gt;&gt; SAGE + ECDSA + BITCOIN + 알고리즘 LLL</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>Private Key</code>&nbsp;우리&nbsp;&nbsp;는&nbsp;&nbsp;.&nbsp;<code>Bitcoin Wallet</code>&nbsp;_&nbsp;<code>ECDSA</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/777/37e/84b/77737e84bb453449fd6956a39c4eb195.png" alt="설치" title="설치"/><figcaption class="wp-element-caption">설치</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ae2/0b3/747/ae20b37475bfff1ce38f81cc206a93f3.png" alt="Bash 스크립트 실행: lattice.sh" title="Bash 스크립트 실행: lattice.sh"/><figcaption class="wp-element-caption">Bash 스크립트 실행: lattice.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/722/89e/9da/72289e9dab54d5aa568438a94a4c90a6.png" alt="HEX 형식의 결과 개인 키가 발견되었습니다!" title="HEX 형식의 결과 개인 키가 발견되었습니다!"/><figcaption class="wp-element-caption">HEX 형식의 결과 개인 키가 발견되었습니다!</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/469/217/84b/46921784bb73f1218ded9e16bc0f8abd.png" alt="파일: ONESIGN.txt(ECDSA 서명 R, S, Z 값)" title="파일: ONESIGN.txt(ECDSA 서명 R, S, Z 값)"/><figcaption class="wp-element-caption">파일: ONESIGN.txt(ECDSA 서명 R, S, Z 값)</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8cb/e22/f9c/8cbe22f9cd364064a8e005ac8ea4e99e.png" alt="Python 스크립트 algorithmLLL.py에 대한 가짜 서명을 전파했습니다." title="Python 스크립트 algorithmLLL.py에 대한 가짜 서명을 전파했습니다."/><figcaption class="wp-element-caption">Python 스크립트 algorithmLLL.py에 대한 가짜 서명을 전파했습니다.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/83f/750/d81/83f750d81ba83309039189495a10680a.png" alt="파일: PRIVATEKEY.txt" title="파일: PRIVATEKEY.txt"/><figcaption class="wp-element-caption">파일: PRIVATEKEY.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/202/982/105/2029821051232d8a95744863eaa65049.png" alt="파일: ADDRESS.txt" title="파일: ADDRESS.txt"/><figcaption class="wp-element-caption">파일: ADDRESS.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a>&nbsp;열고&nbsp;&nbsp;&nbsp;다음을 확인합니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4ce/93f/dd1/4ce93fdd168a7acc734929d342c8949c.png" alt="bitaddress 웹 사이트에서 개인 키 확인" title="bitaddress 웹 사이트에서 개인 키 확인"/><figcaption class="wp-element-caption">bitaddress 웹 사이트에서 개인 키 확인</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em><u>개인 키를 찾았습니다!</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E
</div></figure>
<!-- /wp:embed -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/00c/be7/072/00cbe70723846c402c4da47bcb6d47b3.png" alt="0.001비트코인" title="0.001비트코인"/><figcaption class="wp-element-caption">0.001비트코인</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 15N1KY5ohztgCXtEe13BbGRk85x2FPgW8E
WIF:  5JCAmNLXeSwi2SCgNH7wRL5qSQhPa7sZvj8eDwxisY5hJm8Uh92
HEX:  31AFD65CAD430D276E3360B1C762808D1D051154724B6FC15ED978FA9D06B1C1 </code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>&nbsp;이 비디오 는 BITCOIN 암호화폐의 취약한 ECDSA 서명에 대한 데이터 및 secp256k1 타원 곡선 암호화의 재정적 보안을 보장하기 위해&nbsp;<a href="https://cryptodeep.ru/lattice-attack" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>&nbsp;포털용 으로 제작되었습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>&nbsp;<a href="https://youtu.be/YP4Xj6gUcf4" target="_blank" rel="noreferrer noopener">https://youtu.be/YP4Xj6gUcf4</a></strong>&nbsp;–<strong>&nbsp;동영상 자료</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>cryptodeeptech@gmail.com – 모든 질문에 대한 이메일</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeep_tech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeep_tech</a>&nbsp;– Telegram을 통한 기술 지원</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/YP4Xj6gUcf4","type":"rich","providerNameSlug":"","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/YP4Xj6gUcf4
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
