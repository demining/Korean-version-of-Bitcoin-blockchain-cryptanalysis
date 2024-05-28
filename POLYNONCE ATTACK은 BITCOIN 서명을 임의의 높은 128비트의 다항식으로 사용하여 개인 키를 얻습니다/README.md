# POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다.

<!-- wp:embed {"url":"https://www.youtube.com/embed/7nKs_KHtyn4","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/7nKs_KHtyn4
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeeptech.ru/blockchain-attack-vectors" target="_blank" rel="noreferrer noopener">이 기사에서는 "Bitcoin의 치명적인 취약점"</a></strong>&nbsp;이라는 주제를 다시 다루고&nbsp;2023년의 새로운 공격인&nbsp;<a href="https://cryptodeeptech.ru/polynonce-attack" target="_blank" rel="noreferrer noopener"><strong>"POLYNONCE ATTACK"을</strong></a>&nbsp;세 가지 예 모두에 사용할 것입니다 .&nbsp;<strong><a href="https://research.kudelskisecurity.com/2023/03/06/polynonce-a-tale-of-a-novel-ecdsa-attack-and-bitcoin-tears/" target="_blank" rel="noreferrer noopener">이 공격에 대한 첫 번째 언급은 "Kudelski Security"</a></strong>&nbsp;의 기사에 설명되어 있습니다&nbsp;.<strong><a href="https://cryptodeeptech.ru/blockchain-attack-vectors" target="_blank" rel="noreferrer noopener"></a></strong><a href="https://cryptodeeptech.ru/polynonce-attack" target="_blank" rel="noreferrer noopener"><strong></strong></a><strong><a href="https://research.kudelskisecurity.com/2023/03/06/polynonce-a-tale-of-a-novel-ecdsa-attack-and-bitcoin-tears/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2920} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-140-1024x309.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2920"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2921} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-141-1024x372.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2921"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2922} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-142-1024x498.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2922"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":3043,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-159-1024x403.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-3043"/><figcaption class="wp-element-caption"><a href="https://research.kudelskisecurity.com/2023/03/06/polynonce-a-tale-of-a-novel-ecdsa-attack-and-bitcoin-tears/" target="_blank" rel="noreferrer noopener"><code>https://research.kudelskisecurity.com/2023/03/06/polynonce-a-tale-of-a-novel-ecdsa-attack-and-bitcoin-tears/</code></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">실질적인 근거로 Hal Finney&nbsp;</a><a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA 및 BETA</a>&nbsp;의 secp256k1 곡선 값이&nbsp;비트코인 ​​타원 곡선의 불확실성 깊이를 숨기는 이전 기사&nbsp;<a href="https://cryptodeeptech.ru/endomorphism" target="_blank" rel="noreferrer noopener">"&nbsp;<strong>내형성으로 secp256k1 속도 향상"</strong></a>&nbsp;에서 자료를 가져옵니다 .<a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener"></a>&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>우리는 많은 것을 밝힐 수 있습니다<code>Binary number (4 digits):&nbsp;<strong>"1111"</strong>&nbsp;// Hex number<em>:&nbsp;</em><strong>"F"</strong><em>&nbsp;//</em></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2923,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-143.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2923"/><figcaption class="wp-element-caption"><a href="https://www.rapidtables.com/convert/number/hex-to-binary.html" target="_blank" rel="noreferrer noopener"><code>https://www.rapidtables.com/convert/number/hex-to-binary.html</code></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>우리는 또한 128비트로</strong>&nbsp;구성된&nbsp;<strong><a href="https://cryptodeep.ru/endomorphism/" target="_blank" rel="noreferrer noopener">secp256k1</a></strong>&nbsp;곡선 의 순서를 완벽하게 알고 있습니다.&nbsp;<em>이진수(4자리):&nbsp;</em><strong>"1111"&nbsp;</strong><em>// 16진수:&nbsp;</em><strong>"F"&nbsp;</strong><em>//</em><strong></strong><em></em><strong></strong><em></em><strong></strong><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>n = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:code -->
<pre class="wp-block-code"><code>1111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111010111010101011101101110011100110101011110100100010100000001110111011111111010010010111101000110011010000001101100100000101000001</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>우리는 임의로 높은 차수의 128비트 모듈로의 이진 코드에서 단위로서의 다항식을 봅니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2948} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-147-1024x521.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2948"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener"><code>Speed ​​up secp256k1 with endomorphism</code></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이 사실을 감안할 때 Bitcoin 개인 키의 초기 비트는&nbsp;<em>Binary 숫자(4자리):&nbsp;</em><strong>"1111"&nbsp;</strong><em>// Hex 숫자:&nbsp;</em><strong>"F"&nbsp;</strong><em>//</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">이론적으로 자료를 가져옵니다.</h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://attacksafe.ru/polynonce-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener">"비트코인에 대한 폴리논스 공격"</a></h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2940,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-146.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2940"/><figcaption class="wp-element-caption"><a href="https://attacksafe.ru/polynonce-attack-on-bitcoin" target="_blank" rel="noreferrer noopener"><code>https://attacksafe.ru/polynonce-attack-on-bitcoin</code></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>Bitcoin 주소의 예를 고려하십시오.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/address/1DxzwX4qC9PsWDSAzuWbJRzEwdGx3n9CJB" target="_blank" rel="noreferrer noopener"><strong>1DxzwX4qC9PsWDSAzuWbJRzEwdGx3n9CJB</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2699} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-44.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2699"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/929d565c386a279cf7a0382ba48cab1f72d62e7cfb3ab97b4f211d5673bc4441" target="_blank" rel="noreferrer noopener"><strong>929d565c386a279cf7a0382ba48cab1f72d62e7cfb3ab97b4f211d5673bc4441</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2700} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-45-1024x200.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2700"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2792} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-85-1024x364.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2792"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>02000000019e3de154f8b473a796b9e39dd279dff1d907a4d27a1d8b23a055f97b08ad4c6e310000006b483045022100b29bdfc27ddf6bebd0e77c84b31dc1bc64b5b2276c8d4147421e96ef85467e8d02204ddd8ff0ffa19658e3b417be5f64d9c425a4d9fcd76238b8538c1d605b229baf0121027b06fe78e39ced37586c42c9ac38d7b2d88ccdd4cd1bb38816c0933f9b8db695ffffffff0169020000000000001600145fc8e854994406f93ea5c7f3abccc5d319ae2a3100000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>공식 웹사이트로 이동합니다:&nbsp;&nbsp;<strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">https://colab.research.google.com</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><strong>"노트북 업로드"&nbsp;</strong><em>옵션을 선택합니다.&nbsp;</em><strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2709} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-50.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2709"/></figure>
<!-- /wp:image --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><em>파일 다운로드:&nbsp;&nbsp;</em><strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/POLYNONCE_ATTACK.ipynb" target="_blank" rel="noreferrer noopener">POLYNONCE_ATTACK.ipynb</a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2711} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-52.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2711"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>HEX</code>유틸리티를 통해 -data를&nbsp;로드&nbsp;<code>echo</code>&nbsp;하고 파일에 저장:&nbsp;<strong>RawTX.txt</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!echo '02000000019e3de154f8b473a796b9e39dd279dff1d907a4d27a1d8b23a055f97b08ad4c6e310000006b483045022100b29bdfc27ddf6bebd0e77c84b31dc1bc64b5b2276c8d4147421e96ef85467e8d02204ddd8ff0ffa19658e3b417be5f64d9c425a4d9fcd76238b8538c1d605b229baf0121027b06fe78e39ced37586c42c9ac38d7b2d88ccdd4cd1bb38816c0933f9b8db695ffffffff0169020000000000001600145fc8e854994406f93ea5c7f3abccc5d319ae2a3100000000' &gt; RawTX.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2716} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-53.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2716"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>공격을 구현하기 위해 소프트웨어를 사용합니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;<strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener">공격에 안전한 소프트웨어</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":705,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-14.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-705"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/software</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">액세스 권한:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!chmod +x attacksafe</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2717} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-54.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2717"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">애플리케이션:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -help</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2720} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-57-1024x784.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2720"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>  -version:  software version 
  -list:     list of bitcoin attacks
  -tool:     indicate the attack
  -gpu:      enable gpu
  -time:     work timeout
  -server:   server mode
  -port:     server port
  -open:     open file
  -save:     save file
  -search:   vulnerability search
  -stop:     stop at mode
  -max:      maximum quantity in mode
  -min:      minimum quantity per mode
  -speed:    boost speed for mode
  -range:    specific range
  -crack:    crack mode
  -field:    starting field
  -point:    starting point
  -inject:   injection regimen
  -decode:   decoding mode</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2724} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-60.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2724"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Version 5.3.3. &#91;ATTACKSAFE SOFTWARE, © 2023]</code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>"ATTACKSAFE SOFTWARE"</code>&nbsp;Bitcoin에 대한 모든 대중적인 공격을 포함합니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading -->
