# Blockchain의 첫 번째 심각한 취약점과 RawTX 파일에서 공개 키 Bitcoin ECDSA RSZ 값을 가져오는 방법

<!-- wp:embed {"url":"https://www.youtube.com/embed/BYd-cuFRZmM","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/BYd-cuFRZmM
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"><strong>이 기사 에서는</strong></a>&nbsp;Bitcoin 블록 체인에서 서명 값을 추출하는 방법에 대해 이야기&nbsp; 하지만 먼저&nbsp;<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener">Niels Schneider</a>&nbsp;&nbsp;(&nbsp;<em>일명</em>&nbsp;&nbsp;tcatm&nbsp;&nbsp;)&nbsp;<code>ECDSA R, S, Z</code>&nbsp;에 의해 발견 된 블록 체인 트랜잭션의 첫 번째 심각한 취약점을 기억하십시오.&nbsp;<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"></a><code>Nils Schneider</code>&nbsp;<em></em><a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>Bitcoin 개발자 및 "BitcoinWatch"</em>&nbsp;&nbsp;및&nbsp; "BitcoinCharts"&nbsp;소유자&nbsp;&nbsp;<em>.</em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/20d/674/8c4/20d6748c4bdd5e28ada4e9d06b9e8d35.png" alt="4.1 Bitcoin에 대한 위험한 무작위 공격의 역사" title="4.1 Bitcoin에 대한 위험한 무작위 공격의 역사"/><figcaption class="wp-element-caption">4.1 Bitcoin에 대한 위험한 무작위 공격의 역사</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>문서&nbsp;&nbsp;<code>[PDF]</code>:&nbsp;<a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener"><em>개인 키 복구 조합 공격: 열악한 RNG 이벤트가 있는 인기 비트코인 ​​키 관리, 지갑 및 콜드 스토리지 솔루션의 극도의 취약성에 대해</em></a><a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener">&nbsp;<em></em></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em>2012년 12월 25일</em>&nbsp;&nbsp;Nils는 일부 비트코인 ​​블록체인 거래에서 잠재적인 약점을 발견했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>이 거래를 보십시오:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>transaction:</code>&nbsp;<a href="https://www.blockchain.com/btc/tx/9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1" target="_blank" rel="noreferrer noopener">9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/cc3/2e2/94a/cc32e294aa0e77019d1581ce61893349.png" alt="Blockchain의 첫 번째 심각한 취약점과 RawTX 파일에서 공개 키 Bitcoin ECDSA RSZ 값을 가져오는 방법"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>input script 1:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1022044e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff

input script 2:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad102209a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 트랜잭션에는 두 개의 입력과 하나의 출력이 있습니다.<br>두 개의 입력 스크립트를 자세히 살펴보면 처음과 끝에 동일한 바이트가 꽤 많이 있음을 알 수 있습니다.<br>끝에 있는 바이트는 동전이 사용되는 주소의 16진수로 인코딩된 공개 키이므로 아무런 문제가 없습니다.<br>그러나 스크립트의 전반부는 실제 서명입니다&nbsp;&nbsp;<code>(r, s)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>r1: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1
r2: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1

s1: 44e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e
s2: 9a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>보시&nbsp;&nbsp;<code>r1</code>&nbsp;다시피 똑같습니다&nbsp;&nbsp;<code>r2</code>.&nbsp;<em>이것은&nbsp;&nbsp;</em><strong><em><u>큰 문제</u></em></strong><em>&nbsp;입니다 .</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><u>개인 키를</u></strong>&nbsp;&nbsp;이 공개 키로&nbsp;복원할 수 있습니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>04dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>이를 위해 학교 대수학의 간단한 공식을 사용할 수 있습니다 😉</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>private key = (<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>z1</code>&nbsp;우리는 단지&nbsp;&nbsp;찾고&nbsp;<code>z2</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>хэши</code>&nbsp;서명이 필요한 출력&nbsp;입니다&nbsp; .&nbsp;출력 트랜잭션을 가져와 계산해 보겠습니다( 로 계산&nbsp;&nbsp;<code>OP_CHECKSIG</code>).</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>z1: c0e2d0a89a348de88fda08211c70d1d7e52ccef2eb9459911bf977d587784c6e
z2: 17b0f41c8c337ac1e18c98759e83a8cccbc368dd9d89e5f03cb633c265fd0ddc</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>다음으로 이 모든 값을 하나의 Python</em>&nbsp;스크립트 로&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">압축</a>&nbsp;해 보겠습니다&nbsp;&nbsp;<em>.</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/c5f/301/358/c5f301358b79c833d7701b7c883235a7.png" alt="파이썬 스크립트:vulnerabilityR.py" title="파이썬 스크립트:vulnerabilityR.py"/><figcaption class="wp-element-caption">파이썬 스크립트:vulnerabilityR.py</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>p</code>비트코인이 사용하는&nbsp;<code>G</code>곡선의&nbsp;&nbsp;&nbsp;매개변수인 크기 정도입니다&nbsp; .<code>secp256k1</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>계산을 위한 필드를 만들어 보겠습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = GF(<strong>p</strong>)</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K((<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>)))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:&nbsp;<code>python3 vulnerabilityR.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>다음으로 우리의 스크립트:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">vulnerabilityR.py</a>&nbsp;는 &nbsp;이 필드에서&nbsp;<strong><u>개인 키를</u></strong>&nbsp;&nbsp;계산합니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm
WIF:  5KJp7KEffR7HHFWSFYjiCUAntRSTY69LAQEX1AUzaSBHHFdKEpQ
hex:  c477f9f65c22cce20657faa5b2d1d8122336f851a508a1ed04e479c34985bf96</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/a69/992/dcf/a69992dcf93bacd0324c9a06722be9b5.png" alt="bitaddress 웹 사이트에서 개인 키 확인" title="bitaddress 웹 사이트에서 개인 키 확인"/><figcaption class="wp-element-caption">bitaddress 웹 사이트에서 개인 키 확인</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em><u>개인 키를 찾았습니다!</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm
</div></figure>
<!-- /wp:embed -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/049/126/899/049126899d0dc2b84a30b18fc496c258.png" alt="
0.1638109 비트코인" title="
0.1638109 비트코인"/><figcaption class="wp-element-caption">0.1638109 비트코인</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>물론 Bitcoin 개발자는 결정적 기능을 도입하여 이 취약점을 수정했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 기능은&nbsp;&nbsp;<code>RFC 6979</code>&nbsp;비트코인 ​​서명에 무작위 요소를 도입하여 트랜잭션의 암호화 강도를 향상시킵니다.&nbsp;<code>ECDSA</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>문서&nbsp;&nbsp;<code>[PDF]</code>:&nbsp;<a href="https://datatracker.ietf.org/doc/html/rfc6979" target="_blank" rel="noreferrer noopener"><em>RFC 6979: 디지털 서명 알고리즘(DSA) 및 타원 곡선 디지털 서명 알고리즘(ECDSA)의 결정적 사용</em></a><a href="https://eprint.iacr.org/2014/848.pdf">&nbsp;</a><a href="https://datatracker.ietf.org/doc/html/rfc6979" target="_blank" rel="noreferrer noopener"><em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>우리가 실제로 알고 있듯이 비트코인 ​​블록체인에는 완전히 다른 취약한 트랜잭션이 있습니다.</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>우리는 이전&nbsp;&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><em>에 다음과 같이</em></a><code>статью</code>&nbsp;게시했습니다 .&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><em></em></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/6b8/723/07d/6b872307d4a4dc3a74386c2b83d133a2.png" alt="https://habr.com/ru/post/671932/" title="https://habr.com/ru/post/671932/"/></a></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/RawTX.json" target="_blank" rel="noreferrer noopener">이제 "RawTX.json" 파일(&nbsp;</a><a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><strong>01BlockchainGoogleDrive</strong></a>&nbsp;&nbsp;에 있음&nbsp;&nbsp;&nbsp;)&nbsp;에서&nbsp;&nbsp;공개 키&nbsp;&nbsp;<code>Bitcoin</code>&nbsp;<code>ECDSA</code>&nbsp;와 값을&nbsp; 가져오겠습니다.<code>R, S, Z</code><a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/RawTX.json" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>이렇게 하려면 Google Colab용 터미널&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[&nbsp;<strong>TerminalGoogleColab] 을 사용하십시오.</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener"><strong>이전에 "GITHUB에서 작업하기 위한 모든 편의를 제공하는 Google Colab의 TERMINAL"이라는</strong></a>&nbsp;비디오를 녹화했습니다.&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener"><strong></strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener"><strong>자세한 암호 분석을 위해 "CryptoDeepTools"</strong></a>&nbsp;리포지토리를 살펴보고&nbsp;&nbsp;<em>Bash 스크립트가</em>&nbsp;&nbsp;어떻게 작동하는지 자세히 살펴보겠습니다&nbsp;&nbsp;.&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>팀:</strong></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/02BreakECDSAcryptography/

sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt

chmod +x getsign.sh

./getsign.sh</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/9bf/c35/0c7/9bfc350c715272db79f6bd5c6039e924.png" alt="파일" title="파일"/><figcaption class="wp-element-caption">파일</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5f0/cf5/6f0/5f0cf56f00c897f69fab24e8a3073588.png" alt="Bash 스크립트 코드: getsign.sh" title="Bash 스크립트 코드: getsign.sh"/><figcaption class="wp-element-caption">Bash 스크립트 코드: getsign.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>이제 Bash 스크립트</em>&nbsp;의 전체 작업을 자세히 살펴보겠습니다&nbsp;&nbsp;.&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat RawTX.json &gt; index.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>파일을&nbsp;&nbsp;<code>RawTX.json</code>&nbsp;새 파일로&nbsp; 복사하기<code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>for</strong> run <strong>in</strong> {1..4}; <strong>do</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>파일에서 4줄을</em>&nbsp;&nbsp;사용하기&nbsp;&nbsp;<code>ЦИКЛ</code>&nbsp;때문에&nbsp;&nbsp;파일을 엽니다.&nbsp;<code>index.json</code>&nbsp;<em></em><code>{1..4}</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>export LINE=1 ; sed -n "${LINE}p" index.json &gt; index2.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>유틸리티는&nbsp;&nbsp;<em>1번 줄을</em><code>export</code>&nbsp;&nbsp;가져와&nbsp;&nbsp;&nbsp;새 파일에 저장합니다.&nbsp;<em></em><code>index2.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sed -i '1d' index.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>유틸리티는&nbsp;&nbsp;파일에서&nbsp;&nbsp;<em>라인 #1을&nbsp;</em><code>sed</code>&nbsp;&nbsp;제거합니다.&nbsp;<em></em><code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/972/d1b/555/972d1b5554e84191da57b16415061198.png" alt="echo 유틸리티는 fileopen.py를 위한 Python 스크립트를 생성합니다." title="echo 유틸리티는 fileopen.py를 위한 Python 스크립트를 생성합니다."/><figcaption class="wp-element-caption">echo 유틸리티는 fileopen.py를 위한 Python 스크립트를 생성합니다.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 fileopen.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>Python 스크립트를</em>&nbsp;&nbsp;실행&nbsp;&nbsp;<code>fileopen.py</code>&nbsp;하고 새&nbsp;&nbsp;<em>Bash 스크립트를</em>&nbsp;성공적으로 생성합니다 .&nbsp;<code>signscript.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x signscript.sh
./signscript.sh</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>우리는 Bash 스크립트</em>&nbsp;에 대한 권리를 얻습니다&nbsp;&nbsp;: signscript.sh</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>결과적으로&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py&nbsp;</a><em>Python 스크립트</em>&nbsp;&nbsp;가 시작되고 &nbsp;결국&nbsp; Bitcoin의&nbsp;값&nbsp;&nbsp;&nbsp;과 공개 키를 추출합니다.<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/breakECDSA.py" target="_blank" rel="noreferrer noopener"></a><code>RawTX</code><code>R, S, Z</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 모든 것이 파일에 저장됩니다.&nbsp;<code>"signatures.json"</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2e1/9df/c27/2e19dfc270a6f0bc6bd2ea9123215442.png" alt="파일: &quot;signatures.json&quot; 비트코인 ​​공개 키 및 R, S, Z 값" title="파일: &quot;signatures.json&quot; 비트코인 ​​공개 키 및 R, S, Z 값"/><figcaption class="wp-element-caption">파일: "signatures.json" 비트코인 ​​공개 키 및 R, S, Z 값</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>rm</strong> <strong>signscript</strong>.sh
<strong>rm</strong> <strong>fileopen</strong>.py</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 유틸리티는&nbsp;&nbsp;<em>Python 스크립트를</em><code>rm</code>&nbsp;&nbsp;제거&nbsp;&nbsp;&nbsp;하고 새&nbsp;&nbsp;<em>Bash 스크립트를</em>&nbsp;성공적으로 생성합니다 .&nbsp;<em></em>&nbsp;<code>fileopen.py</code><em></em><code>signscript.sh</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>done</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>결과적으로 모든 것이&nbsp;<em>&nbsp;4주기 후에 종료됩니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>rm <strong>index</strong>.json</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>주기가 닫히고 유틸리티&nbsp;&nbsp;<code>rm</code>&nbsp;가 삭제됩니다.&nbsp;<code>index.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>배쉬 스크립트</em>&nbsp;:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a>&nbsp;<code>Завершает работу!</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>이제 우리는 다음을 배웠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Bitcoin&nbsp;</code>에서&nbsp;공개 키 가져오기&nbsp;<code>&nbsp;ECDSA</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>가치를 얻으&nbsp;&nbsp;<code>R, S, Z</code>&nbsp;십시오<code>&nbsp;ECDSA</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>신청하세요&nbsp;<code>криптоанализа</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>소스 코드:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>텔레그램:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>동영상 자료:&nbsp;&nbsp;<a href="https://youtu.be/BYd-cuFRZmM" target="_blank" rel="noreferrer noopener">https://youtu.be/BYd-cuFRZmM</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/BYd-cuFRZmM","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/BYd-cuFRZmM
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
