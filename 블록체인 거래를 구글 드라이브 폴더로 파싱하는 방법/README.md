<!-- wp:embed {"url":"https://www.youtube.com/embed/ECAPypsmMQs","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ECAPypsmMQs
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>이 기사에서는 비트코인 ​​트랜잭션을 분석하고 블록체인 네트워크에서 Google 드라이브 폴더로 RawTX를 매우 빠르게 구문 분석하는 방법을 배웁니다. 이 모든 것이 비트코인 ​​트랜잭션이 작동하는 방식과 블록체인 네트워크에 있는 모든 내용을 더 잘 이해하는 데 도움이 됩니다.<br>먼저 모든 비트코인 ​​거래가 [txid]에 저장된다는 것을 알아야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>txid</strong>&nbsp;&nbsp;는 비트코인 ​​블록체인에 저장된 트랜잭션 ID이고, RawTX는 이중 해시 형태로 저장됩니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>이는 RawTX가 블록체인에서 볼 수 있는 트랜잭션 해시를 얻기 위해 SHA256 알고리즘을 두 번 통과했음을 의미합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>예를 들어 다음 해시가 있는 트랜잭션:&nbsp;&nbsp;<a href="https://www.blockchain.com/btc/tx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f" target="_blank" rel="noreferrer noopener">d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>비트코인 블록체인의 트랜잭션은 이중 해시 형식으로 저장됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>SHA256(SHA256(0100000001f2068914e2fea859cacd8df990daf4008f11296b3cb953794051147a265d850a000000008b483045022043784344e1e0cb498c1d73b4cee970fb0f9adf38b7891d0b1310fdb9cbc23929022100a734f4e97a05bd169a9f0eb296fc841fa57f8753db09869f8f6f8cc1232616d4014104d6597d465408e6e11264c116dd98b539740e802dc756d7eb88741696e20dfe7d3588695d2e7ad23cbf0aa056d42afada63036d66a1d9b97070dd6bc0c87ceb0dffffffff0100b864d9450000001976a9142df31a60b02cce392822c9a87198753578ef7de888ac00000000) = d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>RawTX를 얻으려면 트랜잭션 ID [txid]를 입력하기만 하면 됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://blockchain.info/rawtx/[txid]?format=hex">https://blockchain.info/rawtx/[txid]?format=hex</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또한 우리는 HEX 형식으로 정보를 받을 것입니다. 이것은 우리가 소중히 여기는 RawTX입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://blockchain.info/rawtx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f?format=hex">https://blockchain.info/rawtx/d76641afb4d0cc648a2f74db09f86ea264498341c49434a933ba8eef9352ab6f?format=hex</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그러나 우리가 알고 있듯이 하나의 비트코인 ​​주소에 많은 트랜잭션[txid]이 있을 수 있으며 이것이 주요 문제입니다. 찾는 데 많은 시간이 걸리고 PC를 로드하며 많은 디스크 공간을 차지합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 문제를 해결하려면&nbsp;&nbsp;<strong><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">https://chain.so/api/</a></strong><code>API</code>&nbsp;&nbsp;사이트를&nbsp; 사용하십시오.<strong><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>따라서 bash 스크립트에서 하나의 비트코인 ​​주소를 지정합니다.&nbsp;&nbsp;<code>getrawtx.sh «address»</code>&nbsp;그런 다음 전체 이전 출력 해시를 추출합니다. 모든 입력은 출력을 참조합니다.&nbsp;<code>(UTXO)</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>UTXO는</strong>&nbsp;&nbsp;새 입력에 사용될&nbsp;&nbsp;<em>(사용되지 않은 트랜잭션 출력)</em>&nbsp;&nbsp;입니다&nbsp; .&nbsp;<em>이것의 해시 값은&nbsp;&nbsp;</em><code>UTXO</code><em>&nbsp;역순으로 저장됩니다.</em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>결과적으로 사용되지 않은 모든 트랜잭션 출력은 파일에 저장됩니다.&nbsp;<code>«RawTX.json»</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>RawTX</code>&nbsp;Bitcoin 주소를&nbsp;&nbsp;얻으려면&nbsp;&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/blob/main/01BlockchainGoogleDrive/getrawtx.sh" target="_blank" rel="noreferrer noopener">Bash 스크립트를 사용하십시오: getrawtx.sh</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/7e4/268/a3a/7e4268a3ab7e36fc45020c6b222b7611.png" alt="구글 드라이브에서 블록체인 파싱" title="구글 드라이브에서 블록체인 파싱"/><figcaption class="wp-element-caption">구글 드라이브에서 블록체인 파싱</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>Google 드라이브 폴더로 파싱하는 방법은 무엇입니까?</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이렇게 하려면 Google Colab용 터미널&nbsp;&nbsp;<strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab] 을 사용할 수 있습니다.</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이전에 비디오 자습서를 녹화했습니다.&nbsp;&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener">"GITHUB에서 작업하기 위한 모든 편의를 만드는 Google Colab의 터미널"</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Bash 스크립트가 어떻게 작동하는지 자세히 살펴보겠습니다. getrawtx.sh</h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/060/833/01b/06083301bd4339d46a9a62e3d8bd606c.png" alt="Bash 스크립트: getrawtx.sh" title="Bash 스크립트: getrawtx.sh"/><figcaption class="wp-element-caption">Bash 스크립트: getrawtx.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code>./getrawtx.sh 12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>Bitcoin 유틸리티</em>&nbsp;명령 에 지정하는 주소&nbsp;<em></em>&nbsp;<code>wget</code></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b68/785/9f6/b687859f62fd52efdfe6b536cf3040be.png" alt="블록체인 거래를 구글 드라이브 폴더로 파싱하는 방법"/></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/338/b5b/10e/338b5b10ebb67a28ce79bcabb7ed4925.png" alt="모든 콘텐츠는 파일에 저장됩니다: index.json" title="모든 콘텐츠는 파일에 저장됩니다: index.json"/><figcaption class="wp-element-caption">모든 콘텐츠는 파일에 저장됩니다: index.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://chain.so/api/v2/get_tx_spent/BTC/12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr">https://chain.so/api/v2/get_tx_spent/BTC/12ib7dApVFvg82TXKycWBNpN8kFyiAN1dr</a></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/073/505/252/07350525294fb491a864ca1d19c4c0f5.png" alt="grep 유틸리티는 모든 &quot;txid&quot; 트랜잭션 ID를 하나의 공통 index2.json 파일에 저장합니다.  " title="grep 유틸리티는 모든 &quot;txid&quot; 트랜잭션 ID를 하나의 공통 index2.json 파일에 저장합니다.  "/><figcaption class="wp-element-caption">grep 유틸리티는 모든 트랜잭션 ID "txid"를 하나의 공통 파일 index2.json에 저장합니다.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/b0e/fa6/edb/b0efa6edbf242f2f6f70bc1cc8b87640.png" alt="모든 콘텐츠는 다음 파일에 저장됩니다: index2.json" title="모든 콘텐츠는 다음 파일에 저장됩니다: index2.json"/><figcaption class="wp-element-caption">모든 콘텐츠는 다음 파일에 저장됩니다: index2.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/4cb/904/b7a/4cb904b7a36460710dd6d51679c8317f.png" alt="index.json 삭제" title="index.json 삭제"/><figcaption class="wp-element-caption">index.json 삭제</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/395/b95/c44/395b95c44bc13e60cbc0abb38c38108b.png" alt="sed 유틸리티를 사용하여 &quot;txid&quot; 접두어와 따옴표 쉼표를 제거합니다." title="sed 유틸리티를 사용하여 &quot;txid&quot; 접두어와 따옴표 쉼표를 제거합니다."/><figcaption class="wp-element-caption">sed 유틸리티를 사용하여 "txid" 접두어와 따옴표 쉼표를 제거합니다.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/951/b67/986/951b6798689d0b357259abf07e711b5a.png" alt="파일의 최종 결과: index2.json" title="파일의 최종 결과: index2.json"/><figcaption class="wp-element-caption">파일의 최종 결과: index2.json</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/375/856/5cf/3758565cfb656de3fcc0069574fbd93c.png" alt="Echo 유틸리티를 사용하여 Python 스크립트 만들기" title="Echo 유틸리티를 사용하여 Python 스크립트 만들기"/><figcaption class="wp-element-caption">Echo 유틸리티를 사용하여 Python 스크립트 만들기</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/9f0/a0f/a55/9f0a0fa556623a5c9e436c0f0c118161.png" alt="Python 스크립트 fileopen.py 실행" title="Python 스크립트 fileopen.py 실행"/><figcaption class="wp-element-caption">Python 스크립트 fileopen.py 실행</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/8cf/23f/c9c/8cf23fc9ce47c1fc907eb723b13c7c23.png" alt="Python 스크립트 fileopen.py를 실행한 후 Bash 스크립트 rawscript.sh가 생성됩니다." title="Python 스크립트 fileopen.py를 실행한 후 Bash 스크립트 rawscript.sh가 생성됩니다."/><figcaption class="wp-element-caption">Python 스크립트 fileopen.py를 실행한 후 Bash 스크립트 rawscript.sh가 생성됩니다.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/35a/f1b/200/35af1b20063d6255c73c95b6628cd111.png" alt="index2.json 삭제" title="index2.json 삭제"/><figcaption class="wp-element-caption">index2.json 삭제</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e63/b09/091/e63b090910e9e2e08d47b61d0ceb065c.png" alt="Bash 스크립트 rawscript.sh에 대한 권한을 얻고 성공적으로 실행합니다!" title="Bash 스크립트 rawscript.sh에 대한 권한을 얻고 성공적으로 실행합니다!"/><figcaption class="wp-element-caption">Bash 스크립트 rawscript.sh에 대한 권한을 얻고 성공적으로 실행합니다!</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/f03/a8d/9c2/f03a8d9c2ecb1e3576e388c59bf33374.png" alt="스크립트 삭제 fileopen.py // rawscript.sh" title="스크립트 삭제 fileopen.py // rawscript.sh"/><figcaption class="wp-element-caption">스크립트 삭제 fileopen.py // rawscript.sh</figcaption></figure>
<!-- /wp:image -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/e91/ddd/baa/e91dddbaa475462a42032e3b0f87cbc5.png" alt="모든 트랜잭션은 &quot;RawTX.json&quot; 파일에 저장됩니다." title="모든 트랜잭션은 &quot;RawTX.json&quot; 파일에 저장됩니다."/><figcaption class="wp-element-caption">모든 트랜잭션은 "RawTX.json" 파일에 저장됩니다.</figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>그 결과 어떤 이점이 있습니까?</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>RawTX 구문 분석이 빠르고 모든 것이 Google 드라이브 폴더의 하나의 파일에 저장됩니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>getrawtransaction 명령과 달리&nbsp;&nbsp;<code>«txid»</code>콘솔에&nbsp;&nbsp;<code>Bitcoin Сore</code>&nbsp;입력할 필요 없이&nbsp;&nbsp;<code>«txid»</code>&nbsp;비트코인 ​​주소&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">getrawtx.sh "address" 만 입력하면 됩니다.</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>bash 스크립트:&nbsp;&nbsp;사이트&nbsp;&nbsp;<a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">API&nbsp;</a><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener">https://chain.so/api/</a>&nbsp;를 &nbsp;통한&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">getrawtx.sh는</a>&nbsp;&nbsp;사용되지 않은 트랜잭션 출력을 찾습니다.&nbsp;<a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener"></a><a href="https://chain.so/api/">&nbsp;</a><a href="https://chain.so/api/" target="_blank" rel="noreferrer noopener"></a><code>(UTXO)</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>소스 코드:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>텔레그램:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>동영상 자료:&nbsp;&nbsp;<a href="https://youtu.be/ECAPypsmMQs" target="_blank" rel="noreferrer noopener">https://youtu.be/ECAPypsmMQs</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/ECAPypsmMQs","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ECAPypsmMQs
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