<h2 class="wp-block-heading">모든 공격 목록을 실행해 보겠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -list</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2728} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-62-1024x758.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2728"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>선택하자<code>&nbsp;-tool: polynonce_attack</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>서명에 대한 특정&nbsp;<code>HEX</code>값을&nbsp;얻기 위해 이전에&nbsp;&nbsp;유틸리티를 통해 텍스트 문서에&nbsp;데이터를 추가&nbsp;&nbsp;하고 파일로 저장했습니다.&nbsp;<code>&nbsp;R,S,Z</code><code>ECDSA</code><code>RawTX</code><code>echo</code><code>RawTX.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>02000000019e3de154f8b473a796b9e39dd279dff1d907a4d27a1d8b23a055f97b08ad4c6e310000006b483045022100b29bdfc27ddf6bebd0e77c84b31dc1bc64b5b2276c8d4147421e96ef85467e8d02204ddd8ff0ffa19658e3b417be5f64d9c425a4d9fcd76238b8538c1d605b229baf0121027b06fe78e39ced37586c42c9ac38d7b2d88ccdd4cd1bb38816c0933f9b8db695ffffffff0169020000000000001600145fc8e854994406f93ea5c7f3abccc5d319ae2a3100000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code>-tool polynonce_attack</code>&nbsp;소프트웨어를 사용하여&nbsp;&nbsp;실행&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -tool polynonce_attack -open RawTX.txt -save SignatureRSZ.csv</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2734} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-64-1024x182.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2734"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;&nbsp;<code>-tool polynonce_attack</code>&nbsp;그 결과는 파일에 저장되었습니다.&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2736} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-65-1024x179.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2736"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>파일에서 비트코인 ​​지갑에 대한 개인 키를 계산하기 위해&nbsp;&nbsp;<strong><a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab/" target="_blank" rel="noreferrer noopener">SageMath를</a></strong><code>SignatureRSZ.csv</code>&nbsp;설치합니다 .<strong><a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-27.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2188"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2189} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-28-1024x445.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2189"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab/" target="_blank" rel="noreferrer noopener">이전에 기사를</a>&nbsp;게시했습니다&nbsp;. 다운로드&nbsp;&nbsp;<code>tar-file</code>:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2" target="_blank" rel="noreferrer noopener"><strong>sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2
!tar -xf sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2744} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-67-1024x319.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2744"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>다음 디렉토리를 살펴보겠습니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd SageMath/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2746} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-68-1024x723.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2746"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;다음 명령으로&nbsp;</em><strong>relocate-once.py를&nbsp;</strong><em>실행합니다&nbsp; .</em><code>Python-script:</code><em>&nbsp;</em><strong></strong><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!python3 relocate-once.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2750} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-69-1024x457.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2750"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>폴더&nbsp;<code>"AttackSafe"</code>로&nbsp;이동<code>"SignatureRSZ.csv"</code><code>"SageMath"</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!mv '/content/attacksafe' '/content/SageMath/attacksafe'
!mv '/content/SignatureRSZ.csv' '/content/SageMath/SignatureRSZ.csv'</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2753} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-70-1024x698.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2753"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3024} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-156-1024x344.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-3024"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>유틸리티를 통해 Dario Clavijo에서&nbsp;&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">crack_weak_ECDSA_nonces_with_LLL.py</a></strong>&nbsp;스크립트를 다운로드합니다.<code>wget</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://raw.githubusercontent.com/demining/CryptoDeepTools/main/20PolynonceAttack/crack_weak_ECDSA_nonces_with_LLL.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2756} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-72-1024x424.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2756"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;이제 다음 명령을&nbsp;</em><em>실행해 보겠습니다&nbsp; .</em><code>SageMath</code><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2760} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-74-1024x505.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2760"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>비트코인 지갑에 대한 개인 키를 계산하려면&nbsp;매개변수를 지정하는&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">crack_weak_ECDSA_nonces_with_LLL.py 스크립트를 실행하십시오.</a></strong><strong><code>128 bits 4 sign</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 crack_weak_ECDSA_nonces_with_LLL.py SignatureRSZ.csv 128 4 &gt; PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2766} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-75-1024x442.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2766"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>파일을 열어봅시다:<code>PrivateKey.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em><code>HEX</code>Bitcoin Wallet의 개인 키를 형식&nbsp;으로 받았습니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2769} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-78.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2769"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>PrivKey = 0xf0a3e31646ce147bbd79bb6e45e6e9c8c4e51c535918c9b4cdca9528eb62172d</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">각 ECDSA 서명에 대한 POLYNONCE 확인</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이렇게 하려면&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example1/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><strong>GITHUB 의 코드를 사용하세요.</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2972,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-150.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2972"/><figcaption class="wp-element-caption"><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example1/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><code>https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example1/POLYNONCE.py</code></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">결과:</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2963} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-149.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2963"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>4개의 동일한 이니셜을 받았습니다.<code>128 bits</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>POLYNONCE &gt;&gt; 93e43392cb31d5d1f75175ee64ce16b7 efc86216627af576c29c9c52a0fd10fe
POLYNONCE &gt;&gt; 93e43392cb31d5d1f75175ee64ce16b7 f88ff4c8a9ea4b61b1e087d0c0988826
POLYNONCE &gt;&gt; 93e43392cb31d5d1f75175ee64ce16b7 6849e83cd03d103bcc37aca8323c8d2f
POLYNONCE &gt;&gt; 93e43392cb31d5d1f75175ee64ce16b7 efc86216627af576c29c9c52a0fd10fe</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">Hal Finney&nbsp;</a>&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA 및 BETA</a>&nbsp;의 secp256k1 곡선 값 덕분에&nbsp;&nbsp;<code>128 bits</code>비트코인 ​​지갑에 대한 개인 키의 초기 비트&nbsp;가<em><code>Binary number (4 digits):&nbsp;</code></em><strong><code>"1111"</code></strong><em><code>&nbsp;// Hex number:&nbsp;</code></em><strong><code>"F"</code></strong><em><code>&nbsp;//</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">개인 키의 HEX를 확인합시다.</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>모듈 설치<code>bitcoin</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!pip3 install bitcoin</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2799} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-86-1024x219.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2799"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>코드를 실행해 봅시다:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from bitcoin import *

