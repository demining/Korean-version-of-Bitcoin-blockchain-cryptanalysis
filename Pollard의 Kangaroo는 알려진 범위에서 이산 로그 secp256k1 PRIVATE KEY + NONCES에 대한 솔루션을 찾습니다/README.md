# Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다.

<!-- wp:embed {"url":"https://www.youtube.com/embed/UGUJyxOhBBQ","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/UGUJyxOhBBQ
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>이 글에서는 전산수론 분야에서 ECDLP를 위한 가장 빠른 알고리즘인 Pollard의 캥거루를 Pollard의 람다 알고리즘이라고도 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Pollard의 캥거루 방법은&nbsp;&nbsp;&nbsp;임의의 순환 그룹에서&nbsp;<a href="https://cryptodeep.ru/doc/discretelog.pdf" target="_blank" rel="noreferrer noopener"><strong>이산 로그를 계산합니다.&nbsp;</strong></a>이산 로그가 특정 범위에 있는 것으로 알려진 경우 적용됩니다&nbsp;&nbsp;<code>[ a , b ]</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>폴라드의 캥거루 장점:</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>메모리를 거의 사용하지 않음</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>선형 가속도와 병렬화 가능</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>메모리 요구 사항을 효과적으로 추적할 수 있습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>이 모든 것이 캥거루 방법을 이산 로그 문제를 해결하는 가장 강력한 방법으로 만듭니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>ECDSA 서명 체계를 깨는 한 가지 방법은 이산 로그 문제를 해결하는 것입니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>설정에서&nbsp; 지수 미적분법과 같은 하위 지수 시간 알고리즘은 사용되지 않으며&nbsp;&nbsp;Pollard kangaroo 방법이&nbsp;<code>ECDSA</code>&nbsp;가장 잘 알려진 솔루션 방법&nbsp; 입니다.&nbsp;<code>DLP</code>다양한 이론적 측면으로 부담을 드리지 않도록 노력하겠습니다.&nbsp;실험적인 부분으로 넘어 갑시다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>비트코인 블록체인에서 알 수 있듯이 BTC 코인을 보낸 사람은 항상 자신의&nbsp;&nbsp;<em>공개 키를</em>&nbsp;공개합니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>폴라드 캥거루 방식의 경우 공개키나&nbsp;</em><em>서명</em>&nbsp;&nbsp;&nbsp;값만&nbsp;&nbsp;알면 충분하다&nbsp;&nbsp;<code>R</code>&nbsp;(값&nbsp; 도&nbsp;&nbsp;타원곡선 평면상의&nbsp;&nbsp;&nbsp;좌표점이므로&nbsp;&nbsp;&nbsp;에서&nbsp;&nbsp;<code>R</code>&nbsp;일종의&nbsp;&nbsp;<em>공개키</em>&nbsp;이다 ) .<code>Nonces</code><code>x</code><code>secp256k1</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>범위&nbsp;</em>&nbsp;<code>PRIVATE KEY</code>&nbsp;<em>또는 범위를</em>&nbsp;<code>NONCES</code>&nbsp;정의하는 것만 남아 있습니다 .</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>비트코인 블록체인에서 서명을 생성하는 일부 장치는&nbsp;<code>ECDSA</code>값에 대한 바이트 정보를 부분적으로 공개할 수 있습니다.&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>우리는 이것이 BTC 코인을 잃을 수 있는 잠재적인 위협이라고 생각하며 모든 사람이 항상 소프트웨어를 업데이트하고 확인된 장치만 사용할 것을 강력히 권장합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>최근에 우리는 비트코인 ​​블록체인에 대한 암호화 분석을 수행했으며 이러한 트랜잭션을 여러 개 발견했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>출금 금액이 501.06516041 BTC인 이 비트코인 ​​주소를 살펴보세요.</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3d9/756/d50/3d9756d50d09b0584c5967175184dd42.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다." title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>이 비트코인 ​​주소 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</strong></a>&nbsp;의 트랜잭션에서&nbsp;&nbsp;값에 대한 바이트 정보가 부분적으로 공개되었습니다.&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><strong><u>지난 기사</u></strong></a>&nbsp;에서 알 수 있듯이&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><strong><u></u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2f6/78f/d0f/2f678fd0faefca8c25518666490d795f.png" alt="habr.com/en/post/671932/" title="habr.com/en/post/671932/"/><figcaption class="wp-element-caption">habr.com/en/post/671932/</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>비밀 키 범위 찾기</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 트랜잭션을 찾아 Pollard의 캥거루 방식을 사용하여&nbsp;&nbsp;<em><u>개인 키를 복구해 보겠습니다.</u></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>이전에 비디오 지침을</em>&nbsp;녹화했습니다&nbsp;&nbsp;.&nbsp;&nbsp;<a href="https://cryptodeep.ru/terminal-google-colab/" target="_blank" rel="noreferrer noopener">"Google Colab의 TERMINAL은 GITHUB에서 작업하기 위한 모든 편의를 만듭니다."</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>터미널에서 Google Colab 열기&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab"><strong>[TerminalGoogleColab]</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">RawTX를 검색하려면 저장소 "01BlockchainGoogleDrive"</a>&nbsp;를 사용합니다.&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/01BlockchainGoogleDrive/

chmod +x getrawtx.sh

./getrawtx.sh 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/496/30f/b12/49630fb12d6c1cf64f99f24f530add95.png" alt="Bash 스크립트 실행: getrawtx.sh" title="Bash 스크립트 실행: getrawtx.sh"/><figcaption class="wp-element-caption">Bash 스크립트 실행: getrawtx.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>비트코인 주소&nbsp;&nbsp;<a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener">14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</a>&nbsp;트랜잭션의 모든 내용이 &nbsp;파일에 저장되었습니다.&nbsp;<code>RawTX.json</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>파일 열기:&nbsp;&nbsp;<code>RawTX.json</code>&nbsp;이 거래를 찾습니다.&nbsp;<code>[строка №10]</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2c1/dca/207/2c1dca20782c1e09325836c491aeaaf0.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>명령을 사용&nbsp;&nbsp;<code>export</code>&nbsp;하고 이 줄을 별도로 저장&nbsp;&nbsp;<code>№10</code>&nbsp;합니다&nbsp;&nbsp;<code>RawTX.json</code>.&nbsp;<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>export LINE=10 ; sed -n "${LINE}p" RawTX.json &gt; RawTX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b8b/0c2/508/b8b0c25080dfe2ad36c112e2f0015e72.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat RawTX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b1a/a44/976/b1aa44976ad24df74e02246a8747db31.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://live.blockcypher.com/btc/decodetx/" target="_blank" rel="noreferrer noopener"><strong>Decode Raw Bitcoin Hexadecimal Transaction</strong></a><code>TxID</code>&nbsp;&nbsp;웹 사이트를&nbsp;&nbsp;열고&nbsp;&nbsp;&nbsp;우리를 삽입하십시오&nbsp;&nbsp;결과적으로 TxID를 얻습니다.<a href="https://live.blockcypher.com/btc/decodetx/" target="_blank" rel="noreferrer noopener"><strong></strong></a><code>RawTX</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/166/292/2df/1662922df068e4d009f0efcbecc2089d.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>결과적으로 TxID를 얻습니다.</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/cc2/bf5/146/cc2bf5146ef7a2e6004d79986535255d.png" alt="TxID: b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b" title="TxID: b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b"/><figcaption class="wp-element-caption">TxID: b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>TxID 링크 열기:<br><a href="https://btc.exan.tech/tx/b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b" target="_blank" rel="noreferrer noopener">https://btc.exan.tech/tx/b5add54960756c58ebabb332c5ef89098d2c3b8f2107b939ec542178e846108b</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/c32/5a8/e40/c325a8e40de9ca6f15431dac1dcfe274.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/3b2/8d1/648/3b28d1648bf0cf157833dbc3b0821fd8.png" alt="RawTX 확인" title="RawTX 확인"/><figcaption class="wp-element-caption">RawTX 확인</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>이제 우리는 값에 대한 정보 바이트의 부분 공개를 찾습니다.&nbsp;<code>"K" (NONCES)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이를 위해 스크립트를 사용합니다.&nbsp;<code>«RangeNonce»</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>«RangeNonce»</code>&nbsp;비밀 키의 범위를 찾는 스크립트입니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>배포 키트의 버전을 선택합시다&nbsp;&nbsp;<code>GNU/Linux</code>&nbsp;.&nbsp;<code>Google Colab</code>&nbsp;제공한다&nbsp;<code>UBUNTU 18.04</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/94d/d82/af4/94dd82af4d7155e548aa7241df9b3206.png" alt="범위논스" title="범위논스"/><figcaption class="wp-element-caption">범위논스</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>에 모든 파일 업로드&nbsp;<code>Google Colab</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/751/91d/9a2/75191d9a233987a74ed0fa016aa5e2a1.png" alt="RangeNonce + Google Colab" title="RangeNonce + Google Colab"/><figcaption class="wp-element-caption">RangeNonce + Google Colab</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>스크립트에 대한 권한을 허용하고 스크립트를 실행합시다&nbsp;<code>«RangeNonce»</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>팀:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x RangeNonce
./RangeNonce
cat Result.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8ff/546/0c3/8ff5460c3570ebbbb3c7fb0f6a394fd9.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>모든 것이 파일에 저장됩니다: Result.txt</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2af/471/f7e/2af471f7eb46f84157b402ed67ea9139.png" alt="결과.txt" title="결과.txt"/><figcaption class="wp-element-caption">결과.txt</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>이것은 "K" 값(NONCES)의 정보 바이트에 대한 부분 공개입니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>따라서 우리의&nbsp;&nbsp;<u>비밀 키는&nbsp;</u><u>다음 범위</u>&nbsp;&nbsp;에 있습니다&nbsp;&nbsp;.</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K = 070239c013e8f40c8c2a0e608ae15a6b00000000000000000000000000000000
K = 070239c013e8f40c8c2a0e608ae15a6bffffffffffffffffffffffffffffffff</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/204/ef7/984/204ef79845ae3d93a9c93d43f81e484b.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong></strong>형식의 초기&nbsp;&nbsp;<code>32</code>&nbsp;숫자와 문자&nbsp; 에&nbsp;<strong>주의하십시오</strong><code>HEX</code>&nbsp;&nbsp;. 서명 값은&nbsp;&nbsp;<em><u>비밀 키의 범위,</u></em>&nbsp;&nbsp;즉 값과&nbsp;&nbsp;<code>Z</code>&nbsp;일치합니다&nbsp; .<em><u></u></em><code>"K" (NONCES)</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2>이것은 매우 심각한 ECDSA 서명 오류입니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>위에서 말했듯이 폴라드 캥거루 방식의 경우&nbsp;&nbsp;<em>공개키나&nbsp;</em><em>&nbsp;서명</em>&nbsp;&nbsp;값 &nbsp;만 알면 충분하다&nbsp;<code>R</code>&nbsp;(값&nbsp; 도&nbsp;&nbsp;타원곡선 평면상의&nbsp;&nbsp;&nbsp;좌표점이므로&nbsp;&nbsp;&nbsp;에서&nbsp;&nbsp;<code>R</code>&nbsp;일종의&nbsp;&nbsp;<em>공개키</em>&nbsp;이다 ) .<code>Nonces</code><code>x</code><code>secp256k1</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;우리의 경우&nbsp;<em>서명</em>&nbsp;&nbsp;값&nbsp; :<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>스크립트는&nbsp;&nbsp;<em>압축된 공개 키를</em>&nbsp;&nbsp;생성하여&nbsp;&nbsp;<code>RangeNonce</code>&nbsp;필요한&nbsp;&nbsp;<em>접두사를 추가했습니다.</em>&nbsp;<code>02</code><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>K_PUBKEY = 0283fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3>이제 정보가 있습니다.</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>비밀 키 범위</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>압축된 공개 키</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>소스 코드를 사용하여&nbsp;&nbsp;&nbsp;프랑스 개발자 Jean-Luc PONS의&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/06KangarooJeanLucPons" target="_blank" rel="noreferrer noopener"><strong>Pollard's Kangaroo 프로그램을 빌드해 봅시다.</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><em><u>계산 속도를</u></em></strong>&nbsp;&nbsp;높이기&nbsp;&nbsp;<code>CUDA</code>&nbsp;위해&nbsp;&nbsp;스스로 조립할 수 있습니다&nbsp; .<code>GPU</code><strong><em><u></u></em></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/afc/280/ae8/afc280ae86d3febb27f1008e8927ae89.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 CPU에 대한 정상적인 조립을 할 것입니다</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>팀:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/CryptoDeepTools/06KangarooJeanLucPons/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/394/ece/ecf/394eceecf11f26952a6fc87a10be2dbc.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt-get update</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2bc/e90/cd5/2bce90cd55b48787511363f9976adbd6.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt-get install g++ -y
sudo apt-get install libgmp3-dev libmpfr-dev -y</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/707/e19/0da/707e190da23fd6b83eead65bce771b5b.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>모든 패키지 설치 후 간단한 명령을 실행하여 빌드합니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>make</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/663/476/ae3/663476ae36f13e98d23f8ee3e879b545.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/1ea/932/dd2/1ea932dd2bd751c24fa95821c6833523.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>조립 성공!</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Проверим версию:

./kangaroo -v</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/76d/f52/532/76df5253202c44d068af867a812d11db.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>그래서 "캥거루 v2.2" 버전을 만들었습니다.</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>성능을 시연하기 위해&nbsp;&nbsp;<code>«Kangaroo v2.2»</code>&nbsp;범위&nbsp;&nbsp;<code>CPU</code>를 높이고 모든 것을 파일에 저장해 보겠습니다.&nbsp;<code>rangepubkey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>텍스트 파일 열기: rangepubkey.txt</h4>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8ac/477/f4c/8ac477f4c2423dc5ff4cce2407481540.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>070239c013e8f40c8c2a0e608ae15a6b23d4a09295be678b2100000000000000
070239c013e8f40c8c2a0e608ae15a6b23d4a09295be678b21ffffffffffffff
0283fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Очистим терминал командой:

clear</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>«Kangaroo v2.2»</code>&nbsp;결과를&nbsp;&nbsp;실행하면&nbsp; 자동으로&nbsp;&nbsp;파일에&nbsp;&nbsp;<em>저장 됩니다.</em><code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./kangaroo -ws -w save.work -wi 30 -o savenonce.txt rangepubkey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ae8/77a/6f4/ae877a6f49f7781d70cf6a986deea751.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5eb/0b2/2e3/5eb0b22e395bd62b5a577a37ba2bebef.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e2d/6a1/e3a/e2d6a1e3ab4cd4bb5be0c58eed1ca6f7.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>검색 시간은 1분이 소요되었습니다.&nbsp;18초</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>파일 결과:</em>&nbsp;<code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/76b/fb1/f4e/76bfb1f4e28f14cebba9b68c31e510ec.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em></em>&nbsp;파일을&nbsp;&nbsp;<em>열어봅시다 :</em><code>savenonce.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/50d/1fd/7ae/50d1fd7aecc8ea69cdb12d8f73830d8b.png" alt="Pollard의 Kangaroo는 알려진 범위에서 이산 로그 secp256k1 PRIVATE KEY + NONCES에 대한 솔루션을 찾습니다."/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>비밀 키를 얻었습니다. 이것이 "K"(NONCES)의 값입니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Key# 0 &#91;1S]Pub:  0x0283FE1C06236449B69A7BEE5BE422C067D02C4CE3F4FA3756BD92C632F971DE06 
       Priv: 0x70239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634 


070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634

K = 070239c013e8f40c8c2a0e608ae15a6b00000000000000000000000000000000 # RangeNonce
K = 070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634 # NONCES
K = 070239c013e8f40c8c2a0e608ae15a6bffffffffffffffffffffffffffffffff # RangeNonce</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>개인 키</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이제 값을 알고 있으므로&nbsp;&nbsp;<em><u>개인 키를</u></em>&nbsp;&nbsp;Bitcoin 주소:&nbsp;&nbsp;<a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong>14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</strong></a><code>"K" (NONCES)</code>&nbsp;로 복원 &nbsp;합니다&nbsp; .<em><u></u></em><a href="https://btc.exan.tech/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>우리가 기억하는 것처럼 처음으로 돌아가서 스크립트는&nbsp;&nbsp;값 범위에 대한&nbsp;&nbsp;<em>정보</em>&nbsp;와&nbsp;&nbsp;<em>정보를</em><code>«RangeNonce»</code>&nbsp;&nbsp;공개했습니다.&nbsp;<em></em><code>"K" (NONCES)</code><em></em>&nbsp;<code>SIGNATURES</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d71/0d3/fa1/d710d3fa1cf97ab16e33f7f824c2fb87.png" alt="서명" title="서명"/><figcaption class="wp-element-caption">서명</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06
S = 7405249d2aa9184b688f5307006fddc3bd4a7eb89294e3be3438636384d64ce7
Z = 070239c013e8f40c8c2a0e608ae15a6b1bb4b8fbcab3cff151a6e4e8e05e10b7</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>Python 스크립트</em>&nbsp;(&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py)</a>&nbsp;의 공식을 사용하여 개인 키를 가져옵니다.<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/calculate.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/getpro/habr/upload_files/b40/7d2/80e/b407d280edbe126f6ec21ac1c1ffa539.svg" alt="PRIVKEY = ((((S * K) - Z) * ​​modinv(R,N)) % N)"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def</strong> <strong>h</strong>(n):
    <strong>return</strong> hex(n).replace("0x","")

<strong>def</strong> <strong>extended_gcd</strong>(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    <strong>while</strong> remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    <strong>return</strong> lastremainder, lastx * (-1 <strong>if</strong> aa &lt; 0 <strong>else</strong> 1), lasty * (-1 <strong>if</strong> bb &lt; 0 <strong>else</strong> 1)

<strong>def</strong> <strong>modinv</strong>(a, m):
    g, x, y = extended_gcd(a, m)
    <strong>if</strong> g != 1:
        <strong>raise</strong> ValueError
    <strong>return</strong> x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141
R = 0x83fe1c06236449b69a7bee5be422c067d02c4ce3f4fa3756bd92c632f971de06
S = 0x7405249d2aa9184b688f5307006fddc3bd4a7eb89294e3be3438636384d64ce7
Z = 0x070239c013e8f40c8c2a0e608ae15a6b1bb4b8fbcab3cff151a6e4e8e05e10b7
K = 0x070239C013E8F40C8C2A0E608AE15A6B23D4A09295BE678B21A5F1DCEAE1F634

<strong>print</strong> (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>팀:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/02BreakECDSAcryptography/calculate.py

python3 calculate.py
</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/803/1f1/189/8031f11893dbb7de1d90858ae8ba634a.png" alt="PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b" title="PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b"/><figcaption class="wp-element-caption">PRIVKEY=23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE
WIF:  5J64pq77XjeacCezwmAr2V1s7snvvJkuAz8sENxw7xCkikceV6e
HEX:  23d4a09295be678b21a5f1dceae1f634a69c1b41775f680ebf8165266471401b</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/d8c/78d/8eb/d8c78d8eb14e5246b495e09f59631e44.png" alt="bitaddress 웹 사이트에서 개인 키 확인" title="bitaddress 웹 사이트에서 개인 키 확인"/><figcaption class="wp-element-caption">bitaddress 웹 사이트에서 개인 키 확인</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>개인 키를 찾았습니다!</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/ed9/7da/c1d/ed97dac1dc07e2bce09fe0951d9f64de.png" alt="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE" title="www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE"/><figcaption class="wp-element-caption">www.blockchain.com/btc/address/14NWDXkQwcGN1Pd9fboL8npVynD5SfyJAE</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;이 비디오는 암호 화폐의&nbsp;&nbsp;&nbsp;약한 서명에 대한&nbsp;&nbsp;&nbsp;타원 곡선의 데이터 및 암호화의 재정적 보안을 보장하기 위해&nbsp;&nbsp;<a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener"><strong>CRYPTO DEEP TECH</strong></a>&nbsp;포털용 으로 제작되었습니다.&nbsp;<code>secp256k1</code><code>ECDSA</code><code>BITCOIN</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/06KangarooJeanLucPons" target="_blank" rel="noreferrer noopener"><strong><u>원천</u></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>텔레그램:&nbsp;&nbsp;</strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"><strong>https://t.me/cryptodeeptech</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>영상자료 :&nbsp;&nbsp;<a href="https://youtu.be/UGUJyxOhBBQ" target="_blank" rel="noreferrer noopener">https://youtu.be/UGUJyxOhBBQ</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>출처:&nbsp;&nbsp;</strong><a href="https://cryptodeep.ru/kangaroo" target="_blank" rel="noreferrer noopener"><strong>https://cryptodeep.ru/kangaroo</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2402} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/03/010-1024x576.png" alt="Pollard's Kangaroo находим решения дискретного логарифма secp256k1 PRIVATE KEY + NONCES в известном диапазоне" class="wp-image-2402"/></figure>
<!-- /wp:image -->