with open("PrivateKey.txt","r") as f:
    content = f.readlines()

content = &#91;x.strip() for x in content]
f.close()


outfile = open("PrivateKeyAddr.txt","w")
for x in content:
  outfile.write(x+":"+pubtoaddr(encode_pubkey(privtopub(x), "bin_compressed"))+"\n")
 
outfile.close()</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2800} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-87.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2800"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>파일을 열어봅시다:<code>PrivateKeyAddr.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2801} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-88.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2801"/><figcaption class="wp-element-caption"><code>f0a3e31646ce147bbd79bb6e45e6e9c8c4e51c535918c9b4cdca9528eb62172d:1DxzwX4qC9PsWDSAzuWbJRzEwdGx3n9CJB</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;&nbsp;&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1DxzwX4qC9PsWDSAzuWbJRzEwdGx3n9CJB
WIF:  L5HV2GiosXifcmijGCpFWdYiMRuXh4x4JVK29urGjfAWyasBYoDX
HEX:  f0a3e31646ce147bbd79bb6e45e6e9c8c4e51c535918c9b4cdca9528eb62172d</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2779} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-bitaddress.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2779"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/1DxzwX4qC9PsWDSAzuWbJRzEwdGx3n9CJB"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/1DxzwX4qC9PsWDSAzuWbJRzEwdGx3n9CJB
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2853} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-106.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2853"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2859} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-110.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2859"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2864} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-113-1024x217.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2864"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 3699.40</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">다른 예를 살펴보겠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>№<strong>2</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>Bitcoin 주소가 있는 예제 #2를 고려하십시오.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/137a6fqt13bhtAkGZWrgcGM98NLCotszR2" target="_blank" rel="noreferrer noopener">137a6fqt13bhtAkGZWrgcGM98NLCotszR2</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2788} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-82.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2788"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/c1da9d117e15883ba41539f558ac870f53865ea00f68a8ff8bc7e8a9ee67099b" target="_blank" rel="noreferrer noopener"><strong>c1da9d117e15883ba41539f558ac870f53865ea00f68a8ff8bc7e8a9ee67099b</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2789} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-83-1024x193.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2789"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2790} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-84-1024x363.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2790"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>010000000103ebc5c4b817124d45ad15e398ec32e9b9b7549c1fc10300ecbf36648c3cb5d42c0000006a47304402204e97dae0ab6e4eee9529f68687907c05db9037d9fbdba78dd01a3338a48d95b602207794cb7aa308243dfbdd5c20225777cd6e01bd7c4f76bf36948aa29290129c2b0121036360352efcff6a823eabb25578a29392eab4d302955fd54ece900578d2ab83b8ffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>첫 번째 예에서 파일을 제거해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!rm RawTX.txt
!rm NoncesHEX.txt
!rm PrivateKey.txt
!rm SignatureRSZ.csv
!rm PrivateKeyAddr.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3027} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-157.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-3027"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><code>HEX</code><em>유틸리티를 통해 -data를&nbsp;&nbsp;</em><em>로드&nbsp;&nbsp;</em><code>echo</code><em>&nbsp;하고 파일에 저장:&nbsp;&nbsp;</em><strong>RawTX.txt</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!echo '010000000103ebc5c4b817124d45ad15e398ec32e9b9b7549c1fc10300ecbf36648c3cb5d42c0000006a47304402204e97dae0ab6e4eee9529f68687907c05db9037d9fbdba78dd01a3338a48d95b602207794cb7aa308243dfbdd5c20225777cd6e01bd7c4f76bf36948aa29290129c2b0121036360352efcff6a823eabb25578a29392eab4d302955fd54ece900578d2ab83b8ffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000' &gt; RawTX.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2820} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-94-1024x393.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2820"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code>-tool polynonce_attack</code>&nbsp;소프트웨어를 사용하여&nbsp;&nbsp;실행&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -tool polynonce_attack -open RawTX.txt -save SignatureRSZ.csv</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2825} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-95-1024x248.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2825"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;&nbsp;<code>-tool polynonce_attack</code>&nbsp;그 결과는 파일에 저장되었습니다.&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2830} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-96-1024x177.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2830"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;다음 명령을&nbsp;</em><em>실행해 보겠습니다&nbsp; .</em><code>SageMath</code><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2837} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-98-1024x494.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2837"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>비트코인 지갑에 대한 개인 키를 계산하려면&nbsp;&nbsp;&nbsp;매개변수를 지정하는&nbsp;&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">crack_weak_ECDSA_nonces_with_LLL.py 스크립트를 실행하십시오.</a></strong><strong><code>128 bits 4 sign</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 crack_weak_ECDSA_nonces_with_LLL.py SignatureRSZ.csv 128 4 &gt; PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2841} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-99-1024x530.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2841"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>파일을 열어봅시다:&nbsp;<code>PrivateKey.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em><code>HEX</code>&nbsp;Bitcoin Wallet의 개인 키를 형식&nbsp;으로 받았습니다.&nbsp;</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2847} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-102.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2847"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>PrivKey = 0xff0178fa717374f7e74d43f00150748967ea04b64241ec10a10f62debb70868c</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">각 ECDSA 서명에 대한 POLYNONCE 확인</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이렇게 하려면&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example2/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><strong>GITHUB 의 코드를 사용하세요.</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2991,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-152.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2991"/><figcaption class="wp-element-caption"><code><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example2/POLYNONCE.py" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example2/POLYNONCE.py</a></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">결과:</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2993} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-153.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2993"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>4개의 동일한 이니셜을 받았습니다.<code>128 bits</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>POLYNONCE &gt;&gt; 5220dae0c281e1115b4dd69ea3500f70 c5f6da6334586ed2bdc88a05f37bcf95
POLYNONCE &gt;&gt; 5220dae0c281e1115b4dd69ea3500f70 6f82fbd847c138ab48e778135e908149
POLYNONCE &gt;&gt; 5220dae0c281e1115b4dd69ea3500f70 5541022f8aeac81e5ce62e018d1cd722
POLYNONCE &gt;&gt; 5220dae0c281e1115b4dd69ea3500f70 80e88efaff419ecd84d7ded17dc548a7</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">Hal Finney&nbsp;</a>&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA 및 BETA</a>&nbsp;의 secp256k1 곡선 값 덕분에&nbsp;&nbsp;<code>128 bits</code>비트코인 ​​지갑에 대한 개인 키의 초기 비트&nbsp;가<em><code>Binary number (4 digits):&nbsp;</code></em><strong><code>"1111"</code></strong><em><code>&nbsp;// Hex number:&nbsp;</code></em><strong><code>"F"</code></strong><em><code>&nbsp;//</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">개인 키의 HEX를 확인합시다.</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>코드를 실행해 봅시다:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from bitcoin import *

with open("PrivateKey.txt","r") as f:
    content = f.readlines()

content = &#91;x.strip() for x in content]
f.close()


outfile = open("PrivateKeyAddr.txt","w")
for x in content:
  outfile.write(x+":"+pubtoaddr(encode_pubkey(privtopub(x), "bin_compressed"))+"\n")
 
outfile.close()</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2848} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-103-1024x451.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2848"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>파일을 열어봅시다:&nbsp;<code>PrivateKeyAddr.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2850} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-104.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2850"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;&nbsp;&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 137a6fqt13bhtAkGZWrgcGM98NLCotszR2
WIF:  L5mQfFuzR3rzLtneJ7Tcv64JrHjCpK64UN4JRdGDxCUTbQ8NfHxo
HEX:  ff0178fa717374f7e74d43f00150748967ea04b64241ec10a10f62debb70868c</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2877} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-bitaddress-2.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2877"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/137a6fqt13bhtAkGZWrgcGM98NLCotszR2"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/137a6fqt13bhtAkGZWrgcGM98NLCotszR2
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2867} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-114.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2867"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2870} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-116.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2870"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2871} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-117-1024x199.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2871"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 1133.73</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">다른 예를 살펴보겠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>№<strong>3</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>Bitcoin 주소가 있는 예제 #3을 고려하십시오.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1HxrEeC2X8UEcSvsemPJtTqrnbAetGWYUt" target="_blank" rel="noreferrer noopener">1HxrEeC2X8UEcSvsemPJtTqrnbAetGWYut</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2883} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-119.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2883"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/tx/fa80af660fc444d87853137506df02e5c75e8c2bf75dc44589b60356867a6d98" target="_blank" rel="noreferrer noopener"><strong>fa80af660fc444d87853137506df02e5c75e8c2bf75dc44589b60356867a6d98</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2884} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-120-1024x193.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2884"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">RawTX</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2885} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-121-1024x353.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2885"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>01000000016eb80d35b08164302e49f88d8f86bf2827a91a5650149be38f4f73751ff41437060000006a473044022043d4c025a0f3be366a0d768c721b9b9191e0c3db6f2c6bfe34e8fb24af7f379102205a4fe2cc6944e00309c35619ff1242301b84d4728b863f97326f56dbd7a782220121027ccccf5f56ed78c2a761721ff3da0f76b792fbe4eae2ac73e7b4651bc3ef19cdffffffff01c057010000000000232103bec42e5d718b0e5b3853243c9bcf00dd671a335b0eb99fd8ca32f8d5784a9476ac00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>두 번째 예에서 파일을 제거해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!rm RawTX.txt
!rm NoncesHEX.txt
!rm PrivateKey.txt
!rm SignatureRSZ.csv
!rm PrivateKeyAddr.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3030} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-158.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-3030"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><code>HEX</code><em>유틸리티를 통해 -data를&nbsp;&nbsp;</em><em>로드&nbsp;&nbsp;</em><code>echo</code><em>&nbsp;하고 파일에 저장:&nbsp;&nbsp;</em><strong>RawTX.txt</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!echo '01000000016eb80d35b08164302e49f88d8f86bf2827a91a5650149be38f4f73751ff41437060000006a473044022043d4c025a0f3be366a0d768c721b9b9191e0c3db6f2c6bfe34e8fb24af7f379102205a4fe2cc6944e00309c35619ff1242301b84d4728b863f97326f56dbd7a782220121027ccccf5f56ed78c2a761721ff3da0f76b792fbe4eae2ac73e7b4651bc3ef19cdffffffff01c057010000000000232103bec42e5d718b0e5b3853243c9bcf00dd671a335b0eb99fd8ca32f8d5784a9476ac00000000' &gt; RawTX.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2889} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-124-1024x468.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2889"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code>-tool polynonce_attack</code>&nbsp;소프트웨어를 사용하여&nbsp;&nbsp;실행&nbsp;<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./attacksafe -tool polynonce_attack -open RawTX.txt -save SignatureRSZ.csv</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2890} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-125-1024x252.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2890"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;&nbsp;<code>-tool polynonce_attack</code>&nbsp;그 결과는 파일에 저장되었습니다.&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.&nbsp;<code>SignatureRSZ.csv</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2892} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-127-1024x184.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2892"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><em>&nbsp;다음 명령을&nbsp;</em><em>실행해 보겠습니다&nbsp; .</em><code>SageMath</code><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2837} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-98-1024x494.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2837"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>비트코인 지갑에 대한 개인 키를 계산하려면&nbsp;&nbsp;&nbsp;매개변수를 지정하는&nbsp;&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/crack_weak_ECDSA_nonces_with_LLL.py" target="_blank" rel="noreferrer noopener">crack_weak_ECDSA_nonces_with_LLL.py 스크립트를 실행하십시오.</a></strong><strong><code>128 bits 4 sign</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 crack_weak_ECDSA_nonces_with_LLL.py SignatureRSZ.csv 128 4 &gt; PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat PrivateKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2896} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-131-1024x530.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2896"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>파일을 열어봅시다:&nbsp;<code>PrivateKey.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><em><code>HEX</code>&nbsp;Bitcoin Wallet의 개인 키를 형식&nbsp;으로 받았습니다.&nbsp;</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":2898} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-132.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2898"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>PrivKey = 0xfbc50a7158b3d9fd7fd58fe0874f20c10c650975dc118163debf442a44203fdf</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">각 ECDSA 서명에 대한 POLYNONCE 확인</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이렇게 하려면&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example3/POLYNONCE.py" target="_blank" rel="noreferrer noopener">GITHUB 의 코드를 사용하세요.</a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2998,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-155.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2998"/><figcaption class="wp-element-caption"><a href="https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example3/POLYNONCE.py" target="_blank" rel="noreferrer noopener"><code>https://github.com/demining/CryptoDeepTools/blob/main/20PolynonceAttack/example3/POLYNONCE.py</code></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading">결과:</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":2997} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-154.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2997"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>4개의 동일한 이니셜을 받았습니다.<code>128 bits</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>POLYNONCE &gt;&gt; d7460c5b1a98f6d0443ae1cfe1f17814 fbc50a7158b3d9fd7fd58fe0874f20c1
POLYNONCE &gt;&gt; d7460c5b1a98f6d0443ae1cfe1f17814 d4de8d539655ecf0d50fd32187c3c467
POLYNONCE &gt;&gt; d7460c5b1a98f6d0443ae1cfe1f17814 6726aea1a6fd64d82dc657670352de72
POLYNONCE &gt;&gt; d7460c5b1a98f6d0443ae1cfe1f17814 89df16fd387156b39adca9a92464de18</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://en.wikipedia.org/wiki/Hal_Finney_(computer_scientist)" target="_blank" rel="noreferrer noopener">Hal Finney&nbsp;</a>&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/endomorphism/" target="_blank" rel="noreferrer noopener">LAMBDA 및 BETA</a>&nbsp;의 secp256k1 곡선 값 덕분에&nbsp;&nbsp;<code>128 bits</code>비트코인 ​​지갑에 대한 개인 키의 초기 비트&nbsp;가<em><code>Binary number (4 digits):&nbsp;</code></em><strong><code>"1111"</code></strong><em><code>&nbsp;// Hex number:&nbsp;</code></em><strong><code>"F"</code></strong><em><code>&nbsp;//</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">개인 키의 HEX를 확인합시다.</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>코드를 실행해 봅시다:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>from bitcoin import *

with open("PrivateKey.txt","r") as f:
    content = f.readlines()

content = &#91;x.strip() for x in content]
f.close()


outfile = open("PrivateKeyAddr.txt","w")
for x in content:
  outfile.write(x+":"+pubtoaddr(encode_pubkey(privtopub(x), "bin_compressed"))+"\n")
 
outfile.close()</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2848} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-103-1024x451.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2848"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>파일을 열어봅시다:&nbsp;<code>PrivateKeyAddr.txt</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":2900} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-133.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2900"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;&nbsp;&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1HxrEeC2X8UEcSvsemPJtTqrnbAetGWYUt
WIF:  L5f7p5bReuXLm3d7rFkpPyGQ1GNpiGuj8QuQ6rNCKXC9bs3J9GEY
HEX:  fbc50a7158b3d9fd7fd58fe0874f20c10c650975dc118163debf442a44203fdf</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2906} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-bitaddress-3.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2906"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/1HxrEeC2X8UEcSvsemPJtTqrnbAetGWYUt"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/1HxrEeC2X8UEcSvsemPJtTqrnbAetGWYUt
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2909} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-137.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2909"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2910} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-138.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2910"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2911} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-139-1024x224.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2911"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 459.24</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">문학:</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>ECDSA에 대한 새로운 관련 Nonce 공격,&nbsp;<a href="https://www.researchgate.net/profile/Marco-Macchetti" target="_blank" rel="noreferrer noopener">Marco Macchetti&nbsp;</a><strong>[Kudelski Security, 스위스](2023)</strong></em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>Gallant, Robert P., Robert J. Lambert, Scott A. Wanston.&nbsp;</em><strong><em>"효율적인 엔도모피즘으로 타원 곡선에서 더 빠른 점 곱셈"</em></strong><em>&nbsp;&nbsp;.&nbsp;연례 암호학 국제 회의, pp.&nbsp;190–200.&nbsp;스프링거, 베를린, 하이델베르크, (2001)</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>Hankerson, Darrell, Alfred J. Menezes 및 Scott Wanston.&nbsp;</em><strong><em>"타원 곡선 암호화에 대한 가이드"</em></strong><em>&nbsp;&nbsp;.&nbsp;컴퓨터 리뷰 46, 아니오.&nbsp;1 (2005)</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>할 피니.&nbsp;bitcointalk –&nbsp;&nbsp;&nbsp;</em><strong><em>“서명 검증 가속화”</em></strong><em>&nbsp;&nbsp;.&nbsp;(2011)&nbsp;&nbsp;</em>&nbsp;<a href="https://bitcointalk.org/index.php?topic=3238.0" target="_blank" rel="noreferrer noopener">https://bitcointalk.org/index.php?topic=3238.0</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>Blahut, Richard E.&nbsp;&nbsp;&nbsp;</em><strong><em>"암호화 및 보안 통신"</em></strong><em>&nbsp;&nbsp;.&nbsp;캠브리지 대학 출판부, (2014)</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/20PolynonceAttack" target="_blank" rel="noreferrer noopener">원천</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/software" target="_blank" rel="noreferrer noopener">공격에 안전한 소프트웨어</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">텔레그램: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/7nKs_KHtyn4" target="_blank" rel="noreferrer noopener">동영상: https://youtu.be/7nKs_KHtyn4</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/polynonce-attack" target="_blank" rel="noreferrer noopener">출처: https://cryptodeep.ru/polynonce-attack</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2915} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/038-1024x576.png" alt="POLYNONCE ATTACK은 BITCOIN 서명을 임의의 높은 128비트의 다항식으로 사용하여 개인 키를 얻습니다." class="wp-image-2915"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
