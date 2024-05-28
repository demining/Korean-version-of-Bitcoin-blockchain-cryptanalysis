# BTC 복구 암호화 가이드

<!-- wp:embed {"url":"https://www.youtube.com/embed/imTXE4rGqHw","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/imTXE4rGqHw
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">이 기사에서는 Crypto Deep Tools</a>&nbsp;리포지토리 의 오픈 소스 암호 복구 도구 및 지갑 시드 문구에 대해 자세히 살펴보고&nbsp;실수로 니모닉의 일부를 분실하거나 잊어버렸거나 실수를 한 상황에 대해서도 논의합니다. 그것을 해독.&nbsp;(따라서 빈 지갑이 표시되거나 시드가 유효하지 않다는 오류가 표시됩니다.) 지갑 암호 또는 암호 복구의 경우 암호가 무엇인지 합리적으로 알고 있는 경우 주로 유용합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>BTCRecover</em>&nbsp;&nbsp;는 오픈 소스 지갑 암호 및 시드 복구 도구입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/" target="_blank" rel="noreferrer noopener">가장 좋은 방법은 BTCRecover 설치 가이드를 따른 다음 원하는 복구 유형에 대한 "빠른 시작"을 읽는 것입니다.&nbsp;(또는 몇 가지 사용 예를 살펴보십시오)</a></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="usage-examples">사용 예</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 페이지는 다양한 복구 시나리오에서 BTCRecover를 사용하는 설정 및 구문을 보여주는 여러 예제에 대한 링크를 제공합니다.&nbsp;(일반적으로 해당 YouTube 동영상 포함)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>주어진 명령은 YouTube 비디오에 제공된 예제를 다시 만들 수 있도록 거의 그대로 복사/붙여넣기할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>참고:</strong>&nbsp;&nbsp;플랫폼에 따라 일부 변경이 필요할 수 있으며, 종종 "python"과 "python3"을 사용하는 것과 같은 단순한 변경이 필요할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Python 버전:</strong>&nbsp;&nbsp;이 비디오 중 다수는 BTCRecover의 다양한 포크를 사용하여 제작되었습니다.&nbsp;여기에 있는 리소스와 명령은 약간 다를 수 있지만 Python3에서 이 포크와 함께 작동하도록 설계되었습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seed-recovery">종자 회수</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>기본 시드 복구(다양한 유형의 지갑으로 복구에 사용할 기본 명령을 보여줍니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 id="basic-passwordpassphrase-recoveries">기본 비밀번호/암호 문구 복구</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>아이디어는 Windows에서 이 도구를 실행하는 경우 이러한 예제를 직접 복사/붙여넣기할 수 있다는 것입니다.&nbsp;(그들은 모두 자동 테스트에 있는 동일한 시드와 주소를 사용합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그들은 모두 거의 즉시 결과를 찾을 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seed-based-recovery-notes">시드 기반 복구 노트</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고</strong>&nbsp;&nbsp;Seedrecover.py는 기본값이 대부분의 단순한 "잘못된 menmonic" 또는 "잘못된 시드" 유형 오류에 대한 결과를 얻도록 설정되었습니다.&nbsp;(예: 오타가 있는 온전한 시드 백업이 있는 경우)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>모든 공통 파생 경로에서 지원되는 암호 화폐에 대한 모든 계정 유형을 검색합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>최대 몇 시간이 소요되는 네 가지 검색 단계를 자동으로 실행합니다.&nbsp;1. 단일 오타 2. 완전히 다른 BIP39 단어를 포함하는 두 개의 오타 3. 완전히 다른 BIP39 단어를 포함하는 세 개의 오타 4. 완전히 다른 단어일 수 있는 두 개의 오타</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>완전히 지원되는 지갑</strong>&nbsp;&nbsp;(지원되는 암호화폐의 경우)</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>하드웨어 지갑<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>렛저 나노 X와 S</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>트레저 원앤티</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>킵키</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>세이프팔</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>콜드카드</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비트박스02</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>요지</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>코보 금고</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>타원형</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>CoolWallet S(시드 번호를 BIP39 시드 단어로 변환하고 Bitcoin 및 Litecoin에 대해 –force-p2sh 인수를 사용해야 합니다...)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>소프트웨어 지갑<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Electrum – V1 및 V2 Seeds(여기에는 Electrum-LTC, Electron-Cash 등과 같은 포크가 포함됨)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>코이노미</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>와사비</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>에지 월렛</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>균사체</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>이동</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>트러스트 월렛</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>메타마스크(Binance Chain Wallet Extension과 같은 클론 포함)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>호환성 문제가 있는 지갑</strong>&nbsp;(파생기준 미준수…)</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>원자 지갑.&nbsp;(ETH(및 모든 ERC20 토큰)에 대한 비표준 파생, , XRP와 함께 사용해야 함&nbsp;&nbsp;<code>--checksinglexpubaddress</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>아브라 지갑.&nbsp;(비표준 시드 형식, 첫 번째 단어는 Non-BIP39 "at", 마지막 12개 단어는 BIP39(및 체크섬)이지만 파생을 재현할 수 없음)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="examples">실험적인 부분으로 넘어 갑시다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener"><strong>[TerminalGoogleColab]을</strong></a>&nbsp;열어봅시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">«17BTCRecoverCryptoGuide»</a></strong>&nbsp;저장소를 사용합시다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/17BTCRecoverCryptoGuide/

ls</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1301} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-1024x561.png" alt="BTC 복구 암호화 가이드" class="wp-image-1301"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>필요한 모든 패키지, 모듈 및 라이브러리를 설치하십시오.</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>pip3 install -r requirements.txt</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1304} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-1-1024x474.png" alt="BTC 복구 암호화 가이드" class="wp-image-1304"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":1305} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-2-1024x375.png" alt="BTC 복구 암호화 가이드" class="wp-image-1305"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>lscpu 명령을 사용하여 Google Colab의 프로세서 아키텍처 찾기</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>lscpu</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1325} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-7-1024x403.png" alt="BTC 복구 암호화 가이드" class="wp-image-1325"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>Linux용 PyOpenCL 설치</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sudo apt install python3-pyopencl</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1308} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-3-1024x491.png" alt="BTC 복구 암호화 가이드" class="wp-image-1308"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2>시스템 테스트</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v GPUTests</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1311} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-4-1024x359.png" alt="BTC 복구 암호화 가이드" class="wp-image-1311"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-bitoin-recoveries">기본 Bitoin 복구</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고:</strong>&nbsp;&nbsp;대부분의 경우 seedrecover.py를 실행하고 두 번 클릭하고 그래픽 인터페이스를 따르기만 하면 됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>기본 Segwit 주소 사용 – 하나의 누락된 단어, 5개의 주소 생성 제한. (따라서 주소는 해당 계정의 처음 5개 주소에 있어야 함)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 seedrecover.py --wallet-type bip39 --addrs bc1qv87qf7prhjf2ld8vgm7l0mj59jggm6ae5jdkx2 --mnemonic "element entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect" --addr-limit 5
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1312} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-5-1024x487.png" alt="BTC 복구 암호화 가이드" class="wp-image-1312"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>P2SH Segwit 주소 사용 – 하나의 누락된 단어, 5개의 주소 생성 제한. (따라서 주소는 해당 계정의 처음 5개 주소에 있어야 함)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --wallet-type bip39 --addrs 3NiRFNztVLMZF21gx6eE1nL3Q57GMGuunG --mnemonic "element entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect" --addr-limit 5
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":1313} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-6-1024x488.png" alt="BTC 복구 암호화 가이드" class="wp-image-1313"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-cardano-recoveries">기본 카르다노 복구</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Cardano 복구의 경우 여기에서도 참고 사항을 참조하십시오.&nbsp;Shelley-Era 기반 또는 지분 주소를 사용할 수 있습니다.&nbsp;(바이런 시대는 지원하지 않음)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>표준 기본 주소를 사용하여 한 단어가 누락된 Ledger Nano의 시드.&nbsp;(Cardano에서는 주소 생성 제한이 적용되지 않습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs addr1qyr2c43g33hgwzyufdd6fztpvn5uq5lwc74j0kuqr7gdrq5dgrztddqtl8qhw93ay8r3g8kw67xs097u6gdspyfcrx5qfv739l --mnemonic "wood blame garbage one federal jaguar slogan movie thunder seed apology trigger spoon basket fine culture boil render special enforce dish middle antique"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>표준 기본 주소를 사용하여 한 단어가 누락된 Trezor의 시드입니다.&nbsp;(Cardano에서는 주소 생성 제한이 적용되지 않습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs addr1q8k0u70k6sxkcl6x539k84ntldh32de47ac8tn4us9q7hufv7g4xxwuezu9q6xqnx7mr3ejhg0jdlczkyv3fs6p477fqxwz930 --mnemonic "ocean kidney famous rich season gloom husband spring convince attitude boy"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>표준 스테이크 주소를 사용하는 Yoroi, Adalite 또는 Daedalus(소프트웨어 지갑으로 작동)의 시드</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 seedrecover.py --wallet-type cardano --addrs stake1uxztdzzm4ljw9a0qmgregc8efgg56p2h3kj75kc6vmhfj2cyg0jmy --mnemonic "cave table seven there limit fat decorate middle gold ten battle trigger luggage demand"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-tron-recoveries">기본 Tron 복구</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>하나의 누락된 단어, 주소 생성 제한은 1입니다. (따라서 주소는 첫 번째 계정에 있어야 합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 seedrecover.py --wallet-type tron --addrs TLxkYzNpMCEz5KThVuZzoyjde1UfsJKof6 --mnemonic "have hint welcome skate cinnamon rabbit cable payment gift uncover column duck scissors wedding decorate under marine hurry scrub rapid change roast print arch" --addr-limit 1
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-helium-recoveries">기본 헬륨 회수</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>빠진 단어 하나</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 seedrecover.py --wallet-type helium --addrs 13hP2Vb1XVcMYrVNdwUW4pF3ZDj8CnET92zzUHqYp7DxxzVASbB --mnemonic "arm hundred female steel describe tip physical weapon peace write advice"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-polkadotsubstrate-recoveries">기본 Polkadot(기질) 복구</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>누락된 단어 하나, 빈 비밀 유도 경로</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 seedrecover.py --wallet-type polkadotsubstrate --addrs 13SsWBQSN6Se72PCaMa6huPXEosRNUXN3316yAycS6rpy3tK --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>누락된 단어 하나, "//hard/soft///btcr-test-password"의 비밀 파생 경로 소프트/하드 파생 경로는 –substrate-path 인수를 통해 프로그램에 전달되고 암호는 a와 동일하게 취급됩니다. 암호(선행 /// 제외)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>python3 seedrecover.py --wallet-type polkadotsubstrate --addrs 12uMBgecqfkHTYZE4GFRx847CwR7sfs2bTdPbPLpzeMDGFwC --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease" --passphrase-arg btcr-test-password --substrate-path //hard/soft
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="basic-stacks-recoveries">기본 스택 복구</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>하나의 누락된 단어, 10개의 주소 생성 제한. (따라서 주어진 시드에 대한 처음 10개의 "계정"을 확인합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 seedrecover.py --wallet-type stacks --addrs SP11KHP08F4KQ06MWESBY48VMXRBK5NB0FSCRP779 --mnemonic "hidden kidney famous rich season gloom husband spring convince attitude boy" --addr-limit 10
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>12단어 BIP39 Seeds Descrambling</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="descrambling-12-word-seeds">12개의 워드 시드 해독</h1>
<!-- /wp:heading -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/ruSF8OKwBRk","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/ruSF8OKwBRk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>이러한 테스트를 위해 세 가지 유형의 토큰 파일이 제공됩니다.&nbsp;첫 번째 확인에서 결과를 찾을 토큰 파일, 마지막 가능한 조합으로 결과를 찾을 토큰 파일 및 그 사이의 어느 시점에서 결과를 찾을 토큰 파일.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>아이디어는 이를 통해 일이 제대로 작동하는지 빠르게 확인하고(첫 번째 결과에서 찾기) 전체 실행에 걸리는 시간(마지막 결과)에 대한 아이디어를 얻고 실제 상황을 나타내는 것을 시도할 수 있다는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>12단어 시드를 디스크램핑하는 경우 테스트할 시드의 수를 쉽게 계산할 수 있고 시드 생성기가 최소 48개의 스레드를 쉽게 유지할 수 있기 때문에 –no-eta 없이 실행하는 데 많은 포인트가 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>참고:</strong>&nbsp;&nbsp;YouTube 비디오 및 예제는 OpenCL 가속이 Blockchain.com 지갑에 추가되기 전에 만들어졌으며 2배의 성능 향상을 제공할 수 있습니다.&nbsp;(자세한 내용은 GPU 가속 참조)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>성능</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>48코어 Linode에서 다음을 기대할 수 있습니다. * 15분 이내에 12단어 Electrum 시드를 해독합니다... * 50분 이내에 12단어 BIP39 시드를 해독합니다...</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>현재(2020년 중반) 중급 CPU에서는 이보다 약 5배 더 오래 걸릴 것으로 예상할 수 있습니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="electrum">일렉트럼</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-wallet-last-result">레거시 지갑(마지막 결과)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist lastcombination_electrum.txt 사용</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>book fit fly ketchup also elevator scout mind edit fatal where rookie</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --addr-limit 1 --addrs 1CU62HPowYSxhHiiNu1ukSbMjrkGj4x52i --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/lastcombination_electrum.txt --wallet-type electrum2
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="segwit-wallet">세그윗 지갑</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist randomcombination_electrum.txt 사용</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>social shoe spin enlist sponsor resource result coffee ocean gas file paddle</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type electrum2 --addr-limit 1 --addrs bc1qtylwmarke39nysxepdx5xzfatvrlel5z8m0jx2 --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/randomcombination_electrum.txt --bip32-path "m/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="bip39">BIP39</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="ethereum-address-default-derivation-path-for-trezor-mew">Ethereum 주소(Trezor, MEW의 기본 파생 경로)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist randomcombination_bip39.txt 사용</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>boy hidden kidney famous spring convince rich season gloom ocean husband attitude</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type ethereum --addr-limit 1 --addrs 0x66F9C09118B1C726BC24811a611baf60af42070A --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/randomcombination_bip39.txt --bip32-path "m/44'/60'/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-btc-address-first-result">레거시 BTC 주소(첫 번째 결과)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist firstcombination_bip39.txt 사용</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>boy attitude convince spring husband gloom season rich famous kidney hidden ocean</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/firstcombination_bip39.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="legacy-btc-address-last-result">레거시 BTC 주소(마지막 결과)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist lastcombination_bip39.txt 사용</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>ocean hidden kidney famous rich season gloom husband spring convince attitude boy</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/lastcombination_bip39.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="litecoin-native-segwit-address-seed-with-positional-anchors-for-known-words-last-word-as-any-valid-bip39-word-starting-with-b">Litecoin 기본 Segwit 주소(알려진 단어에 대한 위치 앵커가 있는 시드, 'B'로 시작하는 유효한 BIP39 단어의 마지막 단어)</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Tokenlist fixedwords_bip39.txt 사용</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>^1^ocean ^2^ocean ^3^ocean ^1^hidden ^2^hidden ^3^hidden ^1^kidney ^2^kidney ^3^kidney ^4^famous ^5^rich ^6^season gloom husband spring convince attitude baby bachelor bacon badge bag balance balcony ball bamboo banana banner bar barely bargain barrel base basic basket battle beach bean beauty because become beef before begin behave behind believe below belt bench benefit best betray better between beyond bicycle bid bike bind biology bird birth bitter black blade blame blanket blast bleak bless blind blood blossom blouse blue blur blush board boat body boil bomb bone bonus book boost border boring borrow boss bottom bounce box boy bracket brain brand brass brave bread breeze brick bridge brief bright bring brisk broccoli broken bronze broom brother brown brush bubble buddy budget buffalo build bulb bulk bullet bundle bunker burden burger burst bus business busy butter buyer buzz</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs ltc1q9srpp39hev6dpsxjjp8t5g0m3z7509vc9llalv --tokenlist ./docs/Usage_Examples/2020-05-02_Descrambling_a_12_word_seed/fixedwords_bip39.txt --bip32-path "m/84'/2'/0'/0"
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>추가 단어가 포함된 다중 장치 디스크램블링 12 단어 시드("필수" 앵커, "위치" 앵커 및 여러 장치에 작업 분산 시연)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="required-anchors-positional-anchors-and-spreading-work-accross-multiple-devices">"필수" 앵커, "위치" 앵커 및 여러 장치에 걸쳐 작업 분산</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>YouTube 동영상은 여기에서 찾을 수 있습니다: TBC</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="background"><strong>배경</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>잠재적인 단어의 토큰 목록을 사용하여 BIP39 시드를 간단히 해독할 수 있는 것 외에도 BTCRecover는&nbsp;&nbsp;<em>일부</em>&nbsp;&nbsp;단어의 위치를 ​​알면서 시드 문구에 미끼 단어를 추가로 포함할 수 있는 상황에서도 사용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>사용 중인 토큰 목록 예: tokenlist.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17</td><td><code>+ ^1^ocean + ^2^hidden + ^3^kidney famous + ^5^rich + ^6^season + ^7^gloom husband spring + ^10^convince + ^11^attitude + ^12^boy glove section chunk brick sauce</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>더 큰 복구 작업의 경우 BTCRecover를 사용하면 여러 장치에 워크로드를 분산시킬 수도 있습니다.&nbsp;BTCRecover가 사용하는 프로세스는&nbsp;&nbsp;<strong>결정론적</strong>&nbsp;&nbsp;이라는 점을 이해하는 것이 중요합니다. 이것이 의미하는 바는 BTCRecover를 실행할 때마다 매번 정확히 동일한 순서로 잠재적인 암호/암호 문구를 검색한다는 것입니다.&nbsp;이것의 의미는 -workers 명령을 사용하지 않고 동시에 두 개의 장치에서 실행하면 단순히 동일한 작업을 두 번 수행한다는 것입니다…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>다행스럽게도 검색을 조각으로 분할하고 이러한 조각을 다른 장치에 할당할 수 있습니다.&nbsp;이를 위한 메커니즘은 기본적으로 "라운드 로빈" 스케줄링 스타일로 암호를 할당하는 매우 간단합니다.&nbsp;(예: 작업이 3개의 장치에 대해 3개의 조각으로 분할된 경우 각 장치는 3번째 암호마다 처리합니다.) 또한 하나의 장치가 다른 장치보다 몇 배 더 빠른 상황에서 단일 장치에 여러 시간 조각을 할당하는 기능도 있습니다. 기타.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>따라서 PC1과 PC2라는 두 장치의 예를 살펴보겠습니다.&nbsp;이 예에서 PC1은 PC2보다 두 배 강력하므로 작업의 2/3가 할당되고 PC2는 1/3이 할당됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="practical-limits">실질적인 한계</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이와 같은 상황에서 얼마나 많은 잠재적 암호가 있는지 알아내는 것은 매우 간단합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>예를 들어, 20개의 단어 목록이 있고 12개의 단어 시드 내에서 그 중 3개의 위치를 ​​안다면 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>17 * 16 * 15 * 14 * 13 * 12 * 11 * 10 * 9 = 8,821,612,800 가능한 시드(사용 가능한 CPU 성능에 따라 며칠 안에 가능)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="running-btcrecover">BTCRecover 실행</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>두 PC 모두 BTCRecover가 설치되어 있어야 하며 두 PC 모두 동일한 명령을 사용합니다. 단, –worker 명령은 PC마다 다릅니다.&nbsp;(우리는 이 토큰 목록이 테스트할 아주 작은 세트만 생성한다는 사실을 무시할 수 있습니다)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>장치는 동일한 운영 체제를 실행할 필요가 없으며 어떤 식으로든 서로 통신할 필요도 없습니다...</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="command-on-pc-1">PC 1의 명령</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>따라서 작업 조각 1과 2를 PC1에 할당하려고 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-23_multi_device_descrambling_12_word_seed_with_extras/tokenlist.txt
 --no-eta --worker 1,2/3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="command-on-pc-2">PC 2의 명령</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>그리고 슬라이스 3을 PC2로 작업</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./docs/Usage_Examples/2020-05-23_multi_device_descrambling_12_word_seed_with_extras/tokenlist.txt
 --no-eta --worker 3/3
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="the-outcome">결과…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 예에서 올바른 시드 구는 PC2에서 찾습니다.&nbsp;장치 간에 통신이 없기 때문에 PC1은 검색 공간이 소진될 때까지 검색을 계속합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것은 또한 이 명령을 사용할 때 수행 중인 작업에 주의를 기울여야 함을 강조합니다.&nbsp;실수로 작업 공유를 PC에 할당하는 것을 잊었거나 동일한 공유를 두 번 할당한 경우 BTCrecover는 이러한 일이 발생했음을 알 수 없으며 테스트되지 않은 공유에서 올바른 암호가 발생했다면 결과를 찾을 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="closing-thoughts">마무리 생각</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>–no-eta 명령을 사용하면 장치가 암호를 확인하는 현재 속도를 표시하므로 이와 같은 상황에서 유용할 수 있습니다.&nbsp;또한 즉시 시작됩니다.&nbsp;(클라우드 서버 시간에 대한 비용을 지불하는 경우 좋을 수 있음)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 명령을 사용하는 것이 유용한 한 가지 방법은 PC에서 이미 암호 검색을 시작했고 몇 개의 암호를 확인해야 하는지 알고 있는 경우 –no-eta를 사용하여 실행 속도를 높이고 수동으로 작업할 수 있습니다. 시간이 얼마나 걸릴지.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>단일 장치에서 시드 복구를 시작했고 다중 장치 설정으로 이동하고 싶지만 단일 장치에서 이미 테스트된 비밀번호를 다시 확인하고 싶지 않은 경우, 몇 개의 비밀번호가 있는지 기록해 둘 수 있습니다. 단일 장치가 테스트되었으며 여러 장치에서 테스트를 다시 시작할 때 –skip 명령을 사용하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>토큰 목록 기반 시드 복구에서 단어 그룹화(여러 단어 그룹이 서로 이어지는 것으로 알려져 있지만 시드 내에서 이러한 그룹의 위치를 ​​알 수 없는 24단어 시드를 해독하는 방법을 보여줍니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="grouping-words-together-in-tokenlist-based-seed-recoveries">토큰 목록 기반 시드 복구에서 단어 그룹화</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="background">배경</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>때로는 누군가가 순서를 알 수 없는 방식으로 시드를 작성했거나 백업을 여러 부분으로 분할했을 수 있는 복구가 있습니다.&nbsp;어느 쪽이든 이것은 상대적인 순서가 알려진 방식으로 그룹화된 단어이지만 더 큰 시드 내에서 이러한 단어의 위치는 알 수 없음을 의미할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이와 같은 상황에서 토큰 목록 내의 단어에 대해 단일 쉼표 문자&nbsp;&nbsp;<code>,</code>&nbsp;(공백 없음, 단일 쉼표)를 사용하여 제공된 순서대로 단어를 함께 사용해야 함을 나타낼 수 있습니다.&nbsp;이는 "상대 앵커" 기능과 유사하지만 훨씬 더 효율적이며 여러 단어 그룹화도 허용합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그룹화된 단어 토큰은 다른 유형의 앵커, 위치 등과 함께 사용할 수도 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이러한 토큰을 사용하면 토큰 수가 더 이상 니모닉 길이와 같지 않음을 의미하므로(일반적으로 단일 단어 토큰으로 디스크램블링하는 경우와 같이) 및 인수를 사용하여 시도해야 하는 최소 토큰 수를 지정할 수도&nbsp;&nbsp;<code>--min-tokens</code>&nbsp;있습니다&nbsp;&nbsp;<code>--max-tokens</code>&nbsp;. 주어진 시드 추측에 대해.&nbsp;(쉼표로 구분된 단어 그룹은 단일 토큰으로 계산됩니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>시드 디스크램블링과 마찬가지로 이러한 종류의 복구에 대한 상한은 토큰 수를 기반으로 하며 일반적으로(위치 앵커 없이) 최대 토큰이 있습니다!&nbsp;(max-tokens factorial) 확인 가능한 시드.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example">예</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>다음 예제에서는 다음 토큰 목록을 사용합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12</td><td><code>^basic,dawn,renew,punch,arch,situate arrest,question,armor hole,lounge,practice resist zoo,zoo,zoo indicate,call lens,group,empty zoo husband verify,eternal,injury battle,satoshi brother,damp,this</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>이 토큰 목록에서 우리가 올바른 순서로 되어 있다고 확신하는 몇 가지 토큰 블록(시드 단어 그룹 중 하나에 대한 위치 앵커 포함)과 몇 가지 추가/단일 단어가 있음을 볼 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그리고 다음 명령으로 실행됩니다(몇 초 안에 결과를 찾을 것입니다).</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 seedrecover.py --tokenlist ./docs/Usage_Examples/2022-04-02_Seed_Tokenlist_TokenBlocks/tokengroups_tokenlist.txt --mnemonic-length 24 --language en --wallet-type bip39 --addrs 1PTcESpqrmWePYB5h18Ni11QTKNfMkdSYJ --dsw --addr-limit 10 --max-tokens 9 --min-tokens 8
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>올바른 씨앗은 다음과 같습니다.&nbsp;<code>basic dawn renew punch arch situate resist indicate call lens group empty brother damp this verify eternal injury arrest question armor hole lounge practice</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>보시다시피 이것은 위의 토큰 목록 파일에 포함된 일부 토큰 그룹으로 구성됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="password-recovery">비밀번호 복구</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>기본 비밀번호 복구(다양한 유형의 지갑에서 복구에 사용할 기본 명령을 보여줍니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="basic-passwordpassphrase-recoveries">기본 비밀번호/암호 문구 복구</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이러한 예는 다양한 유형의 오타, 토큰 목록 등에 사용할 인수와 관련이 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>아이디어는 Windows에서 이 도구를 실행하는 경우 이러한 예제를 직접 복사/붙여넣기할 수 있다는 것입니다.&nbsp;(그들은 모두 자동 테스트에 있는 동일한 시드와 주소를 사용합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그들은 모두 거의 즉시 결과를 찾을 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>아래의 기본 예제에서 사용되는 기본 비밀번호 목록</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>btcr-test-password btcr-test-password:p2pkh btcr-test-password:p2wpkh btcr-test-password:p2wpkh-p2sh btcrtestpassword2022</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="bip38-encrypted-paper-wallet-recovery">BIP38 암호화된 종이 지갑 복구.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고</strong>&nbsp;&nbsp;BIP38 지갑은 sCrypt를 통해 암호화되므로 무차별 대입이 매우 느립니다.&nbsp;이러한 지갑에 대한 GPU 가속을 사용할 수 있지만 여러 개의 GPU가 있거나 CPU에 비해 ​​특히 강력한 GPU가 있지 않는 한(또는 일종의 전용 OpenCL 가속기) 성능 향상을 많이 제공하지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>지원되는 지갑</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.bitaddress.org/">bitaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://liteaddress.org/">liteaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://paper.dash.org/">paper.dash.org</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>그리고 거의 모든 다른 BIP38 암호화 개인 키.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>비트코인의 경우(코인을 지정할 필요가 없으며 기본적으로 비트코인이 선택됨)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PnM7h9sBC9EMZxLVsKzpafvBN8zjKp8MZj6h9mfvYEQRMkKBTPTyWZHHx --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>라이트코인의 경우</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PfVHSTbgRNDaSwddBNgx2vMhMuNdiwRWjFgMGcJPb6J2pCG32SuL3vo6q --bip38-currency litecoin --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>대시의 경우</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 btcrecover.py --bip38-enc-privkey 6PnZC9Snn1DHyvfEq9UKUmZwonqpfaWav6vRiSVNXXLUEDAuikZTxBUTEA --bip38-currency dash --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="bip39-passphrase-protected-wallets-electrum-extra-words">BIP39 암호 보호 지갑 및 Electrum "추가 단어"</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고</strong>&nbsp;&nbsp;BIP39 암호 구문을 참조하는 데 사용되는 언어는 공급업체마다 다를 수 있습니다.&nbsp;때때로 그것은 "25번째 단어"로, 다른 때에는 "그럴듯한 거부 가능성 암호" 또는 때때로 "암호"로 언급됩니다.&nbsp;이것은 지갑 비밀번호 또는 PIN과 다르다는 점에 유의하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BIP39 암호에 오류가 있는 가장 일반적인 증상은 시드+암호가 잔액이나 거래 내역 없이 완전히 비어 있는 일련의 계정을 생성한다는 것입니다.&nbsp;(모든 BIP39 암호가 유효하므로 어떤 종류의 오류 메시지도 표시되지 않습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BIP39 시드 복구는 GPU 가속의 이점을 누릴 수 있지만 현재 BIP39 암호를 복구하는 경우에는 그렇지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>아래의 모든 예제 명령에는 주소 생성 제한이 10으로 설정되어 있으므로 검색하는 주소는 지갑의 처음 10개 주소 내에 있어야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>지원되는 지갑</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>BIP39/44를 지원하는 대부분의 하드웨어 지갑<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Trezor(원앤티)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>렛저 나노(S 및 X)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>킵키</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>콜드카드</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비트박스02</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>코보 볼트 프로</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP39/44를 지원하는 대부분의 소프트웨어 지갑<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>와사비 지갑(와사비는 지갑 비밀번호라고 함)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>사무라이 지갑</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>코이노미</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>균사체</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Zillet("암호 기반" 지갑 유형으로 BIP39 암호 문구 참조)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>일렉트럼</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>이동</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>기본 Bitcoin 명령이므로 지정할 필요 없음&nbsp;&nbsp;<code>--wallet-type</code>&nbsp;추가 매개변수를 추가할 필요 없이 모든 Bitcoin 주소 유형(Legacy, Segwit 또는 Native Segwit)을 지원합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 btcrecover.py --bip39 --addrs 1AmugMgC6pBbJGYuYmuRrEpQVB9BBMvCCn --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "certain come keen collect slab gauge photo inside mechanic deny leader drop"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 비트코인 ​​일렉트럼 지갑 명령.&nbsp;이들은 BIP39가 아니므로&nbsp;&nbsp;<code>--wallet-type electrum2</code>&nbsp;추가 매개변수 없이 Legacy 및 Segwit Electrum 지갑을 모두 지원합니다.&nbsp;(대부분의 Electrum Altcoin 클론에서도 작동합니다)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 btcrecover.py --wallet-type electrum2 --addrs bc1q6n3u9aar3vgydfr6q23fzcfadh4zlp2ns2ljp6 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "quote voice evidence aspect warfare hire system black rate wing ask rug"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 이더리움 명령이므로 지정해야 합니다&nbsp; (하지만&nbsp;&nbsp;함축된 대로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ).<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 btcrecover.py --wallet-type ethereum --addrs 0x4daE22510CE2fE1BC81B97b31350Faf07c0A80D2 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 Zilliqa 명령이므로 지정해야 합니다&nbsp; (그러나&nbsp;&nbsp;암시적으로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ). 이렇게 하면 추가 매개 변수를 추가할 필요 없이 모든 주소 유형(Base16 및 Bech32)이 지원됩니다.<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>참고: Zilliqa 시드 복구는 현재 Ledger Nano 시드/암호를 복구하기 위한 기반으로 사용할 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 btcrecover.py --wallet-type zilliqa --addrs zil1dcsu2uz0yczmunyk90e8g9sr5400c892yeh8fp --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 비트코인 ​​캐시 명령이므로 지정해야 합니다&nbsp; (하지만&nbsp;&nbsp;함축된 대로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ) 이것은 캐시 주소 또는 레거시 스타일 주소를 허용합니다... 이것은 BSV와 같은 BCH 포크에서도 작동합니다...<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>python3 btcrecover.py --wallet-type bch --addrs bitcoincash:qqv8669jcauslc88ty5v0p7xj6p6gpmlgv04ejjq97 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 Cardano이므로 지정해야 합니다&nbsp; (그러나&nbsp;&nbsp;함축된 대로 인수를&nbsp;&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ). Cardano 복구의 경우&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/">여기에서도 참고 사항을 참조하십시오.&nbsp;</a>&nbsp;이것은 기본 또는 스테이크 주소를 허용합니다...(Byron-Era 주소는 지원되지 않음))<code>--bip39</code><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/"></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>python3 btcrecover.py --wallet-type cardano --addrs addr1q90kk6lsmk3fdy54mqfr50hy025ymnmn5hhj8ztthcv3qlzh5aynphrad3d26hzxg7xzzf8hnmdpxwtwums4nmryj3jqk8kvak --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "ocean hidden kidney famous rich season gloom husband spring convince attitude boy"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 대시 명령이므로 지정해야 합니다&nbsp; (하지만&nbsp;&nbsp;함축된 대로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ).<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>python3 btcrecover.py --wallet-type dash --addrs XuTTeMZjUJuZGotrtTPRCmHCaxnX44a2aP --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 Dogecoin 명령이므로 지정해야 합니다&nbsp; (하지만&nbsp;&nbsp;함축된 대로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ).<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>python3 btcrecover.py --wallet-type dogecoin --addrs DSTy3eptg18QWm6pCJGG4BvodSkj3KWvHx --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 Vertcoin 명령이므로 지정해야 합니다&nbsp; (그러나&nbsp;&nbsp;암시적으로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ) 이것은 추가 매개변수를 추가할 필요 없이 모든 주소 유형(레거시, Segwit 또는 기본 Segwit)을 지원합니다.<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --wallet-type vertcoin --addrs Vwodj33bXcT7K1uWbTqtk9UKymYSMeaXc3 --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 Litecoin 명령이므로 지정해야 합니다&nbsp; (그러나&nbsp;&nbsp;암시적으로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ) 이것은 추가 매개변수를 추가할 필요 없이 모든 주소 유형(Legacy, Segwit 또는 Native Segwit)을 지원합니다.<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 btcrecover.py --wallet-type litecoin --addrs LdxLVMdt49CXcrnQRVJFRs8Yftu9dE8xxP --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 Monacoin 명령이므로 지정해야 합니다&nbsp;&nbsp;<code>--wallet-type</code>&nbsp;(그러나 암시적으로 인수를 생략할 수 있음&nbsp;&nbsp;<code>--bip39</code>&nbsp;) 이것은 추가 매개변수를 추가할 필요 없이 모든 주소 유형(Legacy, Segwit 또는 Native Segwit)을 지원합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>python3 btcrecover.py --wallet-type monacoin --addrs MHLW7WdRKE1XBkLFS6oaTJE1nPCkD6acUd --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 DigiByte 명령이므로 지정해야 합니다&nbsp; (그러나&nbsp;&nbsp;암시적으로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ) 이것은 추가 매개변수를 추가할 필요 없이 모든 주소 유형(레거시, Segwit 또는 기본 Segwit)을 지원합니다.<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>python3 btcrecover.py --wallet-type digibyte --addrs DNGbPa9QMbLgeVspu9jb6EEnXjJASMvA5r --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 GroestleCoin 명령이므로 지정해야 합니다&nbsp;&nbsp;<code>--wallet-type</code>&nbsp;(그러나 암시적으로 인수를 생략할 수 있음&nbsp;&nbsp;<code>--bip39</code>&nbsp;) 이것은 추가 매개 변수를 추가할 필요 없이 모든 주소 유형(레거시, Segwit 또는 기본 Segwit)을 지원합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>참고: 이를 위해서는 groestlecoin_hash 모듈을 설치해야 합니다…</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>python3 btcrecover.py --wallet-type groestlecoin --addrs FWzSMhK2TkotZodkApNxi4c6tvLUo7MBWk --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 리플 명령이므로 지정해야 합니다&nbsp; (단&nbsp;&nbsp;, 함축된 대로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ).<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>python3 btcrecover.py --wallet-type ripple --addrs rwv2s1wPjaCxmEFRm4j724yQ5Lh161mzwK --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "cable top mango offer mule air lounge refuse stove text cattle opera"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 Tron 명령이므로 지정해야 합니다&nbsp; (그러나&nbsp;&nbsp;함축된 대로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ).<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>python3 btcrecover.py --wallet-type tron --addrs TGvJrj5D8qdzhcppg9RoLdfbEjDYCne8xc --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "have hint welcome skate cinnamon rabbit cable payment gift uncover column duck scissors wedding decorate under marine hurry scrub rapid change roast print arch" 
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 Polkadot(기질) 명령이므로 지정해야 합니다&nbsp; (하지만&nbsp;&nbsp;함축된 대로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ).<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 명령은 올바른 "비밀 파생 경로"를 검색합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 btcrecover.py --wallet-type polkadotsubstrate --addrs 12uMBgecqfkHTYZE4GFRx847CwR7sfs2bTdPbPLpzeMDGFwC --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "toilet assume drama keen dust warrior stick quote palace imitate music disease" --substrate-path "//hard/soft"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 스택 명령이므로 지정해야 합니다&nbsp; (그러나&nbsp;&nbsp;암시적으로 인수를 생략할 수 있음). 이 예제에는 주소 생성 제한이 10으로 설정되어 있으므로 지정된 시드+암호 문구에 대해 처음 10개의 "계정"을 확인합니다&nbsp;<code>--wallet-type</code>&nbsp;.&nbsp;<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>python3 btcrecover.py --wallet-type stacks --addrs SP2KJB4F9C91R3N5XSNQE0Z3G34DNJWQYTP3PBJTH --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --mnemonic "ocean hidden kidney famous rich season gloom husband spring convince attitude boy" --addr-limit 10
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="brainwallets">두뇌 지갑</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고</strong>&nbsp;&nbsp;Brainwallets는 매우 오래된(&nbsp;<strong>그리고 매우 안전하지 않은</strong>&nbsp;) 유형의 지갑입니다.&nbsp;이를 감안할 때 대부분은 여전히 ​​"압축되지 않은" 주소를 생성합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>지원되는 지갑</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Sha256(암호) 지갑<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.bitaddress.org/">bitaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://segwitaddress.org/">segwitaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://liteaddress.org/">liteaddress.org</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://paper.dash.org/">paper.dash.org</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>워프월렛 지갑<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://keybase.io/warp/">워프월렛</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://dvdbng.github.io/memwallet/">멤월렛</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://patcito.github.io/mindwallet/">마인드월렛</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 id="sha256passphrase-wallets">Sha256(암호) 지갑</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>기본 Bitcoin 명령(이 예에서는 압축된 주소이지만 압축 및 압축되지 않은 주소 유형을 모두 확인합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 1BBRWFHjFhEQc1iS6WTQCtPu2GtZvrRcwy --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Bitcoin Wallet이지만 압축되지 않은 주소만 확인하도록 설정합니다.&nbsp;(압축된 주소가 아니라고 확신하는 아주 오래된 지갑에만 사용하십시오. 압축되지 않은 주소가 기본값이라는 점을 고려하십시오… 약간의 속도 향상만 제공합니다)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 1MHoPPuGJyunUB5LZQF5dXTrLboEdxTmUm --skip-compressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>P2SH Bitcoin 지갑</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs 3C4dEdngg4wnmwDYSwiDLCweYawMGg8dVN --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Bech32 비트코인 ​​지갑.&nbsp;(segwitaddress.org에서)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_25" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs bc1qth4w90jmh0a6ug6pwsuyuk045fmtwzreg03gvj --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Litecoin 지갑(liteaddress.org에서 – 압축을 사용할 수 있는 옵션 없이 모두 압축되지 않음) 이러한 유형의 지갑에는 추가 인수가 필요하지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_26" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs LfWkecD6Pe9qiymVjYENuYXcYpAWjU3mXw --skip-compressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>대시 지갑(paper.dash.org에서) – 지정된 압축 매개변수가 없으므로 둘 다 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_27" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs XvyeDeZAGh8Nd7fvRHZJV49eAwNvfCubvB --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>대시 지갑(paper.dash.org에서 – 또는 압축된 것을 사용했다는 것을 알고 있다면… (비압축이 기본값이지만)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_28" class="wp-block-code"><code>python3 btcrecover.py --brainwallet --addrs XksGLVwdDQSzkxK1xPmd4R5grcUFyB3ouY --skip-uncompressed --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="warpwallets">워프 지갑</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>참고: 현재 비트코인과 라이트코인만 지원합니다… (Eth는 쉽게 추가할 수 있습니다)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>소금으로 "btcr-test-password"가 있는 기본 비트코인 ​​지갑.&nbsp;(워프지갑은 이메일 주소 사용을 권장합니다) 이 지갑들은 모두 "압축되지 않은" 유형이지만 sCrypt 작업에 걸리는 시간에 비해 성능 향상이 너무 적기 때문에 두 유형을 모두 확인하지 않을 가치가 없습니다…</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_29" class="wp-block-code"><code>python3 btcrecover.py --warpwallet --warpwallet-salt btcr-test-password --addrs 1FThrDFjhSf8s1Aw2ed5U2sTrMz7HicZun --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>소금으로 "btcr-test-password"가 있는 기본 Litecoin 지갑.&nbsp;(memwallet이나 mindwallet이 생성하는 것과 마찬가지로 -crypto 인수를 추가하고 라이트코인을 지정해야 합니다.) 이 지갑은 모두 "압축되지 않은" 유형이지만 sCrypt 작업에 걸리는 시간에 비해 성능 향상이 너무 적습니다. 두 가지 유형을 모두 확인하지 않을 가치가 없습니다…</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_30" class="wp-block-code"><code>python3 btcrecover.py --warpwallet --warpwallet-salt btcr-test-password --crypto litecoin --addrs LeBzGzZFxRUzzRAtm8EB2Dw74jRfQqUZeq --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="blockio-wallets">Block.io 지갑</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>먼저 설명서의 스크립트 추출 섹션에 있는 지침을 사용하여 지갑 파일을 다운로드합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 아래와 같은 명령을 사용하여 기본 복구를 수행합니다.&nbsp;(이 명령은 BTCRecover와 함께 제공되는 샘플 지갑 파일을 사용합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_31" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/block.io.request.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="dogechaininfo-wallets">Dogechain.info 지갑</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>먼저 설명서의 스크립트 추출 섹션에 있는 지침을 사용하여 지갑 파일을 다운로드합니다.&nbsp;추출 스크립트를 사용하여 대여한 하드웨어에서 dogechain.info 지갑을 안전하게 실행할 수도 있습니다.&nbsp;스크립트 추출에 대한 자세한 내용은 여기를 참조하십시오…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 아래와 같은 명령을 사용하여 기본 복구를 수행합니다.&nbsp;(이 명령은 BTCRecover와 함께 제공되는 샘플 지갑 파일을 사용합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_32" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/dogechain.wallet.aes.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="ethereum-keystores">이더리움 키 저장소</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>아래와 같은 명령으로 기본 복구를 수행합니다.&nbsp;(이 명령은 BTCRecover와 함께 제공되는 샘플 지갑 파일을 사용합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_33" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/utc-keystore-v3-scrypt-myetherwallet.json --passwordlist ./docs/Usage_Examples/common_passwordlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="slip39-passphrases">SLIP39 암호</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이것은 BIP39 암호를 복구하는 것과 동일한 구문을 많이 사용합니다.&nbsp;BTCRecover는 현재 Trezor T에서 지원하는 대부분의 코인을 지원합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>주요 차이점은 단일 니모닉을 입력하는 대신 아래와 같이 명령줄을 통해 SLIP39 공유를 입력하거나 프롬프트가 표시된다는 것입니다.&nbsp;암호 복구를 수행하려면 SLIP39 공유의 쿼럼이 필요합니다…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>기본 Bitcoin 명령이므로 지정할 필요 없음&nbsp;&nbsp;<code>--wallet-type</code>&nbsp;추가 매개변수를 추가할 필요 없이 모든 Bitcoin 주소 유형(Legacy, Segwit 또는 Native Segwit)을 지원합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_34" class="wp-block-code"><code>python3 btcrecover.py --slip39 --addrs bc1q76szkxz4cta5p5s66muskvads0nhwe5m5w07pq --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --slip39-shares "hearing echo academic acid deny bracelet playoff exact fancy various evidence standard adjust muscle parcel sled crucial amazing mansion losing" "hearing echo academic agency deliver join grant laden index depart deadline starting duration loud crystal bulge gasoline injury tofu together"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>기본 이더리움 명령이므로 지정해야 합니다&nbsp; (하지만&nbsp;&nbsp;함축된 대로 인수를&nbsp;<code>--wallet-type</code>&nbsp;생략할 수 있음&nbsp; ).<code>--bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_35" class="wp-block-code"><code>python3 btcrecover.py --slip39 --wallet-type ethereum --addrs 0x0Ef61684B1E671dcBee4D51646cA6247487Ef91a --addr-limit 10 --passwordlist ./docs/Usage_Examples/common_passwordlist.txt --slip39-shares "hearing echo academic acid deny bracelet playoff exact fancy various evidence standard adjust muscle parcel sled crucial amazing mansion losing" "hearing echo academic agency deliver join grant laden index depart deadline starting duration loud crystal bulge gasoline injury tofu together"
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="raw-private-keys">원시 개인 키</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover는 손상된 개인 키가 있는 상황에서 복구하는 데에도 사용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것은 암호 복구와 유사한 방식으로 처리되므로 개인 키 추측은 토큰 목록에 들어가고 %h 와일드카드를 사용하여 16진수 문자를 대체하거나 %b를 사용하여 base58 문자를 대체합니다.&nbsp;표준 오타뿐 아니라 상황에 따라 토큰 목록 또는 암호 목록을 사용할 수 있습니다.&nbsp;토큰 목록을 사용하는 경우 생성되는 개인 키가 개인 키에 필요한 길이 및 문자와 일치하는지 확인하기만 하면 됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>개인 키에 해당하는 주소를 알고 있는 경우 이를 제공하거나 AddressDB를 사용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="raw-eth-private-keys">원시 Eth 개인 키</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>또한 개인 키에서 선행 "0x"를 제거해야 함을 알 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>예시 토큰 목록</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1</td><td><code>5db77aa7aea5%2h7d6b4c64dab21%h972cf4763d4937d3e6e17f580436dcb10%3h</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>위의 토큰 목록은 3개의 손상된 부분이 있는 표준 Eth 개인 키(선행 0x가 제거됨)의 예입니다.&nbsp;하나의 단일 문자(%h), 하나의 두 문자(%2h) 및 하나의 세 문자(%3h) 실행하는 데 약 20분이 소요됩니다…</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_37" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs 0xB9644424F9E639D1D0F27C4897e696CC324948BB --wallet-type ethereum --tokenlist ./docs/Usage_Examples/eth_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="raw-bitcoin-private-keys">원시 Bitcoin 개인 키</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>비트코인 개인 키는 Base58의 압축 및 비압축 형식 모두와 원시 16진법 키로도 지원됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>한 줄에 하나씩 여러 개인 키가 있는 토큰 목록(아래 예 참조)을 사용하는 경우 "–max-tokens 1" 인수도 지정해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>예시 토큰 목록</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1</td><td><code>5db77aa7aea5%2h7d6b4c64dab21%h972cf4763d4937d3e6e17f580436dcb10%3h</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>아래 명령은 세 개의 가능한 개인 키가 포함된 토큰 목록을 사용하여 하나의 문자가 누락된 압축되지 않은 구식 개인 키에 대한 복구를 시도합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_39" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs 1EDrqbJMVwjQ2K5avN3627NcAXyWbkpGBL --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>아래 명령은 세 개의 가능한 개인 키가 포함된 토큰 목록을 사용하여 한 문자가 누락된 보다 현대적인(압축된 기본 세그윗 주소) 개인 키에 대한 복구를 시도합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_40" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addrs bc1qafy0ftpk5teeayjaqukyd244un8gxvdk8hl5j6 --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>해당 주소에 대한 기록이 없더라도 AddressDB를 이용하여 raw private key 복구도 가능합니다.&nbsp;(Eth, BCH 등에서도 작동합니다…)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_41" class="wp-block-code"><code>python3 btcrecover.py --rawprivatekey --addressdb ./btcrecover/test/test-addressdbs/addresses-BTC-Test.db --wallet-type bitcoin --max-tokens 1 --tokenlist ./docs/Usage_Examples/btc_privkey_tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Blockchain.com 지갑 암호 복구(추출 스크립트, 토큰 목록, 암호 목록 및 다양한 유형 또는 오타를 사용하여 Blockchain.com 지갑을 복구하는 방법을 보여줌)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="recovering-blockchaincom-wallets">Blockchain.com 지갑 복구</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="previously-known-as-blockchaininfo"><em>이전에는 blockchain.info로 알려짐</em></h4>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="overview">개요</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>2020년부터 모든 blockchain.com 지갑은 먼저 이 추출 스크립트를 사용하여 지갑 파일을 다운로드해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>해당 파일이 있으면 blockchain.com 지갑을 복구할 수 있는 두 가지 방법이 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>1) 지갑 파일 직접 사용</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>blockchain.com에서 다운로드한 wallet.aes.json 파일로 BTCRecover를 실행합니다.&nbsp;이것은 BTCRecover를 실행하는 사람/PC가 복구된 지갑 파일을 즉시 사용할 수 있는 충분한 정보를 가지고 있는 BTCRecover를 실행하는 "정상적인" 방법입니다.&nbsp;(따라서 BTCRecover를 실행하는 환경에 대해 예방 조치를 취해야 합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>2) 지갑 파일 “추출” 사용</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>지갑 파일에서 소량의 데이터를 추출하고 그것으로 BTCRecover를 실행합니다... 이것이 의미하는 바는 걱정할 필요 없이 이 데이터 부분을 다른 사람에게 제공하여 복구하거나 일부 클라우드 기반 시스템에서 실행할 수 있다는 것입니다. 누군가가 귀하의 암호화폐를 훔칠 수 있는 정보 유출에 대해.&nbsp;(따라서 BTCRecover를 실행하는 환경의 보안에 대해 크게 걱정할 필요가 없습니다)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>지갑 추출을 사용하려면 몇 가지 추가 단계가 필요합니다... 추출 스크립트에 대한 자세한 내용은 여기를 참조하십시오...</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example-1-using-a-tokenlist-to-recover-wallet-main-password-from-a-wallet-file">예 1 – TokenList를 사용하여 지갑 파일에서 지갑 기본 비밀번호 복구</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="download-the-wallet-file">지갑 파일 다운로드…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover 폴더로 이동하여 다음을 실행합니다.&nbsp;&nbsp;<strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python ./extract-scripts/download-blockchain-wallet.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 walletID를 입력하라는 메시지가 표시되며 이메일을 통해 요청을 확인하고 필요한 2fa 코드를 입력해야 합니다.&nbsp;(비디오에서 나는 558751da-d609-486d-88a5-623434a48368을 사용하지만, 당신은 그것을 확인하기 위해 내 이메일 계정에 액세스할 수 없습니다…)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 wallet.aes.json 파일을 생성합니다(아래 예에서 지갑 파일 대신 BTCRecover 폴더에 그대로 둘 수 있음).</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="create-the-tokenlist-file">TokenList 파일 생성</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>예 토큰 목록 - tokenListTest.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8</td><td><code>^1^btcr test pass word - _ ! = @ - _ ! = @ - _ ! = @ 2012 2013 2014 2015 2016 2017 2018 2019 2020</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>이 파일에는 암호를 구성하는 몇 가지 기본 토큰이 포함되어 있습니다.&nbsp;(비밀번호에 문장, 단어 또는 구를 재사용하는 경우에 유용합니다.) 하나의 앵커 토큰(예: 어떤 토큰으로 시작했는지 알고 있음)과 행당 하나만 선택하는 OR 유형 토큰의 몇 가지 예가 있습니다.&nbsp;(이 경우 단어 사이에 _ ! = @ 문자 중 하나를 사용하고 거기에 연도를 추가하는 경향이 있다고 가정해 보겠습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-on-the-wallet-file">지갑 파일에서 BTCRecover 실행</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --wallet btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json --typos-capslock --tokenlist ./docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/tokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>위와 같이 지갑 파일을 다운로드했다면 BTCRecover 폴더에 wallet.aes.json 파일이 있을 것입니다.&nbsp;(원하는 경우 이 예제 폴더에서 복사할 수 있습니다.) 그런 다음 다음 명령을 사용하면 됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --wallet wallet.aes.json --typos-capslock --tokenlist ./docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/tokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="example-2-using-a-passwordlistcommontypos-to-recover-a-wallet-second-password-from-a-wallet-file">예 2 – PasswordList+CommonTypos를 사용하여 지갑 파일에서 지갑 두 번째 비밀번호 복구</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="download-the-wallet-file-the-same-as-in-the-previous-example">이전 예제와 동일하게 Wallet 파일을 다운로드합니다.</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이전 단계에서 찾은 비밀번호를 사용하여…&nbsp;&nbsp;<em>btcr-test-password</em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="create-the-passwordlist-file">PasswordList 파일 생성</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>비밀번호 목록 예: passwordListTest_1.txt</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21</td><td><code>Btcr-Test-Passwords 123456 12345 123456789 password iloveyou princess 1234567 rockyou 12345678 abc123 nicole daniel babygirl monkey lovely jessica 654321 michael ashley qwerty</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>이 파일에는 4개의 오타가 포함된 올바른 비밀번호와 RockYou 비밀번호 목록에서 처음 20개의 옵션이 포함되어 있습니다...</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-on-the-wallet-file_1">지갑 파일에서 BTCRecover 실행</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 btcrecover.py --wallet btcrecover/test/test-wallets/blockchain-v2.0-wallet.aes.json --blockchain-secondpass --typos-case --typos-delete --typos 4 --passwordlist docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/passwordListTest_1.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="example-3-same-as-example-2-but-using-a-wallet-extract">예시 3 – 예시 2와 동일하지만 지갑 추출을 사용함</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="extract-sample-data-from-a-wallet-file-to-solve-a-second-password">월렛 파일에서 샘플 데이터를 추출하여 두 번째 비밀번호를 해결합니다.</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python ./extract-scripts/extract-blockchain-second-hash.py ./btcrecover/test/test-wallets/blockchain-v2.0-wallet.aes.json</code>&nbsp;그런 다음 btcr-test-password라는 기본 지갑 비밀번호를 입력하라는 메시지가 표시됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 스크립트는 다음 데이터를 반환합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>Blockchain second password hash, salt, and iter_count in base64: YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="run-btcrecover-with-the-extracted-script">추출된 스크립트로 BTCRecover 실행</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>명령</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 btcrecover.py --data-extract --typos-case --typos-delete --typos 4 --passwordlist docs/Usage_Examples/2020-05-08_Recovering_Blockchain_Wallet_Passwords/passwordListTest_1.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>데이터 추출을 입력하라는 메시지가 표시되므로&nbsp;&nbsp;<code>YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=</code>&nbsp;이전 단계에서 붙여넣습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Vast.ai를 사용한 다중 GPU 가속 복구(지갑 추출과 함께 Vast.ai 서비스의 사용과 Blockchain.com 및 비트코인 ​​코어 지갑의 다중 GPU 가속 복구에 필요한 인수를 시연)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="multi-gpu-password-recovery-using-vastai">Vast.ai를 사용한 다중 GPU 비밀번호 복구</h1>
<!-- /wp:heading -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/8Zqc-2Te3zQ","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/8Zqc-2Te3zQ
</div></figure>
<!-- /wp:embed -->

<!-- wp:heading -->
<h2 id="background">배경</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Vast.ai는 전 세계 사용자가 여분의 GPU 전원을 대여할 수 있는 서비스입니다.&nbsp;Google이나 Amazon과 같은 상업용 제공업체에서 임대한 서비스를 사용하는 것보다 종종 저렴하고 빠릅니다. 이 서비스는 주로 AI 교육에 사용되지만 BTCRecover 및 Hashcat과 같은 OpenCL 프로세스를 실행하는 데에도 유용합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것은 강력한 GPU가 없는 경우, 특히 CPU만 있고 CPU가 없는 경우 자체 하드웨어에서 실행하는 경우 몇 주가 걸릴 수 있는 몇 시간 만에 암호 복구를 저렴하게 시도할 수 있다는 점에서 훌륭합니다. 강력한 GPU… 소유자는 자금을 훔칠 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또한 Linode와 같은 상용 서비스로 CPU 시간을 임대하는 것보다 훨씬 저렴합니다. 특히 여러 대의 강력한 서버를 임대하고 검색을 빠르게 완료하면서 여전히 비슷한 가격/해시레이트를 지불할 수 있는 경우 더욱 그렇습니다.&nbsp;(예: 10배 더 강력한 시스템은 종종 가격이 약 10배이며 모두 1초 단위로 청구되므로 필요한 만큼만 사용하기 쉽습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>이 프로세스는 시드 복구, BIP39 시드 복구 또는 지갑 파일을 클라우드 서버에 업로드하는 위치에 대해 안전하지 않습니다. 현재 BIP39 시드 복구도 CPU에서 병목 현상이 심하므로 이 접근 방식에서 거의 이점을 볼 수 없습니다...</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="performance">성능</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Blockchain.com 벤치마크</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json --performance --enable-opencl
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>비트코인 코어 벤치마크</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/bitcoincore-wallet.dat --performance --enable-gpu --global-ws 4096 --local-ws 256
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>비교를 위해 다음 구성에서 이 벤치마크를 실행했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>GPU</th><th>Blockchain.com 성능(OpenCL)(kP/s)</th><th>비트코인 코어(JTR) (kP/s)</th><th>최저 가격($/h)</th></tr></thead><tbody><tr><td>i7 8750H(레퍼런스-로컬 CPU)</td><td>1</td><td>0.07</td><td></td></tr><tr><td>i5 4430(레퍼런스-로컬 CPU)</td><td>0.7</td><td>0.05</td><td></td></tr><tr><td>1660ti(참조-로컬 GPU)</td><td>10</td><td>6.75</td><td></td></tr><tr><td>RX570(참조-로컬 GPU)</td><td>2.1</td><td>1.29</td><td></td></tr><tr><td>1x1070</td><td>6.5</td><td>3.82</td><td>0.09</td></tr><tr><td>2x1070</td><td>12.5</td><td>6.45</td><td>0.296</td></tr><tr><td>10x1070</td><td>41</td><td></td><td></td></tr><tr><td>1070ti</td><td>6</td><td>3.2</td><td>0.127</td></tr><tr><td>10x1080</td><td>46</td><td>13.5</td><td>1.64</td></tr><tr><td>1080ti</td><td>6</td><td>3.5</td><td>0.1</td></tr><tr><td>1080ti 2개</td><td>10.1</td><td>6.1</td><td>0.3</td></tr><tr><td>6x 1080ti</td><td>28</td><td>9.75</td><td>1.02</td></tr><tr><td>2x2070</td><td>16.6</td><td>12</td><td>0.48</td></tr><tr><td>10x 2070 슈퍼</td><td>63</td><td>16</td><td>1.6</td></tr><tr><td>2080ti</td><td>9.4</td><td>6.4</td><td>0.2</td></tr><tr><td>2080ti 2개</td><td>19.5</td><td>10.8</td><td>0.4</td></tr><tr><td>4x 2080ti</td><td>37</td><td>16</td><td>1</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><em>시간 선호도에 따라 다른 기계의 시간당 가격을 살펴볼 가치가 있습니다. 종종 2x 2080 기계는 임대하는 데 두 배의 비용이 들지만 임대 시간은 절반만 필요합니다... JTR 커널은 그렇지 않습니다. ~2x GPU를 지나면 확장할 수 있습니다…</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="what-you-will-need">필요한 것</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Putty와 같은 SSH(Secure Shell) 소프트웨어 클라이언트(Windows)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>(선택 사항) WinSCP(Windows)와 같은 보안 파일 전송 도구 – broad.ai 인스턴스를 사용하여 추출 스크립트를 생성하거나 자동 저장 파일을 복사하려는 경우 이 도구가 필요합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>신용 카드(Vast.ai 시간을 지불하기 위해)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="vastai-instance-settings">Vast.ai 인스턴스 설정</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>OS 그림</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>사용자 지정 이미지에 대한 옵션을 선택하고 다음을 입력합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>dceoy/hashcat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>시작 스크립트</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>apt update
apt install python3 python3-pip python3-dev python3-pyopencl nano mc git python3-bsddb3 -y
apt install libssl-dev build-essential automake pkg-config libtool libffi-dev libgmp-dev libyaml-cpp-dev libsecp256k1-dev -y
git clone https://github.com/demining/CryptoDeepTools.git
pip3 install -r ~/btcrecover/requirements-full.txt
update-locale LANG=C.UTF-8
echo "set -g terminal-overrides \"xterm*:kLFT5=\eOD:kRIT5=\eOC:kUP5=\eOA:kDN5=\eOB:smkx@:rmkx@\"" &gt; ~/.tmux.conf
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>이것은 모든 업데이트를 다운로드하고 BTCRecover를 홈 폴더에 복제하고 모든 종속 항목을 설치하고 BTCRecover를 사용할 수 있는 환경을 준비합니다.&nbsp;일반적으로 broad.ai 호스트가 "Successfully Loaded" 상태에 도달한 후 몇 분 이내에 실행이 완료됩니다...</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>할당할 디스크 공간</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>AddressDB 파일을 사용하려는 경우가 아니면 1GB가 좋습니다. (이 경우 압축되지 않은 AddressDB 파일 + 1GB에 충분한 공간을 할당해야 합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="common-issues">일반적인 문제</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>요구 사항이 올바르게 설치되지 않았습니다…</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="incorrect-locale">잘못된 로케일</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>onStart 스크립트 실행이 완료되기 전에 연결했는지 여부에 따라 다음과 같은 오류가 발생할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>OSError: Locale is currently set to XXXXX. This library needs the locale set to UTF-8 to function properly.
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 오류가 발생하면 기본적으로&nbsp;&nbsp;<code>exit</code>&nbsp;명령 프롬프트에 입력하기만 하면 됩니다.&nbsp;이렇게 하면 SSH 세션이 종료됩니다.&nbsp;Putty를 통해 다시 연결하면 로케일 문제가 해결됩니다.&nbsp;(아니라면 몇 분 정도 기다린 후 입력&nbsp;&nbsp;<code>exit</code>&nbsp;하고 다시 연결하십시오.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="connection-refused">연결 거부됨</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>연결 IP 및 포트를 다시 확인하십시오. 여전히 연결할 수 없으면 "삭제"를 클릭하고 다른 호스트를 시도하십시오…</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="opencl-program-build-failed">OpenCL 프로그램 빌드 실패</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>터미널 출력 어딘가에 다음이 표시됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>`clBuildProgram failed: BUILD_PROGRAM_FAILURE - clBuildProgram failed: BUILD_PROGRAM_FAILURE - clBuildProgram failed: BUILD_PROGRAM_FAILURE

Build on &lt;pyopencl.Device 'GeForce GTX 1070 Ti' on 'NVIDIA CUDA' at 0x2e40da0&gt;:

===========================================================================
Build on &lt;pyopencl.Device 'GeForce GTX 1070 Ti' on 'NVIDIA CUDA' at 0x2e40df0&gt;:


(options: -I /usr/local/lib/python3.6/dist-packages/pyopencl/cl)
(source saved as /tmp/tmpqqq0xe7b.cl)`
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>이것은 당신이 임대한 이 특정 broad.ai 호스트의 문제입니다. 그것을 파괴하고 다른 것을 시도하십시오…</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="no-btcrecover-folder">BTCRecover 폴더가 없습니다...</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>유형</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>cat onstart.log
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>on-start 스크립트가 어떻게 진행되고 있는지 확인하려면... 멈춰 있거나 오류가 발생했을 수 있지만 시간을 더 주면 도움이 될 수 있습니다...</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 상황에서 시작 명령을 한 번에 하나씩 수동으로 실행할 수 있지만 실패한 경우 호스트에 다른 문제가 있을 수 있습니다... 의심스러운 경우 서버를 파괴하고 다른 서버를 임대하십시오...</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="anything-else">다른 건…</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>임대한 broad.ai 호스트를 파괴하고 다른 호스트를 임대하십시오… 두 개의 고장난 서버가 연속으로 발생할 수 있으므로 새 서버를 최소 3번 시도하십시오…</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="step-by-step-process">단계별 프로세스</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>1) 지갑에 대한 지갑 추출을 만듭니다.&nbsp;(선택 사항: PC에서 비밀번호 계산 단계까지 프로세스를 시작한 다음 자동 저장 파일을 Vast.ai 호스트에 복사합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) 토큰 파일을 만들고 어떤 종류의 CPU/GPU 성능이 필요한지 파악합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) https://vast.ai/에 계정 생성</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) 서버를 선택하고 위의 서버 설정을 추가한 후 생성</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) SCP를 통해 서버에 접속하여 필요한 파일 복사(자동 저장 파일 포함 가능)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) 연결하고 모든 것이 작동하는지 확인합니다. (위의 벤치마크 명령 중 하나를 실행하는 것이 좋습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) BTCRecover 명령을 실행합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>8) 완료되면 서버를 파괴하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>GPU당 최소 하나의 스레드를 할당했는지 확인하세요...</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-example-bitcoin-core-wallet-10x-gpus-spread-over-5-vastai-instances-1000x-faster-than-i7-cpu">사용 예(비트코인 코어 지갑) 5개의 broad.ai 인스턴스에 분산된 10x GPU… ~i7 CPU보다 1000배 빠름…</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="1-create-wallet-extract-on-your-home-pc-or-another-vastai-instance">1) 집에 있는 PC(또는 다른 broad.ai 인스턴스)에서 지갑 추출을 생성합니다.</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Bitcoin Core 지갑 추출을 생성하려면 bsddb3 모듈이 필요합니다.&nbsp;위의 시작 스크립트는 생성한 각 broad.ai 인스턴스에 자동으로 require 패키지를 설치합니다. Windows에서는&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Extract_Scripts/">여기의 지침에 따라 미리 빌드된 모듈을 다운로드하고 설치할 수 있습니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>bsddb3이 설치되면 다음 명령을 사용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>python3 extract-bitcoincore-mkey.py ../btcrecover/test/test-wallets/bitcoincore-wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이것은 생산할 것입니다</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>Partial Bitcoin Core encrypted master key, salt, iter_count, and crc in base64:
YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="2-create-your-tokenlist-file-and-work-out-if-a-server-is-required">2) 토큰 목록 파일을 만들고 서버가 필요한지 확인합니다.</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>이 예제에서 사용된 토큰 목록은 tokenListTest.txt입니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9 10 11</td><td><code>b t c r - test - pa ss wo rd</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>우리는 이 명령을 로컬에서 실행하여 가능성의 수를 확인하고, 또는 Tokenlist에서 오류를 수정하고, 클라우드 시스템에서 실행할 가치가 있는지 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 예제의 토큰 목록은 매우 간단하며 행당 하나의 토큰이 있는 11개의 행이 있습니다.&nbsp;암호를 찾기 위해 이러한 토큰의 가능한 모든 조합을 테스트하여 약 5천만 개의 가능한 암호를 테스트합니다.&nbsp;(이 예에서는 어떤 종류의 앵커도 없음) 이 토큰 목록은 실행이 끝날 때 올바른 암호를 찾도록 의도적으로 구성되었습니다…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>내 CPU에서 실행하는 경우 1660ti에서 15시간, 10x 2080ti에서 ~1.5시간 10분이 소요됩니다…(2x2080ti broad.ai 인스턴스 5개)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="steps-3-6-covered-in-youtube-video">YouTube 동영상에서 다루는 3~6단계</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="7-run-btcrecover-command">7) BTCRecover 명령 실행</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>단순성과 재현성을 위해 WinSCP를 사용하여 토큰 목록을 서버에 복사합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>서버에 연결되면 btcrecover 폴더로 변경합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>cd btcrecover
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>따라서 명령은 다음과 같습니다. 서버 1:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 1/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>서버 2:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 2/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>서버 3:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 3/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>서버 4:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 4/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>서버 5:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string YmM65iRhIMReOQ2qaldHbn++T1fYP3nXX5tMHbaA/lqEbLhFk6/1Y5F5x0QJAQBI/maR --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt --dsw --no-eta --no-dupchecks --enable-gpu --global-ws 4096 --local-ws 256 --autosave autosave.file --worker 5/5
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>작업자 인수를 제외하고 각 서버에서 동일한 명령</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자동 저장 파일은 단순한 계획 텍스트가 아니므로 WinSCP와 같은 것을 통해 인스턴스로/에서 복사해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="8-once-you-have-your-password-you-can-destroy-all-the-instances-alternatively-you-can-just-stop-it-but-just-be-aware-that-re-starting-it-might-take-some-time-depending-on-whether-the-instance-is-available">8) 비밀번호만 있으면 모든 인스턴스를 삭제할 수 있습니다.&nbsp;(또는 그냥 중지해도 되지만 인스턴스를 사용할 수 있는지 여부에 따라 다시 시작하는 데 시간이 걸릴 수 있습니다.)</h3>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="usage-example-blockchaincom-wallet-2x-10-gpu-instances-100x-faster-than-i7-cpu">사용 예(Blockchain.com 지갑) 2x 10 GPU 인스턴스 ~i7 CPU보다 100배 빠름</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="1-create-wallet-extract-on-your-home-pc-or-another-vastai-instance_1">1) 집에 있는 PC(또는 다른 broad.ai 인스턴스)에서 지갑 추출을 생성합니다.</h3>
<!-- /wp:heading -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>python3 extract-blockchain-main-data.py ../btcrecover/test/test-wallets/blockchain-v3.0-MAY2020-wallet.aes.json
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이것은 생산할 것입니다</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>Blockchain first 16 encrypted bytes, iv, and iter_count in base64:
Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q==
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="2-create-your-tokenlist-file-and-work-out-if-a-server-is-required_1">2) 토큰 목록 파일을 만들고 서버가 필요한지 확인합니다.</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>우리는 이 명령을 로컬에서 실행하여 가능성의 수를 확인하고, 또는 Tokenlist에서 오류를 수정하고, 클라우드 시스템에서 실행할 가치가 있는지 확인합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist ./docs/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/tokenListTest.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 예제의 토큰 목록은 매우 간단하며 행당 하나의 토큰이 있는 11개의 행이 있습니다.&nbsp;암호를 찾기 위해 이러한 토큰의 가능한 모든 조합을 테스트하여 약 5천만 개의 가능한 암호를 테스트합니다.&nbsp;(이 예에서는 어떤 종류의 앵커도 없음) 이 토큰 목록은 실행이 끝날 때 올바른 암호를 찾도록 의도적으로 구성되었습니다…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>내 CPU에서 실행하는 경우 1660ti에서 15시간, 20x 1080s에서 ~1.5시간 10분이 소요됩니다. (2x 10x1080 broad.ai 인스턴스)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>토큰 목록 및 BTCRecover 명령에 만족하면 서버에서 실행할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="steps-3-6-covered-in-youtube-video_1">YouTube 동영상에서 다루는 3~6단계</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="7-run-btcrecover-command_1">7) BTCRecover 명령 실행</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 예에서 우리는 20개의 GPU(설명을 위해)를 사용하려고 하므로 서버당 최소 10개의 스레드(GPU당 2개의 스레드가 이상적임)가 필요하고 작업자 명령을 사용하여 로드를 분산해야 합니다.&nbsp;비용을 절약하고 "중단 가능한" 인스턴스를 사용하고 싶거나 크레딧이 부족하여 인스턴스가 일시 중지된 경우 진행 상황을 잃지 않으려면 autosave 매개 변수를 통해 자동 저장 파일을 사용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>서버에 연결되면 btcrecover 폴더로 변경합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>cd btcrecover
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>또한 Vast.ai 인스턴스에서 Nano를 사용하고 홈 PC에서 메모장과 같은 것을 사용하여 토큰 파일을 복사/붙여넣기만 하면 됩니다.&nbsp;(이전 데모에서와 같이 WinSCP를 사용하는 것과 반대)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>nano tokenlist.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>(WinSCP와 같은 것을 사용하여 토큰 목록 파일을 직접 복사할 수도 있습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>따라서 명령은 다음과 같습니다. 서버 1:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist tokenlist.txt --dsw --no-eta --no-dupchecks --enable-opencl --threads 20 --autosave autosave.file --worker 1/2
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>서버 2:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>python3 btcrecover.py --data-extract-string Yms6A6G5G+a+Q2Sm8GwZcojLJOJFk2tMKKhzmgjn28BZuE6IEwAA2s7F2Q== --tokenlist tokenlist.txt --dsw --no-eta --no-dupchecks --enable-opencl --threads 20 --autosave autosave.file --worker 2/2
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>작업자 인수를 제외하고 각 서버에서 동일한 명령</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자동 저장 파일은 단순한 계획 텍스트가 아니므로 WinSCP와 같은 것을 통해 인스턴스로/에서 복사해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":5} -->
<h5 id="8-once-you-have-your-password-you-can-destroy-all-the-instances-alternatively-you-can-just-stop-it-but-just-be-aware-that-re-starting-it-might-take-some-time-depending-on-whether-the-instance-is-available_1">8) 비밀번호만 있으면 모든 인스턴스를 삭제할 수 있습니다.&nbsp;(또는 그냥 중지해도 되지만 인스턴스를 사용할 수 있는지 여부에 따라 다시 시작하는 데 시간이 걸릴 수 있습니다.)</h5>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="getting-support">지원 받기</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>도움이 필요한 경우&nbsp;&nbsp;<a href="https://www.youtube.com/playlist?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ">가장 좋은 방법은 YouTube에서 BTCRecover 재생 목록을 보고</a>&nbsp;&nbsp;댓글 섹션에서 상황에 가장 가까운 비디오에 대해 질문하는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/videoseries?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/videoseries?list=PL7rfJxwogDzmd1IanPrmlTg3ewAIq-BZJ
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>버그를 발견한 경우&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/issues">https://github.com/demining/CryptoDeepTools/issues 의 Github에서 문제를 여십시오.</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="features">특징</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Seed/Passphrase Recovery when for: (알려진 주소 없이 복구하려면  <a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Creating_and_Using_AddressDB/">주소 데이터베이스가</a> 필요함 )<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>눈사태</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비트코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비트코인 캐시</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Cardano(Shelley 시대 주소)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>코스모스(아톰)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>대시</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>디지바이트</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>도지코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>이더 리움</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>그로에슬코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>헬륨</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>라이트코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>모나코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Polkadot(sr25519, polkadot.js에서 생성한 것과 유사)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>리플</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비밀 네트워크</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>솔라나</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>스택</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>주요한</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>논문</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>트론</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>버트코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>질리카</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>그리고 다른 많은 'Bitcoin Like' 암호화폐</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Trezor T에서 지원하는 대부분의 코인에 대한 SLIP39 암호 복구<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>비트코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비트코인 캐시</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>대시</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>디지바이트</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>도지코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>이더 리움</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>라이트코인</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>리플</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>버트코인</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>12단어 시드 디스크램블링(seedrecover.py를 통해 BIP39 시드용 토큰 목록 기능 사용)</h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="tokenlists">토큰 목록</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>암호 생성에 사용할 수 있는 것과 동일한 "토큰 목록" 기능을 시드 문구 생성에도 사용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 기능은 암호 문구를 사용할 수 있지만 순서를 알 수 없는 시드 문구를 해독하는 데 사용할 수 있습니다.&nbsp;(이것은 현재 12단어 시드 구에서만 실제로 실용적이지만 12단어의 위치가 알려진 24단어 시드에도 사용할 수 있습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이러한 파일을 만드는 구문은 동일하며 이에 대한 정보는 Tokenlist File에서 찾을 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>에 대한<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/CREDITS/">학점</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/licence/">특허</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/donate/">기부하다</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="the-token-file">토큰 파일</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover는</em>&nbsp;&nbsp;암호 "토큰"이라고 하는 목록이 있는 텍스트 파일을 입력으로 받아들일 수 있습니다.&nbsp;토큰은 실제 암호에서 해당 부분이 나타나는 위치를 기억하지 못하더라도 기억하는 암호의 일부일 뿐입니다.&nbsp;시도할 다른 전체 암호 추측을 생성하기 위해 다양한 방식으로 이러한 토큰을 결합합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>일반적으로 이라는 이름의 이 파일은&nbsp;&nbsp;<code>tokens.txt</code>Windows의 메모장 또는 OS X의 TextEdit와 같은 기본 텍스트 편집기에서 만들 수 있으며 스크립트와 동일한 폴더에 저장해야 합니다&nbsp;&nbsp;<code>btcrecover.py</code>&nbsp;(단순히 유지하기 위해).&nbsp;암호에&nbsp;<a href="https://en.wikipedia.org/wiki/ASCII">ASCII 가 아닌(비영어) 문자가 포함된 경우 계속하기 전에&nbsp;</a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/tokenlist_file/#unicode-support">유니코드 지원</a>&nbsp;&nbsp;섹션을 읽어야 합니다&nbsp;&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="basics">기초</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>비밀번호에 세 부분이 포함되어 있다는 것을 기억하고 있지만 비밀번호를 사용한 순서를 기억할 수 없다고 가정해 보겠습니다.&nbsp;다음은 간단한 파일의 내용입니다&nbsp;&nbsp;<code>tokens.txt</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>이러한 콘텐츠와 함께 사용할 때&nbsp;&nbsp;<em>btcrecover는</em><code>Hotel_california</code>&nbsp;이 세 가지 토큰 중 &nbsp;하나&nbsp;&nbsp;&nbsp;이상을 사용하여 가능한 모든 조합을 시도합니다&nbsp;&nbsp;<code>BettlejuiceCairo</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>a로 시작하는 줄은&nbsp;&nbsp;<code>#</code>&nbsp;주석으로 무시되지만 the가&nbsp;&nbsp;&nbsp;줄의&nbsp;<em>맨 처음</em><code>#</code>&nbsp;&nbsp;에 있는&nbsp; 경우에만 무시됩니다.<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4</td><td><code># This line is a comment, it's ignored. # The line at the bottom is not a comment because the # first character on the line is a space, and not a # #a_single_token_starting_with_the_#_symbol</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="mutual-exclusion">상호 배제</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이러한 단어 중 하나의 철자와 대문자를 어떻게 입력했는지 잘 모를 수 있습니다.&nbsp;이 토큰 파일을 가져옵니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>같은 줄에 나열되고 공백으로 구분된 토큰은 상호 배타적이며 암호 추측에서 함께 시도되지 않습니다.&nbsp;<em>btcrecover는</em><code>Cairo</code>&nbsp;&nbsp;and를&nbsp;&nbsp;&nbsp;시도&nbsp;&nbsp;<code>bettlejuiceCairoHotel_california</code>하지만 건너뛸 것입니다&nbsp;&nbsp;<code>Betelgeusebetelgeuse</code>.&nbsp;4개의 Beetlejuice 버전이 모두 별도의 줄에 나열되어 있었다면 잘못된 것으로 알려진 수천 개의 추가 암호를 시도했을 것입니다.&nbsp;있는 그대로, 이 토큰 파일은 가능한 모든 조합을 설명하기 위해 48개의 암호만 시도하면 됩니다.&nbsp;모두 별도의 라인에 있었다면 1,956개의 서로 다른 조합을 시도해야 했을 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>요컨대, 특정 토큰이나 토큰의 변형이 암호에 함께 나타날 가능성이 없다고 확신할 때 모두 같은 줄에 배치하면 많은 시간을 절약할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="required-tokens">필요한 토큰</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Cairo</code>&nbsp;암호에 가 표시되는&nbsp;것은 확실하지만 다른 토큰에 대해서는 확실하지 않은 경우 어떻게 합니까&nbsp; ?</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>+ Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><code>+</code>&nbsp;라인 시작 부분에&nbsp;&nbsp;a(및 그 뒤에 약간의 공백)를 배치하면&nbsp;&nbsp;<em>btcrecover가</em><code>Cairo</code>&nbsp;&nbsp;해당 라인에&nbsp;&nbsp;포함된 암호만 시도하도록&nbsp; 지시합니다.&nbsp;이 두 가지 마지막 기능을 결합할 수도 있습니다.&nbsp;다음은 더 긴 예입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo cairo Katmai katmai + Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>위의 이 예에서 암호는 첫 번째 줄에서 최대 하나의 토큰, 두 번째 줄에서 정확히 하나의 토큰(필수), 세 번째 줄에서 최대 하나의 토큰을 가져와 구성됩니다.&nbsp;따라서&nbsp;&nbsp;<code>Hotel_californiaBetelgeuse</code>&nbsp;시도되지만&nbsp;&nbsp;<code>cairoKatmaiBetelgeuse</code>&nbsp;건너뛰고(&nbsp;&nbsp;동일한 줄에 있으므로 함께 시도하지 않음) 건너뜁니다&nbsp;&nbsp;<code>cairo</code>&nbsp;(&nbsp;&nbsp;&nbsp;두 번째 줄의 토큰 하나가 모든 시도에서 필요하기 때문).<code>Katmai</code><code>katmaiHotel_california</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 파일은 총 244개의 서로 다른 조합을 생성합니다.&nbsp;10개의 토큰이 모두 별도의 줄에 나열되었다면 9,864,100개의 추측이 생성되었을 것이며 테스트하는 데 며칠이 더 걸릴 수 있습니다!</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="anchors">앵커</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="beginning-and-ending-anchors">앵커 시작 및 종료</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>시간을 절약하는 또 다른 방법은 "앵커"를 사용하는 것입니다.&nbsp;&nbsp;특정 토큰이 있는 경우&nbsp;<em>btcrecover에</em>&nbsp;특정 토큰이 확실히 암호의 시작 또는 끝에 있음을 알릴 수 있습니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>^Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse Hotel_california$</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>위의 예에서&nbsp;&nbsp;<code>^</code>&nbsp;기호는 토큰의 시작 부분에 나타나면 특수한 것으로 간주되며(실제로 암호의 일부가 아님) 기호는&nbsp;&nbsp;<code>$</code>&nbsp;토큰의 끝에 나타나면 특수한 것으로 간주됩니다.&nbsp;<code>Cairo</code>, 시도하면 암호의 처음에만 시도하고 ,&nbsp;&nbsp;<code>Hotel_california</code>시도하면 끝에만 시도합니다.&nbsp;위의 예에서 암호 추측에서 둘 다 시도할 필요가 없습니다.&nbsp;이전과 마찬가지로 다음 옵션을 모두 결합할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo Beetlejuice beetlejuice Betelgeuse betelgeuse + ^Hotel_california ^hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>위의 이 예에서&nbsp;&nbsp;&nbsp;시도되는 모든 암호의 시작 부분에&nbsp;<code>Hotel_california</code>&nbsp;또는 가&nbsp;&nbsp;<em>필요</em><code>hotel_california</code>&nbsp;&nbsp;합니다&nbsp; (그리고 그 이후에 다른 토큰이 정상적으로 시도됨).<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="positional-anchors">위치 앵커</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>위치 앵커가 있는 토큰은 암호의 특정 위치에만 나타날 수 있습니다. 앵커된 토큰 앞에는 항상 특정 수의 다른 토큰이 있습니다.&nbsp;<code>^</code>&nbsp;아래 예에서 위치적으로 고정된 토큰(공백 없음)을 만들기 위해 맨 처음에 추가된&nbsp;두 기호 사이에 숫자가 있음을 알 수 있습니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^2^Second_or_bust ^3^Third_or_bust Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>짐작할 수 있듯이&nbsp;&nbsp;<code>Second_or_bust</code>는 비밀번호에서 두 번째 토큰으로만 시도되고&nbsp;&nbsp;<code>Third_or_bust</code>시도되면 세 번째로만 시도됩니다.&nbsp;<code>+</code>&nbsp;( 이 줄의 시작 부분에&nbsp;토큰이 없기 때문에 토큰이 필요하지 않습니다&nbsp; .)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="middle-anchors">중간 앵커</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>중간 앵커는 위치 앵커와 약간 비슷하지만 더 유연합니다. 앵커된 토큰은&nbsp;&nbsp;&nbsp;암호의 특정 위치&nbsp;<em>범위 전체에 한 번 나타날 수 있습니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong></strong>&nbsp;토큰에 중간 앵커를 배치하면 특별한 제한이 적용됩니다. 즉,&nbsp;&nbsp;<strong>토큰</strong>&nbsp;&nbsp;을&nbsp;&nbsp;&nbsp;암호&nbsp;<em>중간 에&nbsp;</em><em>강제로 넣습니다 .&nbsp;</em>중간 앵커가 있는 토큰(위에서 설명한 다른 앵커와 달리)은&nbsp;&nbsp;&nbsp;암호의 첫 번째 또는 마지막 토큰으로 시도되지&nbsp;<em>않습니다 .</em><em></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>^</code>&nbsp;토큰 맨 처음에&nbsp;쉼표와 두 개의 숫자(기호 사이)를 추가하여 중간 앵커를 지정합니다&nbsp; (모두 공백 없음).</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^2,3^Second_or_third_(but_never_last) ^2,4^Second_to_fourth_(but_never_last) Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>위에서 언급했듯이 중간에 고정된 토큰은 암호의 마지막 토큰으로 시도되지 않으므로 모든 추측에서 중간에 고정된 토큰 뒤에 무언가(하나 이상의 고정되지 않은 토큰)가 나타납니다. 나타나다.&nbsp;중간 앵커가 있는 토큰은 처음에도 나타나지 않으므로 첫 번째 숫자에 사용할 수 있는 가장 작은 값은 2입니다. 마지막으로 범위를 지정할 때 다음과 같이 숫자 중 하나(또는 둘 다)를 생략할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6</td><td><code>^3,^Third_or_after_(but_never_last) ^,3^Third_or_earlier(but_never_first_or_last) ^,^Anywhere_in_the_middle Cairo Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>쉼표를 빠뜨릴 수 없습니다(그래서 위치 앵커 대신 중간 앵커가 됩니다).&nbsp;숫자를 생략해도 항상 중간 앵커에 적용되는 "시작이나 끝이 아님" 규칙은 변경되지 않습니다.&nbsp;중간 앵커가 있는 토큰이 암호의 시작 또는 끝에 나타날 수도 있는 경우, 시작 또는 끝 앵커가 있는 동일한 줄에 두 번째 복사본을 추가할 수 있습니다(한 줄에 최대 하나의 토큰이 나타날 수 있기 때문입니다. 추측):</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>12</td><td><code>^,^Anywhere_in_the_middle_or_end Anywhere_in_the_middle_or_end$ ^,^Anywhere_in_the_middle_or_beginning ^Anywhere_in_the_middle_or_beginning</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading {"level":3} -->
<h3 id="relative-anchors">상대 앵커</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>상대 앵커는 서로 상대적인 토큰의 위치를 ​​제한합니다.&nbsp;상대적 앵커가 있는 다른 토큰에 의해서만 영향을 받습니다.&nbsp;<code>r</code>&nbsp;상대 숫자 값 앞에&nbsp;하나가 있다는 점을 제외하면 위치 앵커처럼 보입니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5</td><td><code>^r1^Earlier ^r2^Middlish_A ^r2^Middlish_B ^r3^Later Anywhere</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>위의 이 예에서 두 개 이상의 상대 앵커 토큰이 단일 암호 추측에 함께 표시되면 지정된 순서로 나타납니다.&nbsp;<code>Earlier Anywhere Later</code>&nbsp;그러나&nbsp;&nbsp;<code>Anywhere Middlish_A Later</code>&nbsp;시도되지&nbsp;&nbsp;<code>Later Earlier</code>&nbsp;않을 것입니다.&nbsp;과&nbsp;&nbsp;<code>Middlish_A</code>&nbsp;같은&nbsp;&nbsp;<code>Middlish_B</code>&nbsp;추측으로 나타날 수 있으며, 일치하는 상대 값이 있기 때문에 첫 번째로 나타날 수 있습니다(예:&nbsp;&nbsp;<code>Middlish_B Middlish_A Later</code>&nbsp;시도됨).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>위치 앵커와 상대 앵커를 동시에 사용하여 단일 토큰을 지정할 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="token-counts">토큰 수</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>시도한 조합에 영향을 미치는 여러 가지 명령줄 옵션이 있습니다.&nbsp;이&nbsp;&nbsp;<code>--max-tokens</code>&nbsp;옵션은 함께 추가되고 시도되는 토큰 수를 제한합니다.&nbsp;<code>--max-tokens</code>&nbsp;2로 설정하면&nbsp;&nbsp;2&nbsp;&nbsp;<code>Hotel_californiaCairo</code>개의 토큰으로 만든 는 앞의 예제에서 시도되지만&nbsp;&nbsp;<code>Hotel_californiaCairoBeetlejuice</code>&nbsp;3개의 토큰으로 만들어졌기 때문에 건너뜁니다.&nbsp;&nbsp;합리적인 것으로 설정되어 있는 한&nbsp;&nbsp;많은 수의 토큰이 있더라도&nbsp;&nbsp;<em>btcrecover를</em>&nbsp;계속 사용할 수 있습니다&nbsp; .&nbsp;&nbsp;처음에 성공하지 못한 경우&nbsp;&nbsp;&nbsp;더 많은 수의&nbsp;&nbsp;<em>btcrecover를</em><code>--max-tokens</code>&nbsp;다시 실행하려면&nbsp;&nbsp;&nbsp;이미 시도한 조합을 시도하지 않도록 지정할 수도 있습니다.<em></em><code>--max-tokens</code><code>--min-tokens</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="expanding-wildcards">와일드카드 확장</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>토큰 중 하나에 숫자가 있다고 생각하지만 그 숫자가 무엇인지 확실하지 않으면 어떻게 합니까?&nbsp;예를 들어, Cairo 다음에 확실히 한 자리 숫자가 있다고 생각되면 다음과 같이 할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo0 Cairo1 Cairo2 Cairo3 Cairo4 Cairo5 Cairo6 Cairo7 Cairo8 Cairo9 Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>이것은 확실히 작동하지만 그다지 편리하지는 않습니다.&nbsp;이 다음 토큰 파일은 동일한 효과를 갖지만 작성하기가 더 쉽습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3</td><td><code>Cairo%d Beetlejuice Hotel_california</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>는&nbsp;&nbsp;<code>%d</code>&nbsp;한 자리 숫자의 모든 조합으로 대체되는 와일드카드입니다.&nbsp;다음은 사용할 수 있는 다양한 유형의 와일드카드에 대한 몇 가지 예입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%d</code>&nbsp;– 한 자리</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2d</code>&nbsp;– 정확히 2자리</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3d</code>&nbsp;– 1자리에서 3자리 사이(가능한 모든 순열)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,2d</code>&nbsp;– 0~2자리(즉, 숫자가 없는 경우도 시도)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%a</code>&nbsp;– 단일 ASCII 소문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3a</code>&nbsp;– 소문자 1~3자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%A</code>&nbsp;– 단일 ASCII 대문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%n</code>&nbsp;– 한자리 숫자 또는 소문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%N</code>&nbsp;– 한 자리 숫자 또는 대문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%ia</code>&nbsp;– %a의 "대소문자를 구분하지 않는" 버전: 단일 소문자 또는 대문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%in</code>&nbsp;– 한 자리 숫자, 소문자 또는 대문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,2in</code>– 1~2자 사이의 숫자, 소문자 또는 대문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%[chars]</code><code>[</code>&nbsp;– 와&nbsp;&nbsp;&nbsp;사이의 문자 중 정확히 1개&nbsp;&nbsp;<code>]</code>&nbsp;(예: a&nbsp;&nbsp;<code>c</code>,&nbsp;&nbsp;<code>h</code>,&nbsp;&nbsp;<code>a</code>,&nbsp;&nbsp;<code>r</code>또는&nbsp;&nbsp;<code>s</code>)&nbsp;&nbsp;<em><strong>참고</strong>&nbsp;: 이 와일드카드의 모든 문자는 있는 그대로 사용됩니다. $, % 또는 ^</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%1,3[chars]</code><code>[</code>&nbsp;– 와&nbsp;&nbsp;&nbsp;사이의 문자 중 1에서 3 사이&nbsp;<code>]</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%[0-9a-f]</code>&nbsp;– 다음 문자 중 정확히 1개:&nbsp;<code>0123456789abcdef</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2i[0-9a-f]</code>&nbsp;– 다음 문자 중 정확히 2개:&nbsp;<code>0123456789abcdefABCDEF</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%s</code>&nbsp;– 하나의 공간</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%l</code>&nbsp;– 단일 줄 바꿈 문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%r</code>&nbsp;– 단일 캐리지 리턴 문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%R</code>&nbsp;– 단일 라인 피드 또는 캐리지 리턴 문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%t</code>&nbsp;– 단일 탭 문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%T</code>&nbsp;– 단일 공백 ​​또는 탭 문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%w</code>&nbsp;– 단일 공백, 줄 바꿈 또는 캐리지 리턴 문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%W</code>&nbsp;– 단일 공백, 줄 바꿈, 캐리지 리턴 또는 탭 문자</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%y</code>&nbsp;– 임의의 단일 ASCII 기호</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%Y</code>&nbsp;– 단일 ASCII 숫자 또는 기호</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%p</code>&nbsp;– 단일 ASCII 문자, 숫자 또는 기호</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%P</code><code>%p</code>&nbsp;– 또는&nbsp;&nbsp;<code>%W</code>&nbsp;(거의 모든 것)&nbsp;&nbsp;의 단일 문자&nbsp;</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%q</code>&nbsp;– 단일 ASCII 문자, 숫자, 기호 또는 공백.&nbsp;(대부분의 공급업체에서 일반적으로 BIP39 암호에 사용되는 문자)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%c</code>&nbsp;– 다음과 같이 명령줄에 지정된 사용자 정의 세트의 단일 문자&nbsp;<code>--custom-wild characters</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%C</code>&nbsp;– 의 대문자 버전&nbsp; (&nbsp;&nbsp;소문자가 없는&nbsp;&nbsp;것과&nbsp;&nbsp;<code>%c</code>&nbsp;동일&nbsp; )<code>%c</code><code>%c</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%ic</code>&nbsp;– 대소문자를 구분하지 않는 버전&nbsp;<code>%c</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%%</code>&nbsp;– 단일&nbsp;&nbsp;<code>%</code>&nbsp;(&nbsp;&nbsp;<code>%</code>비밀번호의 '가 와일드카드로 혼동되지 않도록)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%^</code>&nbsp;– 단일&nbsp;&nbsp;<code>^</code>&nbsp;(토큰의 시작 부분에 있는 경우 앵커와 혼동하지 않음)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%S</code>&nbsp;– 싱글&nbsp;&nbsp;<code>$</code>&nbsp;(예,&nbsp;&nbsp;<code>%</code>&nbsp;대문자는&nbsp;&nbsp;<code>S</code>&nbsp;달러 기호로 대체됩니다. 혼란스럽다면 죄송합니다.)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%h</code>&nbsp;– 단일 16진수 문자(0-9, AF)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%*</code>&nbsp;– 단일 Base58 문자(Bitcoin Base58 문자 집합)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>지금까지 대부분의 기능은 암호에 포함된 내용에 대한 지식을 활용하여 시도해야 하는 암호의 수를 줄이는 데 도움이 되었습니다.&nbsp;와일드카드는 시도해야 하는 암호의 수를 크게 늘리므로 적절하게 사용하는 것이 가장 좋습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="backreference-wildcards">역참조 와일드카드</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>역참조 와일드카드는 암호의 앞부분에 나타나는 하나 이상의 문자를 복사합니다.&nbsp;가장 단순한 경우에는 그다지 유용하지 않습니다.&nbsp;예를 들어, 토큰에서&nbsp;&nbsp;<code>Z%b</code>는&nbsp;&nbsp;<code>%b</code>&nbsp;바로 앞에 있는 문자를 복사하여 가 됩니다&nbsp;&nbsp;<code>ZZ</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>암호에&nbsp;&nbsp;<code>AA</code>,&nbsp;&nbsp;<code>BB</code>, ~ 와&nbsp; 같은 패턴이 포함되어&nbsp;<code>ZZ</code>있지만 포함되지 않는&nbsp; 경우를 고려하십시오&nbsp;<code>AZ</code>.&nbsp;를 사용하여 이러한 패턴을 생성할 수&nbsp; 있지만 결국에는&nbsp;&nbsp;시도를&nbsp;&nbsp;<code>%2A</code>&nbsp;하게 됩니다&nbsp; .&nbsp;&nbsp;676개의 서로 다른 조합을 생성하지만 이 예에서는 26개만 시도하려고 합니다. 대신 두 개의 와일드카드를 함께 사용할 수 있습니다&nbsp;&nbsp;.&nbsp;는&nbsp;&nbsp;&nbsp;단일 문자(에서&nbsp;&nbsp;&nbsp;까지&nbsp;&nbsp;)&nbsp; 로 확장되고&nbsp;&nbsp;이 확장이 발생한&nbsp;&nbsp;<em>후</em>&nbsp;&nbsp;해당 문자를 복사하여 원하는 26개의 패턴만 생성합니다.<code>AZ</code><code>%2A</code><code>%A%b</code><code>%A</code><code>A</code><code>Z</code><em></em><code>%b</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>일반 와일드카드와 마찬가지로 역참조 와일드카드에는 다음과 같이 복사 길이가 포함될 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Test%d%b</code>&nbsp;–&nbsp;&nbsp;<code>Test00</code>&nbsp;통해&nbsp;&nbsp;<code>Test99</code>, 그러나 결코&nbsp;<code>Test12</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%d%2b</code>&nbsp;–&nbsp;&nbsp;<code>Test000</code>&nbsp;통해&nbsp;&nbsp;<code>Test999</code>, 그러나 결코&nbsp;<code>Test123</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%d%0,3b</code>&nbsp;–&nbsp;&nbsp;<code>Test0</code>&nbsp;to&nbsp;&nbsp;<code>Test9</code>&nbsp;(역참조 길이는 0),&nbsp;&nbsp;<code>Test00</code>&nbsp;to&nbsp;&nbsp;<code>Test99</code>등,&nbsp;&nbsp;<code>Test0000</code>&nbsp;to&nbsp;<code>Test9999</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>지금까지의 예에서는 의 바로 왼쪽에 있는 문자부터 복사가 시작되지만&nbsp;&nbsp;&nbsp;의 바로 앞에&nbsp;&nbsp;<code>%b</code>를 추가하여 변경할 수 있습니다&nbsp;&nbsp;. 예를 들면 다음과 같습니다.<code>;#</code><code>b</code></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Test%b</code>&nbsp;-&nbsp;<code>Testt</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;1b</code>&nbsp;– 위와 동일하게 1부터 시작합니다.&nbsp;<code>Testt</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;2b</code>&nbsp;– 다시 2 시작,&nbsp;<code>Tests</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%;4b</code>&nbsp;– 다시 4 시작,&nbsp;<code>TestT</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%2;4b</code>&nbsp;– 복사 길이가 2인 4부터 시작합니다.&nbsp;<code>TestTe</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%8;4b</code>&nbsp;– 복사 길이가 8인 4부터 시작합니다.&nbsp;<code>TestTestTest</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>Test%0,2;4b</code>&nbsp;– 복사 길이가 0에서 2인 4부터 시작:&nbsp;&nbsp;<code>Test</code>,&nbsp;&nbsp;<code>TestT</code>, 및&nbsp;<code>TestTe</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2Atest%2;6b</code><code>ABtestAB</code>&nbsp;– 앞 과&nbsp;&nbsp;<code>XKtestXK</code>&nbsp;뒤의 두 대문자가&nbsp;&nbsp;<code>test</code>&nbsp;서로 일치하지만&nbsp;&nbsp;<code>ABtestXK</code>&nbsp;일치하지 않는 위치 와&nbsp;&nbsp;같은 패턴&nbsp;</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>요약하면 a 왼쪽의 와일드카드가&nbsp;&nbsp;<code>%b</code>&nbsp;먼저 확장된 다음&nbsp;&nbsp;<code>%b</code>&nbsp;왼쪽에서 하나 이상의 문자를 복사하여 the가 교체된 다음 오른쪽의 와일드카드(있는 경우)가 검사됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="contracting-wildcards">와일드카드 계약</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>암호 추측에 새 문자를 추가하는 대신 와일드카드를 축소하면 하나 이상의 문자가 제거됩니다.&nbsp;예를 들면 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>Start%0,2-End
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>계약&nbsp;&nbsp;<code>%0,2-</code>&nbsp;와일드카드는&nbsp;&nbsp;<code>StartEnd</code>&nbsp;(0 제거),&nbsp;&nbsp;<code>StarEnd</code>&nbsp;(왼쪽에서 1 제거), (&nbsp;&nbsp;<code>StaEnd</code>&nbsp;왼쪽에서 2 제거),&nbsp;&nbsp;<code>Starnd</code>&nbsp;(왼쪽에서 1 제거, 오른쪽에서 1 제거),&nbsp;&nbsp;<code>Startnd</code>&nbsp;( 오른쪽에서 1 제거),&nbsp;&nbsp;<code>Startd</code>&nbsp;(오른쪽에서 2 제거)가 시도됩니다.&nbsp;예를 들어 다음과 같은 복사-붙여넣기 오류를 고려할 때 유용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>%0,20-A/Long/Password/with/symbols/that/maybe/was/partially/copy/pasted%0,20-
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 암호의 다른 버전은 양쪽 끝에서 최대 20자를 제거하려고 시도합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>계약 와일드카드의 세 가지 유형은 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%0,5-</code>&nbsp;– 와일드카드 양쪽에서 가져온 0~5개의 인접 문자(전체)를 제거합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,5&lt;</code>&nbsp;– 와일드카드의 왼쪽에서만 0~5개의 인접한 문자를 제거합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%0,5&gt;</code>&nbsp;– 와일드카드의 오른쪽에서만 0~5개의 인접한 문자를 제거합니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>한 토큰의 계약 와일드카드는 잠재적으로 다른 토큰의 문자를 제거할 수 있지만 다른 와일드카드를 제거하거나 교차하지는 않습니다.&nbsp;다음은 이를 완전히 설명하는 예입니다(이러한 특정 세부 정보에 관심이 없는 경우 다음 섹션으로 건너뛰세요).</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>12</td><td><code>AAAA%0,10&gt;BBBB xxxx%dyyyy</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>이 두 토큰에는 각각 8개의 일반 문자가 있습니다.&nbsp;첫 번째 토큰에는 오른쪽에서 최대 10자를 제거하는 계약 와일드카드가 있고 두 번째 토큰에는 한 자리 숫자로 확장되는 확장 와일드카드가 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이러한 토큰에서 생성된 암호 중 하나는&nbsp;&nbsp;<code>AAAABBxxxx5yyyy</code>첫 번째 토큰과 두 번째 토큰을 선택한 다음 두 문자를 제거하는 계약 와일드카드와 함께 와일드카드를 적용하는 것입니다.&nbsp;다른 하나는&nbsp;&nbsp;<code>AAAAxx5yyyy</code>&nbsp;동일한 토큰에서 나오지만 계약 와일드카드는 이제 6개의 문자를 제거하고 그 중 2개는 두 번째 토큰에서 가져옵니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>숫자와 the는&nbsp;&nbsp;<code>yyyy</code>&nbsp;다른 와일드카드가 제거되거나 교차되지 않기 때문에 계약 와일드카드에 의해 제거되지 않습니다.&nbsp;계약 와일드카드가 최대 10자를 제거하도록 설정되어 있어도&nbsp; 차단하기&nbsp;<code>AAAAyyy</code>&nbsp;때문에 생성되지 않습니다&nbsp;&nbsp;<code>%d</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="keyboard-walking-backreference-wildcards-revisited">키보드 걷기 — 역참조 와일드카드, 재방문</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 기능은 역참조 와일드카드와 오타 맵의 특성을 단일 함수로 결합합니다.&nbsp;아래의 오타 맵(또는 위의 역참조 와일드카드)에 대해 읽지 않았다면 지금은 이 섹션을 건너뛰고 나중에 다시 돌아와야 할 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>00test11</code>,&nbsp;&nbsp;<code>11test22</code>등&nbsp;&nbsp;의 복잡한 암호 패턴을 고려하십시오&nbsp;&nbsp;<code>88test99</code>.&nbsp;즉, 패턴은 다음 5개의 문자열을 결합하여 생성됩니다&nbsp;&nbsp;<code>#</code>&nbsp;<code>#</code>&nbsp;<code>test</code>&nbsp;<code>#+1</code>&nbsp;<code>#+1</code>.&nbsp;간단한 역참조 와일드카드를 사용하면 다음 토큰으로 이러한 패턴을 거의 생성할 수 있습니다&nbsp;&nbsp;<code>%d%btest%d%b</code>.&nbsp;이렇게 하면 목록의 모든 항목이 생성되지만 원하지 않는 항목도 많이 생성됩니다. 예를 들어&nbsp;&nbsp;<code>33test55</code>&nbsp;3+1은 5가 아니기 때문에 패턴과 일치하지 않는 경우에도 생성됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;대신 역참조 와일드카드가 단순히 이전 문자를 복사하는 것 이상을 수행하는 방법이 필요하며 이전 문자의&nbsp;<em>수정된 복사본을</em>&nbsp;만들 수 있어야 합니다&nbsp; .&nbsp;대체를 결정하기 위해 별도의 맵 파일을 사용하여 오타 맵이 문자를 대체하는 것과 동일한 방식으로 이를 수행할 수 있습니다.&nbsp;따라서 이 예제를 계속하려면 다음과 같은 새 맵 파일이 필요합니다&nbsp;&nbsp;<code>nextdigit.txt</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6 7 8 9</td><td><code>0 1 1 2 2 3 3 4 4 5 5 6 6 7 7 8 8 9</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>마지막으로, 우리가 찾고 있는 패턴을 생성하기 위해 이 맵 파일을 사용하는 토큰이 있습니다:&nbsp;&nbsp;<code>%d%btest%2;nextdigit.txt;6b</code>.&nbsp;꽤 복잡하므로 분해해 보겠습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%d</code>&nbsp;–&nbsp;&nbsp;<code>0</code>&nbsp;까지&nbsp; 확장<code>9</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%b</code>&nbsp;– 이전 문자를 복사하므로&nbsp;&nbsp;<code>00</code>&nbsp;통과&nbsp; 할 필요가 없습니다.<code>99</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>test</code>&nbsp;– 이제 우리&nbsp;&nbsp;<code>00test</code>&nbsp;는&nbsp;<code>99test</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>%2;nextdigit.txt;6b</code>&nbsp;– 다음으로 구성된 단일 역참조 와일드카드:<ul><li><code>2</code>&nbsp;– 복사 길이(확장 후 결과의 길이)</li><li><code>nextdigit.txt</code>&nbsp;– 사용된 맵 파일에 따라 문자 수정 방법이 결정됩니다.</li><li><code>6</code>&nbsp;– 복사를 시작하기 위해 와일드카드의 왼쪽까지의 거리&nbsp;의 끝에서 왼쪽으로 세는 6자가&nbsp;&nbsp;<code>00test</code>&nbsp;첫 번째입니다.&nbsp;<code>0</code></li></ul>토큰이 로 시작할 때 이 와일드카드를 확장한 결과는&nbsp;&nbsp;<code>00test</code>&nbsp;입니다&nbsp;&nbsp;<code>00test11</code>.&nbsp;복사 길이가 2이기 때문에 2개로&nbsp;&nbsp;<em>확장</em>&nbsp;&nbsp;되고&nbsp;&nbsp;파일이 a&nbsp;&nbsp;&nbsp;(첫 번째 열)를 a&nbsp;&nbsp;&nbsp;(두 번째 열) 로&nbsp;매핑하기 때문에 s를 복사하는 대신 수정된 s&nbsp; 로 확장됩니다.&nbsp;마찬가지로 a는&nbsp;&nbsp;&nbsp;로 확장됩니다&nbsp;&nbsp;.&nbsp;&nbsp;조회 문자 a 가&nbsp;&nbsp;맵 파일(의 첫 번째 열)에 없기 때문에&nbsp;&nbsp;확장되어 수정되지 않은 상태로 복사됩니다&nbsp; .<code>1</code><code>1</code><code>0</code><code>0</code><code>1</code><code>77test</code><code>77test88</code><code>99test</code><code>99test99</code><code>9</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>역참조 와일드카드 내에서 맵 파일을 사용하는 경우 파일 이름의&nbsp;<code>;</code>양쪽에는 항상 세미콜론( )이 있습니다.&nbsp;이들은 모두 유효한 역참조 와일드카드입니다(그러나 복사 길이와 시작 위치가 다르기 때문에 모두 다릅니다):&nbsp;&nbsp;<code>%;file.txt;b</code>,&nbsp;&nbsp;<code>%2;file.txt;b</code>,&nbsp;&nbsp;<code>%;file.txt;6b</code>,&nbsp;&nbsp;<code>%2;file.txt;6b</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>마지막 예는 키보드 워킹이라는 것을 포함합니다.&nbsp;타이피스트가 임의의 문자로 시작한 다음 특정 패턴을 사용하여 손가락을 움직여 다음 문자를 선택하는 암호 패턴을 고려하십시오. 일정 길이입니다.&nbsp;맵 파일을 사용하는 단일 역참조 와일드카드는 이 패턴을 생성할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 패턴에 대한 맵 파일의 시작 부분은 다음과&nbsp;&nbsp;<code>pattern.txt</code>같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><tbody><tr><td>1 2 3 4 5 6</td><td><code>q 2a a wz z s 2 w w 3s ...</code></td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>따라서 마지막 문자가 a이면&nbsp;&nbsp;<code>q</code>패턴의 다음 문자는 a&nbsp;&nbsp;<code>2</code>&nbsp;또는 an&nbsp; 입니다&nbsp;<code>a</code>&nbsp;(오른쪽 위 또는 오른쪽 아래로 이동).&nbsp;마지막 문자가 이면&nbsp;&nbsp;<code>z</code>다음 문자에 사용할 수 있는 방향은 오른쪽 상단에서 까지만 있습니다&nbsp;&nbsp;<code>s</code>.&nbsp;이 맵 파일과 다음 토큰을 사용하면 4~6자 길이의 이 패턴을 따르는 모든 조합이 시도됩니다.&nbsp;<code>%a%3,5;pattern.txt;b</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="delimiters-spaces-and-special-symbols-in-passwords">암호의 구분 기호, 공백 및 특수 기호</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>기본적으로&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;하나 이상의 공백을 사용하여 토큰 목록 파일에서 토큰을 분리하고, 교체할 문자를 typos-map 파일에서 대체 문자와 분리합니다.&nbsp;또한 이러한 파일의 추가 공백도 무시합니다.&nbsp;이로 인해 공백 및 기타 특정 기호가 포함된 암호를 테스트하기가 어렵습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>%s</code>&nbsp;토큰 목록 파일에서만 작동하는 이 문제를 해결하는 한 가지 방법 은 단일 공백으로 대체되는 와일드카드를&nbsp;사용하는 것입니다&nbsp; .&nbsp;tokenlist 파일과 typos-map 파일 모두에 대해 작동하는 또 다른 옵션은&nbsp;&nbsp;<code>--delimiter</code>&nbsp;이 동작을 변경할 수 있는 옵션을 사용하는 것입니다.&nbsp;사용하면 공백이 더 이상 무시되지 않으며 여분의 공백도 제거되지 않습니다.&nbsp;&nbsp;대신 토큰 또는 오타 맵 열을 구분하기 위해&nbsp;<em>지정된 대로</em>&nbsp;새&nbsp;&nbsp;<code>--delimiter</code>&nbsp;문자열을 정확히 사용해야 합니다&nbsp; .&nbsp;모든 공백은 토큰의 일부가 되므로 이러한 파일에 실수로 공백을 추가하지 않도록 주의해야 합니다.<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또한&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;tokenlist 파일(및&nbsp;&nbsp;<code>#</code>&nbsp;typos-map 파일에서도 기호에 대해)의 특정 특정 상황에서 다음 기호를 특별하게 간주합니다.&nbsp;특수 기호는 암호의 일부가 아니라 구문의 일부입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>%</code>&nbsp;– 항상 특수한 것으로 간주됩니다(-스타일 와일드카드 내부에 있는 경우 제외&nbsp;&nbsp;&nbsp;,&nbsp;&nbsp;<em>와일드&nbsp;</em><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">카드</a><code>%[...]</code>&nbsp;섹션 참조&nbsp;&nbsp;&nbsp;).&nbsp;&nbsp;토큰에서 검색 중에&nbsp;&nbsp;로 대체됩니다.&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards"></a><code>%%</code><code>%</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>^</code>&nbsp;– 토큰의 첫 번째 문자인 경우에만 특별합니다.&nbsp;&nbsp;검색하는 동안&nbsp;<code>%^</code>&nbsp;로 대체됩니다.&nbsp;<code>^</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>$</code>&nbsp;– 토큰의 마지막 문자인 경우에만 특별합니다.&nbsp;<code>%S</code>&nbsp;(대문자&nbsp; )는&nbsp;&nbsp;검색 중에&nbsp;<code>S</code>로 대체됩니다.&nbsp;<code>$</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>#</code>&nbsp;– 줄의&nbsp;&nbsp;<em>첫 번째</em>&nbsp;문자 &nbsp;인 경우에만 특별합니다&nbsp; .&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#basics">주석에 대한 참고 사항은 여기를 참조하십시오.</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>+</code>&nbsp;– 줄의 첫 번째(공백 포함 안 함) 문자, 바로 뒤에 공백(또는 구분 기호) 및 일부 토큰이 있는 경우에만 특별합니다(상호 제외 섹션 참조).&nbsp;토큰으로 단일 문자가 필요한 경우&nbsp;&nbsp;<code>+</code>&nbsp;라인의 첫 번째 토큰이 아닌지 확인하거나 자체적으로 라인에 있어야 합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>]</code><code>%[</code>&nbsp;– -style 와일드카드 의 끝을 표시하기 위해 토큰 뒤에&nbsp;&nbsp;&nbsp;오는 경우에만 특별합니다&nbsp;&nbsp;<code>%[...]</code>.&nbsp;&nbsp;의&nbsp;&nbsp;<em>바로 뒤에</em>&nbsp;나타나면&nbsp;&nbsp;<code>%[</code>대체 세트의 일부이며 다음&nbsp;&nbsp;<em>은</em>&nbsp;<code>]</code>&nbsp;&nbsp;실제로 와일드카드를 끝냅니다. 예를 들어 와일드카드&nbsp;&nbsp;<code>%[]x]</code>&nbsp;에는 두 개의 대체 문자&nbsp;&nbsp;<code>]</code>&nbsp;및 가&nbsp; 포함됩니다&nbsp;<code>x</code>.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>이 중 어느 것도 공백과 기호(캐리지 리턴 및 줄 바꿈 제외)를 그대로 취급하여 암호의 일부로 취급하는 암호 목록 파일에는 적용되지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>알려진 위치의 문자 6개와 알 수 없는 문자 6개가 있는 파일의 예는 다음에서 찾을 수 있습니다. 샘플 TokenList</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 토큰 목록을 사용할 예제 명령은 다음과 같습니다.&nbsp;<code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --tokenlist ./btcrecover/test/test-listfiles/SeedTokenListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>이 방법을 사용할 때 니모닉 길이와 언어를 지정해야 한다는 점에 유의해야 합니다.</strong>&nbsp;&nbsp;지원되는 언어는 여기에서 찾을 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--listpass</code>&nbsp;BTCRecover는 또한 토큰 목록을 디버깅하는 데 유용할 수 있는 명령을 통해 테스트할 시드를 인쇄할 수 있습니다. 토큰 목록의 시드 목록에 대한 자세한 내용은 여기를 참조하십시오&nbsp;…&nbsp;&nbsp;매우 빠르게 커질 텍스트 파일을 덤프합니다. 나중에 이를 최적화할 예정입니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="the-passwordlist">비밀번호 목록</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover"><em>테스트하려는 전체 암호의 간단한 목록이 이미 있고 위에서 설명한 기능이 필요하지 않은 경우 btcrecover</em></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover">&nbsp;실행&nbsp;</a>&nbsp;&nbsp;에서 나중에 설명하는 옵션&nbsp;&nbsp;<code>--passwordlist</code>&nbsp;대신 명령줄 옵션을&nbsp;&nbsp;사용할 수 있습니다.&nbsp;&nbsp;&nbsp;부분).&nbsp;암호에&nbsp;<a href="https://en.wikipedia.org/wiki/ASCII">ASCII 가 아닌(비영어) 문자가 포함된 경우 계속하기 전에&nbsp;</a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#unicode-support">유니코드 지원</a>&nbsp;&nbsp;섹션을 읽어야 합니다&nbsp;&nbsp;&nbsp;.<code>--tokenlist</code><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#running-btcrecover"><em></em></a><a href="https://en.wikipedia.org/wiki/ASCII"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/#unicode-support"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--passwordlist</code>&nbsp;파일 없이&nbsp;&nbsp;지정하면&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;명령 프롬프트 창에서 암호 목록을 한 줄에 하나씩 입력하라는 메시지를 표시합니다.&nbsp;암호가 포함된 텍스트 파일이 이미 있는 경우 대신 사용할 수 있습니다&nbsp; (&nbsp;&nbsp;파일 이름으로&nbsp;<code>--passwordlist FILE</code>&nbsp;대체&nbsp; ).<code>FILE</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>해당 공백이 실제로 암호의 일부가 아닌 한 여분의 공백을 추가하지 마십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>옵션을 사용할 때 각 줄은 그대로 단일 암호로 사용됩니다&nbsp;&nbsp;<code>--passwordlist</code>&nbsp;(위의 기능은 적용되지 않음).&nbsp;그러나 아래에 설명된 Typos 기능 중 하나를 사용하여 비밀번호 목록에서 다양한 비밀번호 변형을 시도할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="seedlists">시드리스트</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>"암호 목록"(&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/">여기</a>&nbsp;참조 ) 기능은 인수를 통해 시드 문구와 함께 사용할 수도 있습니다&nbsp;&nbsp;<code>--seedlist</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>암호 목록과의 주요 차이점은 여전히 ​​한 줄에 하나의 시드 구를 나열하지만 명령을 통해 내보낸 것과 동일한 스타일로 형식을 지정해야 한다는 것입니다&nbsp;&nbsp;<code>--listpass</code>&nbsp;.&nbsp;이것은 이 도구의 tokenlst 단계의 출력이 passwordlist 단계에서 직접 사용될 수 있도록 하기 위한 것입니다.&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/btcrecover/test/test-listfiles/SeedListTest.txt">샘플 시드 목록</a>&nbsp;참조&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/btcrecover/test/test-listfiles/SeedListTest.txt"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>SeedList의 사용 예(위 토큰 목록 명령의 출력으로 listseeds를 사용하여 생성된 Seedlist):&nbsp;<code>python3 seedrecover.py --no-dupchecks --mnemonic-length 12 --language EN --dsw --wallet-type BIP39 --addr-limit 1 --addrs 17GR7xWtWrfYm6y3xoZy8cXioVqBbSYcpU --seedlist ./btcrecover/test/test-listfiles/SeedListTest.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>다양한 지갑에 대한 지갑 파일 암호 복구</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다음 지갑에 대한 Seed Phrase (Mnemonic) 복구<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://electrum.org/">Electrum</a>&nbsp;&nbsp;(1.x, 2.x, 3.x 및 4.x)(레거시 및 Segwit 지갑용. Segwit 지갑에 대해 –bip32-path "m/0'/0" 설정, 레거시에는 bip32-path 공백으로 두십시오. … 2fa 지갑은 지원하지 않습니다…)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.electroncash.org/">전자 현금</a>&nbsp;&nbsp;(2.x, 3.x 및 4.x)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다음을 포함하는 BIP-32/39 준수 지갑( <a href="https://bitcoinj.github.io/">bitcoinj</a> ):<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://multibit.org/">멀티비트 HD</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=de.schildbach.wallet">Android/BlackBerry용 비트코인 ​​지갑 (이전에&nbsp;</a><a href="https://github.com/gurnec/decrypt_bitcoinj_seed">decrypt_bitcoinj_seeds</a>&nbsp;&nbsp;에 의해 추출된 시드 포함&nbsp;&nbsp;)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=com.hivewallet.hive.cordova">Android용 Hive</a>&nbsp;,&nbsp;&nbsp;<a href="https://github.com/hivewallet/hive-ios">iOS용</a>&nbsp;및&nbsp;&nbsp;<a href="https://hivewallet.com/">Hive 웹용</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://brd.com/">빵 지갑</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다음을 포함하는 BIP-32/39/44 비트코인 ​​및 이더리움 준수 지갑:<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://wallet.mycelium.com/">Android용 균사체</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.bitcointrezor.com/">안전한</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.ledgerwallet.com/">원장</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://shapeshift.io/keepkey/">킵키</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://jaxx.io/">잭스</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.coinomi.com/">코이노미</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.exodus.io/">이동</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.myetherwallet.com/">마이이더월렛</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bither.net/">비더</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://blockchain.com/wallet">Blockchain.com</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bitaddress.org/">암호화(BIP-38) 종이 지갑 지원(예: Bitaddress.org에서)</a>&nbsp;&nbsp;liteaddress.org, paper.dash.org 등과 같은 altcoin 포크에서도 작동합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>두뇌 지갑<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Sha256(Passphrase) brainwallets (예: Bitaddress.org, liteaddress.org, paper.dash.org)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>sCrypt Secured Brainwallets(예: Warpwallet, Memwallet)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다음에 대한 비트코인 ​​지갑 암호 복구 지원:<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://bitcoincore.org/">비트코인 코어</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://multibit.org/">MultiBit HD</a>&nbsp;&nbsp;및&nbsp;&nbsp;<a href="https://multibit.org/help/v0.5/help_contents.html">MultiBit Classic</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://electrum.org/">Electrum</a>&nbsp;&nbsp;(1.x, 2.x, 3.x 및 4.x)(레거시 및 Segwit 지갑용. Segwit 지갑에 대해 –bip32-path "m/0'/0" 설정, 레거시에는 bip32-path 공백으로 두십시오. … 2fa 지갑은 지원하지 않습니다…)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/hivewallet/hive-mac/wiki/FAQ">OS X용 Hive</a>&nbsp;를 포함한&nbsp; 대부분의&nbsp;<a href="https://bitcoinj.github.io/">비트코인</a>&nbsp;​​기반 지갑&nbsp;<a href="https://github.com/hivewallet/hive-mac/wiki/FAQ"></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 암호(시드 복구를 위해 지원되는 모든 암호화 및 Electrum 시드에 대한 "추가 단어" 복구도 지원)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://ciphrex.com/products/">엠시그나(코인볼트)</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://blockchain.com/wallet">Blockchain.com</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://block.io/">block.io</a>&nbsp;&nbsp;(지갑 “비밀번호” 복구)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/jackjack-jj/pywallet">pywallet –</a>&nbsp;&nbsp;비트코인 ​​무제한/클래식/XT/코어 지갑의 덤프 지갑</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://play.google.com/store/apps/details?id=de.schildbach.wallet">Android/BlackBerry</a>&nbsp;&nbsp;지출 PIN 및 암호화된 백업용 비트코인 ​​지갑</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://github.com/kncgroup/bitcoin-wallet"></a>&nbsp;Android 암호화 백업용&nbsp;<a href="https://github.com/kncgroup/bitcoin-wallet">KnC Wallet</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://bither.net/">비더</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다음을 포함하여 위의 것 중 하나에서 파생된 대부분의 지갑에 대한 Altcoin 비밀번호 복구 지원:<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.coinomi.com/en/">Coinomi</a>&nbsp;&nbsp;(비밀번호로 보호된 지갑만 지원)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://metamask.io/">메타마스크</a>&nbsp;&nbsp;(및 바이낸스 체인 월렛, 로닌 월렛 등과 같은 메타마스크 클론)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://litecoin.org/">라이트코인 코어</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://electrum-ltc.org/">Electrum-LTC</a>&nbsp;&nbsp;(레거시 및 Segwit 지갑의 경우. Segwit 지갑의 경우 –bip32-path "m/0'/0" 설정, 레거시의 경우 bip32-path를 공백으로 두십시오... 2fa 지갑은 지원하지 않습니다...)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.electroncash.org/">전자 현금</a>&nbsp;&nbsp;(2.x, 3.x 및 4.x)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://litecoin.org/"></a>&nbsp;Android 암호화 백업용&nbsp;<a href="https://litecoin.org/">Litecoin Wallet</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://dogecoin.com/">도지코인 코어</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://multidoge.org/">멀티도그</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://dogechain.info/">dogchain.info</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://dogecoin.com/"></a>&nbsp;Android 암호화 백업용&nbsp;<a href="http://dogecoin.com/">Dogecoin 지갑</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://yoroi-wallet.com/#/">Cardano Master용 Yoroi 월렛</a>&nbsp;&nbsp;_지갑 데이터에서 추출한 비밀번호(브라우저 또는 루팅/탈옥된 휴대폰)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/">손상된 원시 Eth 개인 키</a>&nbsp;&nbsp;문자가 누락된 개별 개인 키입니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://myetherwallet.com/">이더리움 UTC 키 저장소 파일</a>&nbsp;&nbsp;이더리움 키 저장소 파일, 일반적으로 MyEtherWallet, MyCrypto 등과 같은 지갑에서 사용됩니다. (Theta 등과 같은 Eth 클론에서도 자주 사용됨)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="http://en.wikipedia.org/wiki/Free_and_open-source_software">무료 및 오픈 소스</a>&nbsp;&nbsp;– 누구나 이 소프트웨어를 다운로드, 검사, 사용 및 재배포할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Windows, Linux 및 OS X에서 지원됨</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>유니코드 암호 및 시드 지원</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>사용자가 스레드 수를 선택할 수 있는 다중 스레드 검색</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>여러 장치에 검색 작업을 분산시키는 기능</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/GPU_Acceleration/"></a>&nbsp;Bitcoin Core Passwords, Blockchain.com(Main and Second Password), Electrum Passwords + BIP39 및 Electrum Seeds를 위한&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/GPU_Acceleration/">GPU 가속</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>암호에 대한 와일드카드 확장</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>암호 및 시드에 대한 오타 시뮬레이션</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>진행률 표시줄 및 ETA 표시(명령줄에서)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>선택적 자동 저장 - 진행률을 잃지 않고 암호 복구를 중단하고 계속합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>간단한 그래픽 사용자 인터페이스로 자동화된 시드 복구</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>–pathlist 명령을 통해 주어진 시드에 대해 여러 파생 경로를 동시에 검색하는 기능(예: 의 경로 목록 파일)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>지원되는 거의 모든 지갑에 대한 "오프라인" 모드 –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Extract_Scripts/">추출 스크립트(자세한 내용을 보려면 클릭) 중 하나를 사용하여&nbsp;</a><em>btcrecover</em>&nbsp;또는 그것을 실행하는 사람에게 &nbsp;귀하의 주소 또는 개인 키&nbsp;<em>에</em>&nbsp;&nbsp;대한 액세스 권한을&nbsp;&nbsp;&nbsp;부여하지 않고 비밀번호 복구를 시도하기에 충분한 정보를 추출하십시오.&nbsp;&nbsp;비트코인 지갑.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>도구가 위에 나열되지 않은 암호화/지갑을 지원하도록 하려면 작동하는지 테스트하고 해당 코인에 대한 단위 테스트와 주소 형식을 수락하는 데 필요한 코드가 포함된 PR을 제출하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 id="btcrecover-extract-scripts"><em>btcrecover</em>&nbsp;&nbsp;추출 스크립트</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;때로는 대상 지갑 파일을 저장하는 컴퓨터에서&nbsp;<em>btcrecover를</em>&nbsp;직접 실행하는 것이 바람직하지 않을 수 있습니다&nbsp; .&nbsp;예를 들어:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>CPU나 GPU가 더 빠른 컴퓨터나 클라우드 기반 가상 머신이&nbsp;&nbsp;<em>btcrecover 를</em>&nbsp;실행하기에 더 좋은 장소일 수 있습니다 .</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;비밀번호를 올바르게 검색하도록&nbsp;<em>btcrecover를</em>&nbsp;구성하는&nbsp; 것은 까다로울 수 있습니다.&nbsp;&nbsp;자신의 컴퓨터에서&nbsp;<em>btcrecover를</em>&nbsp;구성하고 실행할 수 있는 사람을 찾는 데 관심이 있을 수 있습니다&nbsp; .</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>btcrecover</em>&nbsp;&nbsp;에 유해한 버그나 기타 악의적인 동작이 없다고&nbsp;&nbsp;믿을 수 없습니다&nbsp; .&nbsp;<em>btcrecover</em>&nbsp;&nbsp;는 오픈 소스이며 신뢰할 수 없는 바이너리를 설치할 필요가 없습니다.&nbsp;그러나 그것은 또한 상당히 길고 복잡한 Python 스크립트이기 때문에 다른 Python 프로그래머도 유해한 코드(의도적으로 악의적이거나 우연히)가 포함되어 있지 않음을 확신하기 어렵습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><em>이 디렉토리의 추출 스크립트는 btcrecover가</em>&nbsp;&nbsp;암호 검색을 수행할 수&nbsp;있도록 지갑 파일에서 충분한 정보를 추출하는 비교적 짧고 간단한 스크립트입니다&nbsp; .&nbsp;이 스크립트는 암호를 찾은 후에도 비트코인 ​​자금을 위험에 빠뜨릴 만큼 충분한 정보를 추출하지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>&nbsp;에 대한 자세한 내용은&nbsp;<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/CREDITS/">학점</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/licence/">특허</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="btcrecoverpy-tutorial">btcrecover.py 튜토리얼</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover.py</em>&nbsp;&nbsp;는 Bitcoin Core, MultiBit(Classic 및 HD), Electrum(1.x 및 2.x), mSIGNA(CoinVault), OS X용 Hive, 블록체인을 지원하는 무료 오픈 소스 멀티스레드 지갑 암호 복구 도구입니다. com(v1-v3 지갑 형식, 주 비밀번호와 보조 비밀번호 모두), Bither, Android용 Bitcoin 및 KNC 지갑.&nbsp;대부분의 암호를 이미 알고 있지만 다양한 가능한 조합을 시도하는 데 도움이 필요한 경우를 위해 설계되었습니다.&nbsp;이 자습서는 제공해야 하는 기능을 안내합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="installation">BTCRecover 설치</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover를 설치하는 몇 가지 기본 단계가 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) BTCRecover 스크립트 다운로드 및 압축 해제</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) Python3 다운로드 및 설치</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) Python PIP를 통해 필수 패키지 설치</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) (선택 사항) GPU 가속을 위한 PyOpenCL 모듈 설치</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) 설치 테스트(선택 사항이지만 좋은 생각임)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이러한 단계는 지원되는 각 운영 체제에 대한 아래 비디오에서도 다룹니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>참고: 운영 체제 및 Python 환경에 따라 명령&nbsp;&nbsp;<code>python</code>&nbsp;을&nbsp;&nbsp;<code>python3</code>.&nbsp;(기본적으로 사용할 명령은&nbsp;&nbsp;<code>python</code>&nbsp;Windows 및&nbsp;&nbsp;<code>python3</code>&nbsp;Linux에 있습니다.) 대부분의 비기술적 사용자는 Windows를 사용하므로 모든 예제 명령은&nbsp;&nbsp;<code>python</code>&nbsp;이 플랫폼의 기본값과 일치하는 데 사용됩니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>비디오 자습서</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>윈도우:&nbsp;</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/8q65eqpf4gE","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/8q65eqpf4gE
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>우분투 리눅스:</strong>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Met3NbxcZTU","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Met3NbxcZTU
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>맥 OS:&nbsp;</strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/Qzc3oHzbcAo","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/Qzc3oHzbcAo
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="1-downloading-btcrecover">1)&nbsp;&nbsp;<em>btcrecover 다운로드</em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/archive/master.zip">https://github.com/demining/CryptoDeepTools/archive/master.zip</a>&nbsp;에서 최신 버전을 다운로드&nbsp;&nbsp;&nbsp;하고 원하는 위치에 압축을 풉니다.&nbsp;<em>btcrecover</em>&nbsp;자체 에 대한 설치 절차는 없지만&nbsp;&nbsp;&nbsp;운영 체제 및 복구하려는 지갑 유형에 따라 아래의 추가 요구 사항이 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="2-install-python">2) 파이썬 설치</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고:</strong>&nbsp;&nbsp;Python 3.7 이상만 공식적으로 지원됩니다. BTCRecover는 지원되는 모든 환경(Windows, Linux, Mac)에서 지원되는 모든 Python 버전(3.7, 3.8, 3.9, 3.10)으로 자동 테스트되므로 BTCRecover와 모든 필수 패키지가 올바르게 작동합니다.&nbsp;BTCRecover의 일부 기능은 이전 버전의 Python에서 작동할 수 있습니다. 가장 좋은 방법은 run-all-tests.py를 사용하여 작동하는 것과 작동하지 않는 것을 확인하는 것입니다…</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="windows">윈도우</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Windows에서 BTCRecover 설치 비디오 데모:&nbsp;&nbsp;<a href="https://youtu.be/8q65eqpf4gE">https://youtu.be/8q65eqpf4gE</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Python 다운로드 페이지(&nbsp;&nbsp;<a href="https://www.python.org/downloads/windows/">https://www.python.org/downloads/windows/</a>&nbsp;)를 방문 하고 최신&nbsp;&nbsp;<strong>Python 3.9</strong>&nbsp;&nbsp;릴리스 링크를 클릭합니다(Python 3.10 등도 작동하지만 Python 3.9는 필수 모듈 설치가 더 간단합니다. )&nbsp;<em>Windows용 Python 릴리스</em>&nbsp;제목 아래 페이지 상단 근처에 릴리스합니다&nbsp;&nbsp;.&nbsp;<code>Windows x86 MSI installer</code>&nbsp;32비트 버전의 Python용 또는&nbsp;&nbsp;<code>Windows x86-64 MSI installer</code>&nbsp;64비트 버전용을&nbsp;다운로드하고 실행합니다&nbsp; .&nbsp;최신 PC는 64비트 버전을 사용해야 하지만 어떤 버전이 자신의 PC와 호환되는지 잘 모르겠다면 32비트 버전을 선택하세요.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em><strong>Windows에서 Python을 설치할 때 설치 프로그램의 첫 번째 화면에서 "Add Python 3.9 to PATH"를 선택하십시오…</strong></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>대형 다중 CPU 시스템에 대한 참고 사항:</strong>&nbsp;&nbsp;Windows는 가능한 스레드 수를 64개로 제한합니다. 시스템에 이보다 더 많은 논리적/물리적 코어가 있는 경우 가장 좋은 방법은 Linux에서 도구를 실행하는 것입니다.&nbsp;(Ubuntu는 시작하기 쉬운 곳입니다)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="linux">리눅스</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Ubuntu Live USB에 BTCRecover 설치 비디오 데모:&nbsp;&nbsp;<a href="https://youtu.be/Met3NbxcZTU">https://youtu.be/Met3NbxcZTU</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>대부분의 최신 배포판에는 사전 설치된 Python 3이 포함되어 있습니다.&nbsp;이전 Linux 배포판에는 Python2가 포함되므로 python3을 설치해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>SeedRecover를 사용하는 경우 seedrecover에 기본 GUI 팝업을 사용하려면 tkinter(python3-tk)도 설치해야 합니다.&nbsp;(명령줄 사용은 이 패키지 없이도 작동합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Linux의 일부 배포판은 이것을 Python3과 함께 번들로 제공하지만 Ubuntu와 같은 다른 배포판의 경우 tkinter 모듈을 수동으로 설치해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>다음 명령으로 설치할 수 있습니다.&nbsp;<code>sudo apt install python3-tk</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>아래의 "pip3" 명령 중 하나라도 실패하면 다음 명령을 통해 PIP를 설치해야 할 수도 있습니다.&nbsp;<code>sudo apt install python3-pip</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Python3-pip에 대한 설치 후보가 없다는 메시지가 표시되면 다음 명령을 사용하여 "universe" 리포지토리를 활성화해야 합니다.&nbsp;<code>sudo add-apt-repository universe</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 명령을 다시 실행하여 위에서 python3-pip를 설치할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="enabling-native-ripemd160-support">기본 RIPEMD160 지원 활성화</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>OpenSSL v3(2021년 말)부터, ripemd160은 더 이상 기본적으로 활성화되지 않으며 이제 "레거시" 해시 함수 세트의 일부입니다.&nbsp;Linux/MacOS 환경에서 Python의 hashlib 모듈은 익은 md160용 OpenSSL에 의존하므로 이러한 환경에서 완전한 성능을 원하는 경우 OpenSSL 설정을 수정하여 레거시 공급자를 활성화해야 할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2022년 7월 현재 BTCRecover에는 RIPEMD160의 "순수한 Python" 구현이 포함되어 있지만 이는 hashlib를 통한 기본 구현과 비교할 때 약 1/3의 성능만 제공합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 적용 수정의 비디오 데모는 여기에서 찾을 수 있습니다:&nbsp;&nbsp;<a href="https://youtu.be/S3DWKp0i4i0">https://youtu.be/S3DWKp0i4i0</a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/S3DWKp0i4i0","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/S3DWKp0i4i0
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>수정된 구성 파일의 예는&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/master/docs/example_openssl.cnf">https://github.com/demining/CryptoDeepTools/blob/master/docs/example_openssl.cnf 에서 찾을 수 있습니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자세한 내용은 OpenSSL Github 리포지토리의 관련 문제(&nbsp;&nbsp;<a href="https://github.com/openssl/openssl/issues/16994">https://github.com/openssl/openssl/issues/16994 )를 참조하십시오.</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1265} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/11/image-191.png" alt="BTC 복구 암호화 가이드" class="wp-image-1265"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="macos">맥 OS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>MacOS에서 BTCRecover 설치 비디오 데모:&nbsp;&nbsp;<a href="https://youtu.be/Qzc3oHzbcAo">https://youtu.be/Qzc3oHzbcAo</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1)&nbsp;&nbsp;<a href="https://brew.sh/">brew.sh의 지침에 따라 추출을 설치합니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>설치 명령은 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>지침을 따르고 경로에 추출을 추가하십시오…</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2)&nbsp;&nbsp;<a href="https://ofek.dev/coincurve/install/">coincurve 빌드 요구 사항 설치</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>설치 명령은 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>brew install autoconf automake libffi libtool pkg-config python
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>그래픽 인터페이스를 사용하려면 지침에 따라 tkinter도 설치해야 합니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Brew를 통해 Python을 설치한 후에는 전체 버전 번호가 포함된 명령을 사용하여 Python과 PIP를 모두 실행해야 합니다.&nbsp;(예: python3.9 및 pip3.9)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="3-install-requirements-via-python-pip">3) Python Pip을 통해 요구 사항 설치</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Python3과 PIP가 모두 설치되면 다음 명령을 사용하여 BTCRecover의 모든 기능에 대한 모든 요구 사항을 자동으로 설치할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>pip3 install -r requirements.txt</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>고급 사용자인 경우 시도 중인 특정 복구에 필요한 추가 패키지만 설치하도록 선택할 수 있습니다.&nbsp;어떤 지갑이 어떤 패키지를 필요로 하는지에 대한 자세한 정보는 이 가이드의 맨 아래에 있습니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="4-install-pyopencl-for-gpu-acceleration">4) GPU 가속을 위한 PyOpenCL 설치</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>GPU 지원을 사용하려면 위 명령에서 다루지 않는 추가 OpenCL 라이브러리를 설치해야 합니다...</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자세한 정보 및 지침은 여기에서 GPU 가속 페이지를 참조하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>GPU 가속</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="btcrecover-gpu-acceleration-guide">BTCRecover GPU 가속 가이드</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="performance-notes">성능 노트</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover에는 하나 이상의 그래픽 카드 또는 전용 가속기 카드를 사용하여 검색 성능을 높이는 지원이 포함되어 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것이 제공하는 성능 향상은 복구하려는 지갑 유형, CPU 및 GPU에 따라 다릅니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>비교를 위해 다양한 지갑에 대한 i7-8750 대 NVidia 1660ti의 CPU 대 GPU 성능은 일반적으로 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>복구 유형</th><th>CPU 성능(kp/초)</th><th>GPU 성능(kp/s)</th><th>GPU 속도 향상 대 CPU</th></tr></thead><tbody><tr><td>비트코인 코어(JTR 커널)</td><td>0.07</td><td>6.75</td><td>96배</td></tr><tr><td>비트코인 코어(OpenCL_Brute)</td><td>0.07</td><td>0.95</td><td>14배</td></tr><tr><td>Blockchain.com 기본 비밀번호</td><td>1</td><td>10</td><td>10배</td></tr><tr><td>Blockchain.com 두 번째 비밀번호</td><td>0.39</td><td>15.5</td><td>40배</td></tr><tr><td>dogchain.info</td><td>1.3</td><td>11.3</td><td>10배</td></tr><tr><td>일렉트럼 2 월렛 비밀번호</td><td>4.5</td><td>21</td><td>4.5배</td></tr><tr><td>BIP39 암호(또는 Electrum '추가 단어'</td><td>2.3</td><td>10.4</td><td>4.5</td></tr><tr><td>BIP39 12 워드 시드</td><td>33</td><td>134</td><td>4.3배</td></tr><tr><td>BIP39 12 단어 시드(토큰 목록)</td><td>33</td><td>130</td><td>4배</td></tr><tr><td>BIP39 24 워드 시드</td><td>160</td><td>180</td><td>1.15배</td></tr><tr><td>BIP39 24 단어 시드(토큰 목록)</td><td>140</td><td>160</td><td>1.15배</td></tr><tr><td>단청 씨앗</td><td>200</td><td>366</td><td>1.8배</td></tr><tr><td>BIP38 암호화 키</td><td>0.02</td><td>0.02</td><td>1x(다중 GPU로 잘 확장됨)</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><strong>이 시점에서 GPU/OpenCL을 활성화하면 속도가 향상된다고 가정하지 마십시오. 특히 매우 고급 CPU와 저사양 GPU가 있는 경우... OpenCL/GPU를 사용하거나 사용하지 않고 명령을 테스트하고 –no-eta를 사용하십시오. 및 - 성능을 평가하기 위한 성능 인수</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>이 급격한 성능 차이는 특히 BIP39 및 Electrum 시드 복구의 경우 프로세스의 다른 부분이 다양한 정도로 CPU에 바인딩되어 있기 때문입니다.&nbsp;따라서 더 많은 처리를 OpenCL로 전환하고 보다 효율적인 시드 생성기를 만드는 것이 향후 작업 영역이 될 것입니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Usage_Examples/2020-10-06_Multi-GPU_with_vastai/Example_Multi-GPU_with_vastai/">또한 이 문서에서 다양한 GPU, 특히 다중 GPU 상황에 대한 성능 정보를 찾을 수 있습니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pyopencl-installation">PyOpenCL 설치</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>GPU/OpenCL 가속은 OpenCL 1.2용 PyOpenCL을 설치했는지에 따라 달라집니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 기능을 사용하려면 OpenCL을 지원하는 카드와 드라이버가 있어야 하며(대부분의 AMD 및 NVIDIA 카드와 드라이버는 이미 Windows에서 OpenCL을 지원함) 아래 설명된 대로 필수 Python 라이브러리를 설치해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>GPU 가속은 MacOS에서도 작동해야 하지만 필요한 Python 라이브러리를 설치하기 위한 지침은 현재 이 자습서에 포함되어 있지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pyopencl-installation-for-windows">Windows용 PyOpenCL 설치</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이렇게 하면 OpenCL을 설치하기 전에 미리 컴파일된 작업 버전의 numpy를 수동으로 설치합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>GPU용 드라이버 패키지를 설치하십시오… 이것 없이는 아무 것도 작동하지 않습니다…</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>OpenCL 1.2 및 Python 3용 최신 버전의 PyOpenCL(32비트 버전 또는 설치한 Python 버전과 일치하는 64비트 버전)을 여기에서 다운로드하십시오:&nbsp;&nbsp;<a href="http://www.lfd.uci.edu/~gohlke/pythonlibs/#pyopencl">http://www.lfd.uci.edu/~ gohlke/pythonlibs/#pyopencl</a>&nbsp;.&nbsp;<em>최상의 호환성을 위해 OpenCL 1.2 이상</em>&nbsp;버전을 선택해야 합니다&nbsp;&nbsp;&nbsp;(파일 이름에서 "cl12"를 찾고 Python 버전을 메이칭할 숫자도 찾습니다(예: Python 3.8과 일치하는 "38"). (OpenCL 2.0 버전이 시스템에서 작동할 수 있으므로 OpenCL 1.2용 PyOpenCL을 사용할 수 없는 경우 시도해 보십시오.) 각기:<code>pyopencl‑2021.1.4+cl12‑cp39‑cp39‑win_amd64.whl pyopencl‑2021.1.4+cl12‑cp39‑cp39‑win32.whl</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>명령 프롬프트 창을 열고 1단계에서 다운로드한 파일을 다운로드한 위치로 이동한 다음 다음을 입력하여 PyOpenCL 및 해당 종속성을 설치합니다. (64비트 환경에서 Python3.8로 가정)<code>pip3 install "pyopencl-2021.1.4+cl12-cp39-cp39-win_amd64.whl</code></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="pyopencl-installation-for-linux">Linux용 PyOpenCL 설치</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>Ubuntu 20.04에서 사용</strong>&nbsp;&nbsp;1. NVidia GPU의 경우 시스템에 Nvidia 바이너리 드라이버를 설치합니다.&nbsp;(Ubuntu에서 이것은 간단하며 여기에 설명되어 있습니다: https://help.ubuntu.com/community/BinaryDriverHowto/Nvidia#NVIDIA_driver_from_the_Ubuntu_repositories 440 버전의 드라이버 메타팩이 테스트되었으며 제대로 작동합니다) – 현재 AMD가 없습니다. 테스트할 시스템이지만 AMD 드라이버가 설치되어 있는 한 제대로 작동해야 합니다. 2. 시스템에 pyOpenCL 라이브러리를 설치합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>    sudo apt install python3-pyopencl
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Linux 환경에 따라 APT를 통해 사용할 수 있는 Python 라이브러리가 매우 오래되어 제대로 작동하지 않을 수 있습니다.&nbsp;이 경우 Pip를 통해 PyOpenCL을 설치하고 빌드해야 할 수 있습니다.&nbsp;(그리고 PyOpenCL의 특정 버전이 시스템에 빌드되는지 여부는 다를 수 있으므로 이전 PyOpenCL 패키지 버전을 사용하는 것이 도움이 될 수 있습니다(예: pyopencl==2019.1.1).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>이 외에도 최신 Ubuntu LTS 릴리스 이외의 배포에 대해서는 추가 지원이 제공되지 않습니다.&nbsp;</strong>&nbsp;일반적으로 Hashcat용 환경 설치 및 구성 지침은 환경을 설정하고 작동하는 데 필요한 사항을 다룹니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="testing-your-system">시스템 테스트</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>PyOpenCL 설치가 올바르게 작동하는지 확인하려면 실행하려는 GPU 가속 복구 유형과 관련된 단위 테스트를 실행할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>비트코인 코어 John-The-Ripper 커널(JTR)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v GPUTests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>테스트가 실패하지 않는다고 가정하면&nbsp;&nbsp;<code>--enable-gpu</code>&nbsp;명령줄에 옵션을 추가하여 GPU 지원을 활성화할 수 있습니다.&nbsp;검색 성능을 향상시키기 위해 특정 값과 함께 제공되어야 하는 특히&nbsp;<code>--global-ws</code>&nbsp;및 와&nbsp;&nbsp;같은 다른 추가 옵션이 있습니다&nbsp; .&nbsp;<code>--local-ws</code>안타깝게도 이러한 옵션의 정확한 값은 아래에 설명된 대로 시행착오를 통해서만 결정할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>OpenCL_Brute Kernel을 통한 Blockchain.com, Electrum 지갑 및 BIP39 암호(또는 Electrum '추가 단어')(Bitcoin 코어도 지원하지만 JTR보다 느림)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>python3 -m btcrecover.test.test_passwords -v OpenCL_Tests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>모든 테스트가 통과하면 –enable-opencl을 명령줄 인수에 추가하기만 하면 됩니다.&nbsp;OpenCL 플랫폼 선택 및 작업 그룹 크기의 기본값은 좋은 결과를 제공해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>BIP39 또는 전기 종자 회수</strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>python3 -m btcrecover.test.test_seeds -v OpenCL_Tests
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>모든 테스트가 통과하면 –enable-opencl을 명령줄 인수에 추가하기만 하면 됩니다.&nbsp;OpenCL 플랫폼 선택 및 작업 그룹 크기의 기본값은 좋은 결과를 제공해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="performance-tuning-background">성능 조정: 배경</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>OpenCL 성능 조정과 관련하여 이해해야 할 핵심 사항은 CPU가 명령을 처리하는 방식과 GPU가 근본적으로 다르다는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>CPU는 명령을 매우 빠르게 처리할 수 있지만 기본적으로 CPU 코어당 한 번에 한 번만 작업을 수행할 수 있습니다.&nbsp;반면에 GPU는 동일한 작업을 수행할 때 실제로 더 느릴 수 있지만 차이점은 CPU에서 발생하는 것과 같이 차례로 수행하는 것이 아니라 병렬로 동시에 1000개의 작업 배치를 수행할 수 있다는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것이 의미하는 바는 GPU에 로드하는 작업 배치의 크기에 따라 GPU 처리에 상당한 성능 차이가 있을 수 있다는 것입니다.&nbsp;(잠재적인 배치 크기를 절반만 채우는 등의 작업을 수행하면 성능이 절반으로 떨어집니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>따라서 Global 및 Local work-size 인수를 설정하면 JTR 커널에 큰 차이를 만들 수 있는 반면 workgroup-size 명령을 사용하면 OpenCL_Brute 커널을 사용할 때 큰 차이를 만들 수 있습니다(OpenCL_Brute 커널의 기본값은 자동으로 작동해야 하지만). 시스템에 최적에 가까운 것을 출력)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것은 또한 CPU 처리에서 문제가 되지 않는 성능 병목 현상이 GPU 처리를 사용할 때 문제가 된다는 것을 의미합니다.&nbsp;(이것이 바로 24단어 시드에 대한 토큰 목록이 BIP39 12단어 시드를 사용한 표준 복구만큼 성능 향상을 거의 얻지 못하는 이유입니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것은 또한 한 PC에서 체크섬 시드 목록을 생성하고 –savevalidseeds, –savevalidseeds-filesize, –multi-file-seedlist 및 –skip-worker-checksum 인수를 사용하여 다른 PC에 로드하는 데 약간의 이점이 있음을 알 수 있는 이유이기도 합니다. .</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="multi-gpu-systems">다중 GPU 시스템</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>기본적으로 두 OpenCL 커널은 시스템에서 사용 가능한 모든 GPU를 사용하지만 조금 다르게 활용합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>JohnTheRipper Kernel(–enable-gpu 인수가 사용될 때 Bitcoin Core에서 사용됨)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>단일 CPU 스레드를 사용하고 모든 GPU를 사용하지만 성능 측면에서 GPU가 동일해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>OpenCL_Brute 커널(–enable-opencl 인수를 통해 활성화됨)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>라운드 로빈의 스레드에 GPU를 할당합니다.&nbsp;(예를 들어 3개의 GPU와 3개의 CPU 코어가 있는 경우 GPU1-&gt;CPU1, GPU2-&gt;CPU2, GPU3-&gt;CPU3 등을 할당합니다.) 이를 감안할 때 일반적으로 최소한 스레드 수만큼의 스레드를 원할 것입니다. GPU가 있습니다.&nbsp;(CPU보다 GPU가 더 많은 ex-crypto 마이닝 장비 이외의 시스템은 본 적이 없지만) BTCRecover는 기본적으로 논리적 CPU 코어 수만큼 스레드를 사용하지만 시스템 코어 수가 GPU보다 적으면 항상 –threads 인수를 사용하여 스레드 수를 수동으로 지정할 수 있습니다.&nbsp;<strong><em>일반적으로 말하자면, GPU당 2개의 스레드가 아마도 성능 측면에서 가장 좋은 출발점이라고 제안합니다…</em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>–opencl-devices 인수를 통해 사용하려는 OpenCL 장치를 수동으로 지정할 수도 있습니다.&nbsp;여기에 GPU를 두 번 나열할 수도 있습니다. 한 GPU가 다른 GPU보다 두 배 강력하여 더 큰 몫을 할당하려는 경우 유용할 수 있습니다.&nbsp;(예: GPU 0 0 1을 지정하면 GPU0이 GPU1보다 두 배 많은 스레드에 할당됩니다.) 위에서 언급한 것처럼 이러한 GPU는 라운드 로빈 방식으로 할당되므로 기본적으로 스레드가 있는 만큼 장치를 지정할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gpu-performance-tuning-for-bitcoin-core-and-derived-altcoin-wallets-with-the-jtr-kernel">JTR 커널을 사용하여 비트코인 ​​코어 및 파생된 알트코인 지갑을 위한 GPU 성능 튜닝</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 지갑의 좋은 출발점은 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 btcrecover.py --wallet ./btcrecover/test/test-wallets/bitcoincore-wallet.dat --performance --enable-gpu --global-ws 4096 --local-ws 256
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이&nbsp;&nbsp;<code>--performance</code>&nbsp;옵션은&nbsp;&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;Ctrl-C를 누를 때까지 성능을 측정하고 특정 암호를 테스트하지 않도록 지시합니다.&nbsp;성능 테스트를 위해서는 여전히 지갑 파일(또는 옵션)이 필요합니다&nbsp;&nbsp;<code>--extract-data</code>&nbsp;.&nbsp;이 초기 테스트에서 기준선을 얻은 후 다른 값을 시도&nbsp;&nbsp;<code>--global-ws</code>&nbsp;하고&nbsp;&nbsp;<code>--local-ws</code>&nbsp;성능이 향상되는지 악화되는지 확인할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>에 대한 올바른 값을 찾으면&nbsp; 10배 개선할 수&nbsp;<code>--global-ws</code>&nbsp;있으므로&nbsp;&nbsp;<code>--local-ws</code>&nbsp;일반적으로 노력할 가치가 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>일반적으로 테스트할 때 이 두 값을 2의 거듭제곱으로 늘리거나 줄여야 합니다. 예를 들어 한 번에 128 또는 256씩 늘리거나 줄여야 합니다.&nbsp;는&nbsp;&nbsp;<code>--global-ws</code>&nbsp;항상 로 균등하게 나눌 수 있어야 합니다&nbsp;&nbsp;<code>--local-ws</code>. 그렇지 않으면&nbsp;&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;오류 메시지와 함께 종료됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 절차는 지루할 수 있지만 더 큰 토큰 목록 또는 암호 목록을 사용하면 상당한 차이를 만들 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="opencl-performance-tuning-for-other-wallets">다른 지갑에 대한 OpenCL 성능 튜닝</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="limiting-derivation-paths-searched-for-seed-based-wallets">시드 기반 지갑에 대한 파생 경로 검색 제한</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>기본적으로 BTCRecover는 이제 주어진 암호화폐에 대한 모든 공통 파생 경로를 자동으로 검색합니다.&nbsp;(예: 비트코인 ​​BIP44, 49 및 84)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>CPU 기반 복구의 경우 성능이 크게 저하되지는 않지만 CPU에 따라&nbsp;&nbsp;&nbsp;OpenCL 성능이&nbsp;<strong>절반으로 떨어질 수 있습니다.&nbsp;</strong>따라서 찾고자 하는 파생 경로를 알고 있는 경우 –bip32-path 명령을 통해 수동으로 지정해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="address-generation-limit-for-seed-based-wallets">시드 기반 지갑의 주소 생성 제한</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>비트코인과 같은 암호화폐는 일반적으로 "받기"를 선택할 때마다 새 주소를 생성합니다.&nbsp;주소 생성 제한(–addr-limit 인수)은 BTCRecover가 각 시드 내에서 생성하고 검색해야 하는 주소 수를 알려줍니다.&nbsp;(이것이 지갑에서 가능한 가장 빠른 주소를 사용하려는 이유입니다)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>CPU 기반 복구의 경우 주소 생성 제한을 10과 같이 설정해도 성능에 큰 영향을 미치지 않는 반면 OpenCL 기반 복구의 경우 주소 생성 제한을 10으로 설정하면&nbsp;&nbsp;&nbsp;검색 성능이&nbsp;<strong>절반으로 줄어들 수 있습니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>즉, Ethereum 또는 Ripple 지갑과 같은 항목에서 복구를 수행하는 경우 이러한 계정 기반 암호화는 고정 수신 주소를 사용하는 경향이 있으므로 일반적으로 주소 생성 제한을 1로 둘 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또한 주소 데이터베이스를 사용하는 경우 일반적으로 주소 생성 제한을 1로 둘 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="work-group-size">작업 그룹 크기</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>–opencl-info 명령을 사용하면 OpenCL 장치 목록과 해당 최대 작업 그룹 크기가 표시됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 –opencl-workgroup-size 명령을 사용하여 작업 그룹 크기를 수동으로 설정할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>암호 복구의 경우:</strong>&nbsp;&nbsp;작업 그룹 명령을 최대 작업 그룹 크기의 정확한 배수로 설정해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>시드 복구의 경우</strong>&nbsp;&nbsp;시드 복구가 자동으로 작업 그룹 크기를 훨씬 더 큰 값으로 설정한다는 것을 알 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이는 생성된 시드의 대부분이 체크섬만 수행되고 완전히 해시되지 않기 때문입니다.&nbsp;생성된 시드:해시 비율은 지갑 유형과 시드 길이에 따라 다릅니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>일반적으로 말하자면: * BIP39 12 워드: 16:1 * BIP39 18 워드: 64:1 * BIP39 24 워드: 256:1 * 일렉트럼: 125:1</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것이 의미하는 바는 GPU의 최대 작업 그룹 크기를 채우기 위해 seedgenerator가 최대 작업 그룹 크기보다 몇 배 더 큰 가능한 시드 청크를 GPU에 전달해야 한다는 것입니다.&nbsp;(예: 작업 그룹 크기가 1024인 경우 BIP39 24 단어 시드에는 262,144개의 잠재적 시드가 필요합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="5-testing-your-installation">5) 설치 테스트</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BTCRecover, 설치된 Python 및 모든 필수 라이브러리를 다운로드하고 압축을 풀면 다음 명령을 사용하여 프로그램을 테스트할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 run-all-tests.py -vv</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 명령은 실행하는 데 몇 분 정도 걸리며 오류 없이 완료되어 시스템이 BTCRecover의 모든 기능을 사용할 준비가 되었음을 나타냅니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="wallet-python-package-requirements">Wallet Python 패키지 요구 사항</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>모든 지갑 유형에 대한 모든 요구 사항을 설치하려면 간단히 명령을 사용할 수 있습니다.&nbsp;<code>pip3 install -r requirements-full.txt</code></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>아래 목록에서 지갑 유형을 찾고 지갑 옆에 나열된 섹션에 대한 지침만 따르십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>비트코인 코어 – 옵션:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit Classic – 추천:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit HD – 옵션:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum(1.x 또는 2.x) – 권장:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum 2.8+ 완전히 암호화된 지갑 –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a>&nbsp;, 옵션:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 비트코인 ​​암호(예: TREZOR) –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP-39 이더리움 암호(예: TREZOR) –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome&nbsp;</a>&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>OS X용 Hive –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#google-protocol-buffers">Google protobuf</a>&nbsp;, 선택 사항:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA(CoinVault) – 추천:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Blockchain.info – 추천:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android/BlackBerry 백업용 비트코인 ​​지갑 – 권장:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android/BlackBerry 지출 PIN용 비트코인 ​​지갑 –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#scrypt">scrypt</a>&nbsp;,&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#google-protocol-buffers">Google protobuf</a>&nbsp;, 옵션:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>KnC Wallet for Android 백업 – 추천:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Bither –&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Seedrecover_Quick_Start_Guide/#installation">coincurve</a>&nbsp;, 옵션:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Litecoin-Qt – 옵션:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Electrum-LTC – 추천:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android용 라이트코인 지갑 – 추천:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Dogecoin 코어 – 옵션:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiDoge – 추천:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android용 Dogecoin 지갑 – 추천:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pycryptodome">PyCryptoDome</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SLIP39 지갑:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#shamir-mnemonic">shamir-mnemonic</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Py_Crypto_HD_Wallet 기반 BIP39 지갑:  <a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#py_crypto_hd_wallet">py_crypto_hd_wallet</a><!-- wp:list -->
<ul><!-- wp:list-item -->
<li>눈사태</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>코스모스(아톰)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>폴카 도트</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비밀 네트워크</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>솔라나</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>주요한</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>논문</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>트론</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Helium BIP39 지갑:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#pynacl">pynacl</a>&nbsp;&nbsp;및&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#bitstring">bitstring</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Eth 키 저장소 파일:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#eth-keyfile">eth-keyfile</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>그로슬코인 BIP39 지갑:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#groestlcoin_hash">groestlcoin_hash</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>BIP38 암호화 개인 키:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/INSTALL/#ecdsa">ecdsa</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="pycryptodome">파이크립토돔</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이더리움 지갑을 제외하고 PyCryptoDome은 모든 지갑에 엄격하게 요구되지는 않지만 위 목록에서 권장하는 대로 태그가 지정된 지갑에 대해 20배 속도 향상을 제공합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="py_crypto_hd_wallet">Py_Crypto_HD_Wallet</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 모듈은 다양한 지갑 유형에 필요합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Windows 사용자의 경우 모듈을 성공적으로 설치하려면 Microsoft Visual C++ 빌드 도구도 설치해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이를 다루는 비디오 자습서는 여기에서 찾을 수 있습니다:&nbsp;&nbsp;<a href="https://youtu.be/0LMUf0R9Pi4">https://youtu.be/0LMUf0R9Pi4</a></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/0LMUf0R9Pi4","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/0LMUf0R9Pi4
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>MacOS 및 Linux 사용자의 경우 플랫폼에 대한 이 페이지의 설치 지침을 따르면 모듈이 제대로 빌드/설치됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="running-btcrecoverpy"><em>btcrecover.py</em>&nbsp;실행&nbsp;<em></em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 튜토리얼은 꽤 깁니다... 전체 내용을 읽을 필요는 없습니다.&nbsp;다음은 시작해야 할 몇 가지 장소입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>이미 파일이 있는 경우&nbsp;&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;6단계로 건너뛰십시오. 그렇지 않은 경우 기억나는 작은 조각의 여러 조합으로 암호를 만드는 데 도움이 필요하면 4단계부터 시작하십시오. 암호에 오타가 있다고 생각되거나 대부분 전체 암호가 무엇인지 알고 있으며 다양한 변형을 시도하기만 하면 됩니다. 5단계를 읽으십시오.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>토큰 파일 섹션(최소한 시작 부분)을 읽으십시오.&nbsp;&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;기억나는 작은 조각에서 기억하지 못하는 전체 암호를 구축하는 방법을 설명합니다.&nbsp;작업이 완료되면&nbsp;&nbsp;<code>tokens.txt</code>&nbsp;나중에 필요한 파일을 만드는 방법을 알게 됩니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>btcrecover가</em>  전체 암호를 변형하여 다른 암호 추측을 생성하는 방법을 설명하는 Typos 섹션을 읽으십시오  . 완료되면 테스트하려는 변형을 생성하는 명령줄 옵션 목록이 표시됩니다.<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>위의 4단계를 건너뛴 경우 대신 간단한&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#token-Lists-and-password-or-seed-lists">암호 목록</a>&nbsp;&nbsp;섹션을 읽으십시오.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#running-btcrecover"><em>btcrecover</em></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#running-btcrecover">&nbsp;실행&nbsp;<em></em></a> 섹션을 읽고   이러한 부분을 함께 배치하는 방법과   명령 프롬프트 창에서 <em>btcrecover를 실행하는 방법을 확인하십시오.</em><!-- wp:list -->
<ul><!-- wp:list-item -->
<li>(선택 사항)&nbsp;&nbsp;&nbsp;테스트할 암호를 보려면&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#testing-your-config">구성 테스트 섹션을 읽으십시오.</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>(선택 사항) 오랜 시간이 걸리는 조합을 많이 테스트하는 경우&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#autosave">자동 저장</a>&nbsp;&nbsp;기능을 사용하여 진행 상황이 손실되지 않도록 보호하세요.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>(선택사항이지만 강력히 권장합니다) 비밀번호를 찾으면 거액의 비트코인을 기부 주소로 기부하세요.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="bip3944-wallets-with-addressdb">AddressDB가 있는 BIP39/44 지갑</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BIP39/44 지갑에서 암호를 복구하는 경우 찾고 있는 주소가 있든 없든 복구할 수 있습니다. 자세한 내용은 주소 데이터베이스로 복구를 참조하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="recovery-with-an-address-database">주소 데이터베이스를 사용한 복구</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="background">배경</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>BIP39/44 지갑을 복구하려고 할 때&nbsp;&nbsp;<em>seedrecover.py</em>&nbsp;&nbsp;및&nbsp;&nbsp;<em>btcrecover.py는</em>&nbsp;&nbsp;입력한 시드를 기반으로 다른 추측을 시도하므로 어떤 시드 추측이 올바른지 확인할 방법이 필요합니다.&nbsp;<em>일반적으로 각 시드 추측을 사용하여 마스터 공개 키( mpk</em>&nbsp;) 를 만들고&nbsp;&nbsp;입력한 mpk와 비교하거나 비트코인 ​​주소를 만들고 입력한 주소와 비교합니다.&nbsp;mpk나 주소가 없는 경우에도&nbsp;&nbsp;<em>seedrecover.py를</em>&nbsp;사용할 수 &nbsp;있지만 더 복잡하고 시간이 많이 걸립니다.&nbsp;<strong>이 프로세스의 주요 시간 비용은 블록체인을 다운로드하고 AddressDB를 생성하는 데 있습니다. 프로세스의 실제 확인 부분은 단일 주소 또는 600,000개의 주소가 있는 addressDB에 대해 테스트하는지 여부에 관계없이 거의 동일한 속도로 실행됩니다… 따라서 지갑에서 사용한 주소에 대해 조금이라도 확신이 서지 않는다면 AddressDB는 매우 가치가 있습니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>위와 같이 주소를 생성한 다음 전체 블록체인에서 생성된 각 주소를 찾는 방식으로 작동합니다.&nbsp;이렇게 하려면 먼저 블록체인을 기반으로 하는 주소 데이터베이스를 만들어야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>원시 블록체인 데이터를 직접 구문 분석하거나 주소 목록이 포함된 파일을 처리하여 AddressDB를 생성할 수 있는 두 가지 방법이 있습니다.&nbsp;(이 주소 목록에는 여러 코인 유형의 주소를 포함하여 BTCRecover가 지원하는 모든 주소 유형이 포함될 수 있습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="pre-made-addressdb-files">미리 만들어진 AddressDB 파일</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고: AddressDB 파일은 BTCRecover의 Python2 및 Python3 분기 간에 호환되지 않습니다.&nbsp;올바른 것을 다운로드했는지 확인하십시오.&nbsp;(이 Github의 마스터 브랜치는 이제 모두 Python3입니다…)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>지원되는 일부 체인에 대한 AddressDatabases를 만들고 업로드했으며 주기적으로 업데이트할 예정입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptoguide.tips/btcrecover-addressdbs/">여기 내 웹사이트에서 다운로드할 수 있습니다</a></strong>&nbsp;&nbsp;…</p>
<!-- /wp:paragraph -->

<!-- wp:image {"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://cryptoguide.tips/btcrecover-addressdbs/AddressDBs%20include%20transactions%20up%20until%20approximately%20the%20file%20modified%20date.txt"><img src="https://cryptoguide.tips/icons/text.gif" alt="[TXT]"/></a></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 id="parameters-to-manage-addressdb-size">AddressDB 크기를 관리하기 위한 매개변수</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>DB길이</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 도구는 미리 최대 크기를 지정해야 하는 데이터베이스 파일을 생성합니다.&nbsp;이 최대 주소 수는 2의 거듭제곱으로 지정됩니다. 예: –dblength 30은 2^30개의 주소를 위한 공간을 만듭니다. 충돌이 발생하므로 다시 실행하고 –dblength를 하나씩 늘려야 할 수 있습니다.&nbsp;기본값은 30으로, ~8GB 파일을 생성하고 2018년 11월 비트코인 ​​블록체인에 충분합니다&nbsp;&nbsp;<strong>. AddressDB 파일 크기는 사용되는 주소 수가 아니라 수용할 수 있는 최대 주소 수에 따라 달라집니다.</strong>&nbsp;이것이 의미하는 바는 Vertcoin과 같은 더 작은 블록체인에 대해 addressDB를 생성하는 경우 더 작은 dblength를 지정하여 공간을 절약할 수 있다는 것입니다.&nbsp;기본값으로 두면 ~30mb 파일이 작동했을 때 8GB 파일로 끝납니다.&nbsp;<strong>HDD 공간이 충분하다면 문제가 되지 않습니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2021년 1월 현재 블록체인, AddressDB 크기 및 최적 매개변수에 대한 대략적인 가이드는 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>동전</th><th>블록체인 크기</th><th>주소DB 크기</th><th>필수 DB길이</th></tr></thead><tbody><tr><td>비트코인</td><td>324GB</td><td>16 기가 바이트</td><td>31</td></tr><tr><td>비트코인 캐시</td><td>155GB</td><td>4GB</td><td>29</td></tr><tr><td>라이트코인</td><td>90GB</td><td>2GB</td><td>28</td></tr><tr><td>버트코인</td><td>5GB</td><td>32MB</td><td>22</td></tr><tr><td>모나코인</td><td>2.5GB</td><td>32MB</td><td>22</td></tr><tr><td>이더 리움</td><td>N/A(~1억 2천만 개의 주소가 있는 BigQuery의 AddressList)</td><td>4GB</td><td>29</td></tr><tr><td>도지코인</td><td>해당 사항 없음(~6천만 개의 주소가 있는 BigQuery의 주소 목록)</td><td>1GB</td><td>27</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p><em>의심스러운 경우 전체 블록체인을 다운로드하고 엔트리티에서 구문 분석하십시오… 기본값은 괜찮을 것입니다…</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>AddressDB 생성을 위한 날짜 범위 제한</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>특정 날짜 사이에 발생한 거래에 대한 주소만 포함하는 주소 데이터베이스를 생성할 수 있습니다.&nbsp;이는 AddressDB 파일에 필요한 추가 공간이 적고 램도 훨씬 적게 사용한다는 점에서 유용할 수 있습니다.&nbsp;(예: 하드웨어 지갑을 주문한 후에 사용된 주소만 고려하도록 선택할 수 있습니다.) 이것은 YYYY-MM-DD 형식의 날짜와 함께 –blocks-startdate BLOCKS_STARTDATE 및 –blocks-enddate BLOCKS_ENDDATE 인수를 통해 수행됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>AddressDB 생성 시 X개의 블록 파일 건너뛰기</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>특정 블록 파일에서 처리를 시작하도록 AddressDB 생성 스크립트에 지시하는 것도 가능합니다.&nbsp;이것은 더 큰 블록체인의 처리 속도를 높이는 데 도움이 됩니다.&nbsp;(예: 비트코인에 대해 2018년에 사용된 주소만 원하는 경우) 이것은 –first-block-file FIRST_BLOCK_FILE을 통해 수행되며 FIRST_BLOCK_FILE은 블록 파일의 번호입니다.&nbsp;<strong>이 기능은 –blocks-startdate와 함께 사용하는 경우 시작 날짜 이후에 블록 계산을 시작하도록 지시하면 경고하지 않습니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="creating-an-addressdb-from-blockchain-data">블록체인 데이터에서 AddressDB 생성</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>다음에서 원시 블록체인 데이터를 구문 분석하여 addressDB를 생성할 수 있습니다. * Bitcoin * Bitcoin Cash * Litecoin * Vertcoin * Monacoin</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또한 –dbyolo 플래그를 통해 강제 시도를 통해 다른 '비트코인 유사' 블록체인과 함께 작동할 수도 있습니다.&nbsp;(처리하면서 발견된 주소 수가 증가하는 것을 보면 성공적으로 블록체인을 구문 분석하고 있음을 알 수 있습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;*Dogecoin*Verge*Zcash 및 Zencash*Monero*Ethereum과 작동&nbsp;<strong>하지 않음</strong>&nbsp;을 테스트하여 확인했습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이러한 블록체인의 경우 Google BigQuery와 같은 것을 통해 주소 목록을 얻고 이 목록에서 addressDB를 생성해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>알트코인 블록체인</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 도구는 위에 지정된 블록체인과 작동하도록 테스트되었습니다.&nbsp;기본적으로 기본 Bitcoin 설치 디렉토리를 스캔하여 사용합니다.&nbsp;비트코인을 다른 곳에 설치했거나 대체 블록체인에서 AddressDB를 생성하려는 경우 –datadir 인수를 사용하여 해당 위치를 수동으로 지정해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>어떤 블록체인을 사용하고 싶은지에 대한 질문은 개인 상황에 달려 있습니다.&nbsp;즉, 어느 시점에 Litecoin 또는 Vertcoin을 저장하는 데 사용한 BIP39 지갑이 있는 경우 전체 BTC 블록체인을 다운로드하는 대신 이러한 체인 중 하나를 다운로드하여 사용하는 것이 좋습니다.&nbsp;BIP39/44 지갑은 모든 통화에 대해 동일한 시드를 사용하므로 시드를 복구하기 위해 어느 것을 사용하는지는 중요하지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>재현할 예</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;AddressDB에 대해 몇 가지 테스트를 실행하려는 경우 이 프로젝트의&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/master/btcrecover/test/test-addressdbs">./btcrecover/test/test-addressdbs</a>&nbsp;폴더 에 테스트 DB용이 있습니다&nbsp; .&nbsp;기본적으로 각 블록에서 24시간 분량의 주소만 포함하기 때문에 크기가 작습니다.&nbsp;(–blocks-startdate 및 enddate 인수로 생성됨)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>다음 명령과 함께 이러한 데이터베이스 중 하나를 사용하여 테스트를 실행할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 seedrecover.py --no-dupchecks --addr-limit 2 --bip32-path "m/44'/28'/1'/0" --big-typos 1 --addressdb ./btcrecover/test/test-addressdbs/addresses-VTC-Test.db --wallet-type bip39</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그리고 첫 단어 대신 숫자 1이 붙은 씨앗은…</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>1 entire sniff tired miracle solve shadow scatter hello never tank side sight isolate sister uniform advice pen praise soap lizard festival connect baby</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/master/btcrecover/test/test_seeds.py">test_seeds.py</a>&nbsp;에서 다루는 단위 테스트에서 작은 AddressDB를 사용하는 테스트의 더 많은 예를 찾을 수 있습니다&nbsp;&nbsp;&nbsp;. "test_addressdb_"로 시작하는 메서드를 검색하면 매개변수에 addressDB 제한, 테스트 구문, 파생 경로 및 사용된 AddressDB가 나열됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>블록체인 데이터에서 AddressDb를 생성하는 단계:</strong>&nbsp;&nbsp;1. 처리하려는 전체 블록체인을 위한 충분한 공간과 결국 얻게 될 AddressDB 크기의 두 배에 해당하는 RAM이 있는 컴퓨터를 사용해야 합니다(이는 매우 넉넉한 추정치입니다. , 적게 해도 괜찮을 것 같지만 적어도 만들려는 AddressDB만큼은 있어야 합니다.) .&nbsp;64비트 버전의 Python이 설치되어 있어야 합니다.&nbsp;(다른 소규모 블록체인은 훨씬 적은 공간과 RAM을 필요로 함)</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><a href="https://bitcoincore.org/">Bitcoin Core</a>&nbsp;,&nbsp;&nbsp;<a href="https://bitcoinabc.org/">Bitcoin ABC</a>&nbsp;,&nbsp;&nbsp;<a href="https://litecoin.org/">Litecoin Core</a>&nbsp;,&nbsp;&nbsp;<a href="https://vertcoin.org/download-wallet/">Vertcoin</a>&nbsp;,&nbsp;&nbsp;<a href="https://monacoin.org/">Monacoin Core</a>&nbsp;와 같이 선택한 블록체인에 풀 노드 클라이언트를 설치하십시오&nbsp;&nbsp;.&nbsp;(Electrum 등과 같은 라이트 클라이언트는 작동하지 않습니다…)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>전체 노드 클라이언트를 시작하고 완전히 동기화하도록 허용합니다.&nbsp;인터넷 연결 및 컴퓨터에 따라 노드를 완전히 동기화하는 데 하루 이상이 걸릴 수 있습니다.&nbsp;옵션으로 시작&nbsp;&nbsp;<code>bitcoin-qt</code>&nbsp;(또는&nbsp;&nbsp;<code>bitcoind</code>)하면&nbsp;&nbsp;<code>-dbcache #</code>&nbsp;도움이 될 수 있습니다. 는&nbsp;&nbsp;<code>#</code>&nbsp;데이터베이스 캐시에 사용할 RAM의 양(MB)입니다.&nbsp;컴퓨터에 최소 8GB의 RAM이 있는 경우 최대&nbsp;&nbsp;<code>4000</code>&nbsp;MB&nbsp; 까지 할당하면&nbsp;<code>-dbcache</code>&nbsp;속도가 빨라집니다.&nbsp;SSD가 있는 컴퓨터에 비트코인을 설치하는 것도 도움이 될 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>풀 노드 클라이언트가 동기화되면 풀 노드 클라이언트 소프트웨어를 닫습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>(OS X에서는&nbsp;&nbsp;<code>create-address-db.py</code>&nbsp;스크립트 파일의&nbsp; 이름을 로 바꿉니다.) 완전히 동기화된 블록체인을 사용하여 주소 데이터베이스를 구축하려면&nbsp;&nbsp;스크립트(와 같은 폴더에 있음&nbsp; )&nbsp;<code>create-address-db.command</code>를 두 번 클릭합니다&nbsp; (&nbsp;&nbsp;이름과&nbsp;&nbsp;동일한 디렉터리에 저장됨&nbsp;&nbsp;) .&nbsp;.&nbsp;이 프로세스는 약 1시간이 소요되며 약 4GB의 RAM과 드라이브 공간을 모두 사용합니다.<code>create-address-db.py</code><code>seedrecover.py</code><code>create-address-db.py</code><code>addresses.db</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Creating_and_Using_AddressDB/#running-seedrecoverpy">Running&nbsp;&nbsp;<em>seedrecover.py</em></a>&nbsp;섹션 에 나열된 단계를 따르십시오&nbsp;&nbsp;&nbsp;. 단, 4단계에서 주소 입력 창이 나타나면 을 클릭합니다&nbsp;&nbsp;<code>Cancel</code>.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다음 단계에서는 여전히 주소 생성 제한을 선택해야 합니다.&nbsp;이것은 처음 사용하기 전에 지갑 시작 부분에 있다고 의심되는 미사용 주소의 수여야 합니다.&nbsp;지갑의 첫 번째 주소를 사용한 것이 확실한 경우&nbsp;&nbsp;<code>1</code>&nbsp;여기에서 사용할 수 있지만 확실하지 않은 경우 더 높은 추정치를 선택해야 합니다(&nbsp;&nbsp;<em>seedrecover.py를</em>&nbsp;&nbsp;실행하는 데 시간이 더 오래 걸릴 수 있음).</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>AddressDB로 실행하면 주소 데이터베이스로 실행하는 동안 AddressDB 파일 크기와 거의 동일한 양의 RAM이 사용됩니다.&nbsp;(예: Full Bitcoin AddressDB는 2019년 11월 현재 약 8.5GB의 RAM이 필요합니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="creating-an-addressdb-from-an-address-list">주소 목록에서 AddressDB 생성</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>addressDB를 생성하는 다른 방법은 주소 목록을 사용하는 것입니다.&nbsp;(예: Google BigQuery와 같은 것의 모든 Eth 주소 목록)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>–inputlist 매개 변수를 사용하여 입력 목록을 지정하고 사용하려는 dblength를 지정하기만 하면 됩니다.&nbsp;(그렇지 않으면 기본적으로 30으로 설정되어 8GB 파일 생성) bigquery에서 Google Cloud Storage로 데이터를 내보낼 때 자동으로 생성된 파일 목록을 자동으로 포함할 수 있도록 –multifileinputlist도 필요할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>여러 목록의 주소를 결합하거나 기존 블록체인 생성 addressDB에 주소 목록을 추가하려는 경우 –update 인수를 사용하여 이를 수행할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>약 1,000만 개의 주소가 있는 파일을 추가하는 데 약 1분 정도 소요됩니다… (BigQuery Eth 데이터의 성능 기준)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="generating-address-lists-from-google-bigquery">Google BigQuery에서 주소 목록 생성</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em><strong>참고:</strong>&nbsp;&nbsp;Google BigQuery의 데이터는 1~2개월마다 업데이트되며 때로는 덜 자주 업데이트되므로 AddressDB를 생성하는 데 사용하는 데이터 세트에 대한 "마지막 수정" 정보를 확인하여 관련 트랜잭션이 포함되어 있는지 확인하십시오. 지갑으로…</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>유용한 Google BigQuery 쿼리</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:05c3cbf256dd43a898f5168b94bc66cc">모든 BTC 주소</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:c6370cf863224be1942ecfdf03e0f0ca">모든 ETH 주소</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:c130730990e94212bf20b3dea5c4c815">모든 총독 주소</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:1cb1a218b17d4498bb3d9103e5b2fb3a">모든 BCH 주소</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://console.cloud.google.com/bigquery?sq=871259226971:13e998b9bf864df8b7c0772f4913b28d">모든 LTC 주소</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="generating-address-lists-using-ethereum-etl">Ethereum-ETL을 사용하여 주소 목록 생성</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>작동 확인: * Geth 노드가 설치된 Binance 스마트 체인:&nbsp;&nbsp;<a href="https://docs.bnbchain.org/docs/validator/fullnode">https://docs.bnbchain.org/docs/validator/fullnode</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>EVM 유형 체인(예: Binance Smart Chain)의 경우 다른 옵션은 Ethereum-ETL 도구를 사용하는 것입니다.&nbsp;이를 통해 전체 노드(Running Geth 또는 Parity 또는 이들의 포크)를 쿼리하고 트랜잭션을 나타내는 사람이 읽을 수 있는 CSV 데이터를 검색할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Geth-Like 노드가 실행되면 다음과 같은 명령을 사용하여 ETL 데이터를 검색할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>ethereumetl export_blocks_and_transactions --start-block STARTBLOCKNUMBER --end-block ENDBLOCKNUMBER --provider-uri http://FULLNODEIP:8545 --blocks-output LOCAL_BLOCKS_CSV_FILE --transactions-output LOCAL_TRANSACTIONS_CSV_FILE</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>트랜잭션을 내보낸 후에는&nbsp;&nbsp;&nbsp;이 리포지토리 내의 폴더&nbsp;<code>addrListsFromETLTransactions.py</code>&nbsp;에 있는 파일을&nbsp; 사용하여 주소 목록이 포함된 파일을 생성할 수 있습니다.&nbsp;<code>utilities</code>그런 다음 이러한 주소 목록을 사용하여 앞에서 설명한 것과 동일한 프로세스를 사용하여 addressDB를 만들 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 접근 방식에서 이해해야 할 핵심 사항은 저장/실행을 위해 몇 TB 상당의 디스크 공간이 필요하고 전체 Ethereum ETL 출력을 위해 몇 TB 상당의 추가 공간이 필요하다는 것입니다.&nbsp;(따라서 약 10TB의 공간이 필요할 것입니다…)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="checkingvalidating-addressdbs">AddressDB 확인/검증</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>check-address-db.py 파일을 사용하여 addresslist 파일에 지정된 주소가 포함되어 있는지 여부를 테스트할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>예를 들어 다음 명령을 사용하여 Dogecoin AddressDB(위에서 다운로드 가능)에 몇 가지 특정 주소가 포함되어 있는지 확인할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>python3 check-address-db.py --dbfilename "E:\CryptoGuide\OneDrive\AddressDBs (Mega)\addresses-DOGE.db" --checkaddresses DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>그러면 다음과 같은 출력이 생성됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>Starting CheckAddressDB 1.9.0-CryptoGuide
Loading address database ...
Loaded 60750752 addresses from database ...
DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T Found!
DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU Found!
DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN Found!
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>체크리스트 파일</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>BTCRecover 리포지토리는 addressDB에 특정 시간 간격 동안 처음 시드된 주소가 포함되어 있는지 확인하는 데 사용할 수 있는 몇 가지 기본 주소 목록과 함께 번들로 제공됩니다.&nbsp;이 주소는 블록체인에서 무작위로 선택되었으며 약 6개월 간격으로 배치됩니다.&nbsp;(따라서 주어진 addressDB가 필요한 날짜를 대략적으로 포함하는지 확인하는 데 사용할 수 있습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>예를 들어 명령을 사용하여 Dogecoin AddressDB(위에서 다운로드 가능)에 2021년 2월까지의 주소가 포함되어 있는지 확인할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>python3 check-address-db.py --dbfilename addresses-DOGE.db --checkaddresslist ./addressdb-checklists/DOGE.txt
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>그러면 다음과 같은 출력이 생성됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>Starting CheckAddressDB 1.9.0-CryptoGuide
Loading address database ...
Loaded 60750752 addresses from database ...
Loading:  ./addressdb-checklists/DOGE.txt
DMQ6uuLAtNoe5y6DCpxk2Hy83nYSPDwb5T Found! First Seen 2021-01-31
DFgLZmxFnzv2wR4GAGS3GeHvoEeSkz9ubU Found! First seen 2020-06-29
DKTHYZwd81xT7qJF33YRi7ftDkvouGdxxN Found! First seen 2019-12-30
DPPg5BVqn7Ck5YVf6ei7NbXGVPDSzXnCBL Found! First seen 2019-05-17
DBbTFW9PZJj9EsXu5Ji59Tp6ZdKNrTZmWq Found! First seen 2018-12-05
DFJRDVzjk7NPbApWsLDreML7RDawp8UmoF Found! First seen 2018-05-16
D9dWXJjYb4HDrXpdef234GHDDggrnGsfxm Found! First seen 2017-11-05
D6A894uLhQjwSRpEroPMop4MPpUL4BZZHc Found! First seen 2017-05-19
DGVxem7KdNBCJWygpRcypS5pMJgJVRZEXD Found! First seen 2016-12-25
DMPHyer3WdKrSmwmFarXtXCxbbp4BMwo9J Found! First seen 2016-05-22
DRusoAd1Q9PJq3KpkhXjpZAoCqdQzGS6AH Found! First seen 2015-12-29
D6sxvQRSriU4pkozdYxDVRKRmoRYCVmqKv Found! First seen 2015-05-10
DNULsd2gbojENHtRRx45PUWvPgkrbL2vjE Found! First seen 2014-12-15
D5mrYgNeLwVXFyy9t9NhBpTqVaa58gUYAC Found! First seen 2014-04-29
DLAznsPDLDRgsVcTFWRMYMG5uH6GddDtv8 Found! First seen 2013-12-07
</code></pre>
<!-- /wp:code -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="token-lists-and-password-or-seed-lists">토큰 목록 및 암호 또는 시드 목록</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>암호 및 시드 복구 방법 모두 토큰 파일과 암호/시드 목록 파일을 모두 사용할 수 있습니다.&nbsp;비밀번호 복구를 위해서는 이들 중 적어도 하나가 필요합니다.&nbsp;(그리고 일부 유형의 시드 복구, 예: 시드 구 스크램블링에 필요할 수 있음)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>암호/시드 목록 파일을 사용하면 암호 생성 작업과 테스트 작업을 두 단계로 분리하여 사용자가 암호 생성을 위해 PYPY가 제공하는 속도 향상, 테스트 속도 향상의 이점을 누릴 수 있습니다. cpython에서는 여러 서버에서 많은 수의 암호를 테스트하는 작업을 쉽게 분할할 수 있습니다.&nbsp;(또는 더 강력하고 비싼 시스템에서 테스트하는 작업과 별도로 암호 목록을 만드는 단일 스레드 작업 수행)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>비밀번호 목록 파일과 토큰 파일 모두 아래에 자체 문서가 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/passwordlist_file/">암호/시드 목록 파일</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/tokenlist_file/">토큰 목록 파일</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="typos">오타</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover는</em>&nbsp;&nbsp;암호를 입력하거나 기록하는 동안 실수로 저지른 오타나 실수를 찾기 위해 다양한 암호 변형을 생성할 수 있습니다.&nbsp;<em>이 기능은 btcrecover 를</em>&nbsp;실행할 때 하나 이상의 명령줄 옵션을 포함하여 활성화됩니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>추가할 수 있는 명령줄 옵션의 특정 예를 보려면&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Typos_Quick_Start_Guide/">Typos 빠른 시작 가이드 를</a>&nbsp;참조하십시오 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--typos #</code>&nbsp;명령줄 옵션(&nbsp;&nbsp;<code>#</code>&nbsp;오타 수로 대체됨)을&nbsp;&nbsp;사용하여&nbsp;&nbsp;<em>btcrecover</em>&nbsp;&nbsp;에 각 비밀번호(토큰 파일에서 생성되었거나 전술 한 바와).&nbsp;또한 생성할 오타 유형을 지정해야 하며, 가능한 모든 조합을 거칩니다(오타가 없을 가능성 포함).&nbsp;다음은 각 유형을 활성화하는 명령줄 옵션과 함께 기본 유형의 오타에 대한 요약입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-capslock</code>&nbsp;– Caps Lock을 켠 상태에서 전체 암호 시도</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-swap</code>&nbsp;– 인접한 두 문자를 바꿉니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-repeat</code>&nbsp;– 문자 반복(이중)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-delete</code>&nbsp;– 문자를 삭제합니다</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-case</code>&nbsp;– 단일 문자의 대/소문자 변경</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>예를 들어 명령줄에 옵션을 지정하면&nbsp;&nbsp;&nbsp;(오타 없음),&nbsp;&nbsp;&nbsp;(오타 1개: caps lock),&nbsp;&nbsp;&nbsp;(오타 2개: 모두 반복) 및&nbsp;&nbsp;&nbsp;(오타 2개: 1개와 같이&nbsp;<code>--typos 2 --typos-capslock --typos-repeat</code>&nbsp;최대 2개의 오타를 포함하는 모든 조합이 시도됩니다.&nbsp;&nbsp;각 유형)을 시도합니다.&nbsp;명령줄에 많은 오타 유형을 추가하면 조합 수가 크게 증가할 수 있으며 개수를 늘리는 것은&nbsp;&nbsp;&nbsp;훨씬 더 극적일 수 있으므로 작은 토큰 파일이나 암호 목록이 없는 경우 이 기능을 사용할 때 가볍게 밟는 것이 가장 좋습니다.<code>Cairo</code><code>cAIRO</code><code>CCairoo</code><code>cAIROO</code><code>--typos</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>다음은 약간의 추가 설명이 필요한 추가 유형의 오타입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-closecase</code>&nbsp;– 와 같지만&nbsp;&nbsp;<code>--typos-case</code>해당 문자가 대소문자가 다른 문자 옆에 있거나 시작 또는 끝에 있는 경우에만 문자의 대소문자 변경을 시도합니다.&nbsp;이렇게 하면 시도할 조합이 적어지므로 더 빠르게 실행되며 누군가 shift를 너무 오래 누르거나 충분히 오래 누르지 않는 경우를 여전히 포착합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-replace s</code>&nbsp;– 각 단일 문자를 지정된 문자열(예: an&nbsp;&nbsp;<code>s</code>)로 바꾸려고 시도합니다.&nbsp;문자열은 단일 문자이거나 더 긴 문자열(이 경우 각 단일 문자가 전체 문자열로 대체됨) 또는 하나 이상의&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">확장 와일드카드</a>&nbsp;가 &nbsp;포함된 문자열일 수 있습니다.&nbsp;예를 들어&nbsp;&nbsp;<code>--typos 1 --typos-replace %a</code>&nbsp;각 문자(한 번에 하나씩)를 소문자로 바꾸고 가능한 모든 조합을 시도합니다.&nbsp;와일드카드를 사용하면 총 조합 수가 크게 증가할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>--typos-insert s</code>&nbsp;– 와 비슷&nbsp;&nbsp;<code>--typos-replace</code>하지만 문자를 교체하는 대신 각 문자 쌍 사이와 처음과 끝에 문자열의 단일 복사본(또는 와일드카드 대체)을 삽입하려고 시도합니다. 이 1보다 큰 경우&nbsp;&nbsp;<code>--typos</code>&nbsp;에도&nbsp;&nbsp;<code>--typos-insert</code>&nbsp;일반적으로 동일한 위치에 문자열의 여러 복사본을 삽입하려고 시도하지 않습니다.&nbsp;예를 들어, 지정된 경우&nbsp;&nbsp;&nbsp;and&nbsp;&nbsp;<code>--typos 2 --typos-insert Z</code>&nbsp;와 같은 추측은&nbsp;&nbsp;&nbsp;시도되지만 시도되지&nbsp;&nbsp;&nbsp;는 않습니다.&nbsp;&nbsp;1보다 큰 숫자와 함께&nbsp;사용하여 이를 변경할 수 있습니다&nbsp; .<code>CaiZro</code><code>CZairoZ</code><code>CaiZZro</code><code>--max-adjacent-inserts #</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4 id="typos-map">타이포스 지도</h4>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>--typos-map typos.txt</code>&nbsp;– 이것은 비교적 복잡하지만 유연한 유형의 오타입니다.&nbsp;<code>typos.txt</code>세부 정보를 설명하기 위해&nbsp;별도의 파일(이 예에서는 )을 사용하여 특정 특정 문자를 특정 다른 특정 문자로 바꾸려고 시도합니다&nbsp; .&nbsp;<code>. ,/; ; [‘/.&nbsp;</code>예를 들어&nbsp;&nbsp;구두점을 자주 실수하는 경우 다음 두 줄이 포함된 오타 맵 파일을 만들&nbsp;&nbsp;수&nbsp;<em>있습니다</em>&nbsp;&nbsp;.&nbsp; 같은 줄에 있고&nbsp;&nbsp;그 뒤에 오는 4개의 구두점 중 하나로&nbsp;<code>.</code>각각을 바꾸려고 시도합니다.&nbsp; 이 기능은 단순한 오타 이상으로 사용할 수 있습니다.&nbsp;<code>;</code>예를 들어 "1337"(leet)의 팬이라면 암호를 입력하고 다음 줄에 따라 오타 맵을 만들 수 있습니다.<code>aA @ sS $5 oO 0&nbsp;</code>옵션으로 지정된 최대 오타 수까지&nbsp;&nbsp;<code>a</code>&nbsp;or&nbsp; 의 인스턴스를&nbsp;<code>A</code>&nbsp;로&nbsp;&nbsp;<code>@</code>,&nbsp;&nbsp;<code>s</code>&nbsp;또는&nbsp; 의 인스턴스를&nbsp;<code>S</code>&nbsp;a&nbsp;&nbsp;<code>$</code>&nbsp;또는 a&nbsp; 등으로&nbsp;바꾸려고 합니다&nbsp;&nbsp;&nbsp;.&nbsp;예를 들어, 토큰 파일에 토큰이 포함되어 있고 를&nbsp;&nbsp;지정한 경우&nbsp;&nbsp;&nbsp;각각 3개 이하의 오타/교체가 있기 때문에 둘 다 시도되지만&nbsp;&nbsp;&nbsp;5&nbsp;&nbsp;&nbsp;개의 ​​오타는 시도되지 않습니다.&nbsp;&nbsp;<em>btcrecover</em>&nbsp;&nbsp;패키지에는 몇 가지 오타가 포함되어 있습니다&nbsp;.&nbsp; 디렉토리&nbsp;의 예제 파일을 매핑합니다&nbsp;&nbsp;&nbsp;.&nbsp;Typos 빠른 시작 가이드에서 자세한 내용을 읽을 수 있습니다.<code>5</code><code>--typos #</code><code>Passwords</code><code>--typos 3</code><code>P@55words</code><code>Pa$sword5</code><code>P@$$w0rd5</code><em></em><code>typos</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 id="max-typos-by-type">유형별 최대 오타</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>위에서 설명한 것처럼&nbsp;&nbsp;<code>--typos #</code>&nbsp;명령줄 옵션은 유형에 관계없이 단일 추측에 적용되는 총 오타 수를 제한합니다.&nbsp;특정 유형의 오타에만 적용되는 제한을 설정할 수도 있습니다.&nbsp;위 의 각&nbsp;&nbsp;<code>--typos-xxxx</code>&nbsp;명령줄 옵션에 해당하는 옵션이 있습니다&nbsp;&nbsp;<code>--max-typos-xxxx #</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>예를 들어 를 사용하면&nbsp;&nbsp;<code>--typos 3 --typos-delete --typos-insert %a --max-typos-insert 1</code>최대 3개의 오타가 시도됩니다.&nbsp;모두 삭제 오타일 수 있지만 최대 하나만 삽입 오타(이 경우 단일 소문자 삽입)가 됩니다.&nbsp;이는 이 예에서와 같이 와일드카드와 함께 사용할 때 특히 유용합니다&nbsp;&nbsp;<code>--typos-insert</code>&nbsp;.&nbsp;&nbsp;<code>--typos-replace</code>&nbsp;시도해야 하는 총 조합 수를 크게 줄여서 테스트하는 데 너무 오래 걸리는 총 수를 훨씬 더 합리적인 조합으로 바꿀 수 있기 때문입니다. .</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="typos-gory-details">오타 피투성이 세부 사항</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>오타 기능의 의도는 단일 암호 추측에 여러 오타를 적용하는 경우에도 단일 문자에 한 번에 최대 하나의 오타만 적용하는 것입니다.&nbsp;예를 들어 를 지정할 때&nbsp;&nbsp;<code>--typos 2 --typo-case --typo-repeat</code>각 암호 추측에는 최대 2개의 오타가 적용될 수 있습니다(따라서&nbsp;&nbsp;&nbsp;최대 2개의 대소문자 변경, 2개의 반복 문자 또는 1개의 대소문자 변경과 1개의 반복&nbsp;<strong>문자</strong>&nbsp;&nbsp;)&nbsp;&nbsp;<strong>.&nbsp;</strong>추측의 단일 문자에는 단일 추측에서 하나 이상의 오타가 적용되지 않습니다. 예를 들어 단일 문자는 절대로 동시에 반복되고 대소문자가 변경되지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그러나이 문자 당 하나의 오타 규칙에는 몇 가지 예외가 있습니다. 하나는 의도적이며 다른 하나는 소프트웨어의 제한 사항입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>오타&nbsp;&nbsp;<code>--typos-capslock</code>&nbsp;는 추측하는 동안 Caps Lock을 켠 상태로 두는 것을 시뮬레이트합니다.&nbsp;하나의 오타라도 한 번에 비밀번호의 모든 문자에 영향을 미칠 수 있습니다.&nbsp;문자당 1타자 규칙을 제외하고 한 글자가&nbsp;&nbsp;&nbsp;Caps Lock 오타와 다른 오타의 영향을 동시에 받을&nbsp;<em>수 있습니다 .</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>오타 는&nbsp;&nbsp;<code>--typos-swap</code>&nbsp;또한 문자당 하나의 오타 규칙을 무시합니다.&nbsp;두 개의 인접한 문자를 바꿀 수 있으며(하나의 오타로 계산) 두 번째 오타를 교체된 문자 중 하나(또는 둘 다)에 적용할 수 있습니다.&nbsp;이것은 디자인 선택보다 소프트웨어 제한에 가깝지만 변경될 가능성은 없습니다.&nbsp;그러나 단일 문자가 추측당 한 번 이상 교체되지 않는다는 것을 보장합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>마지막으로 오타가 적용되기 전에 와일드카드 대체(확장 및 축소)가 발생하며 오타가 와일드카드 확장 결과에 적용될 수 있다는 점에 유의해야 합니다.&nbsp;비밀번호 생성의 정확한 순서는 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>모든 토큰 규칙(상호 배제, 앵커 등)에 따라 하나 이상의 토큰에서 "기본" 암호를 만듭니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>모든 와일드카드 확장 및 축소를 적용합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>최대 단일 Caps Lock 오타를 적용합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>0개 이상의 스왑 오타를 적용합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>0개 이상의 문자 변경 오타를 적용합니다(이러한 오타는&nbsp;&nbsp;&nbsp;문자당 하나의 오타 규칙을 따릅니다)&nbsp;<em>.</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>0개 이상의 오타 삽입을 적용합니다(&nbsp;&nbsp;<code>typos-insert</code>&nbsp;옵션에서).</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>단일 추측의 총 오타 수는 옵션으로 요청된 것보다 많지 않습니다&nbsp; (&nbsp;&nbsp;사용된 경우 옵션&nbsp;<code>--typos #</code>&nbsp;보다 적지 않음&nbsp; ).<code>--min-typos</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="autosave">자동 저장</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>시도해야 하는 암호의 수에 따라&nbsp;&nbsp;<em>btcrecover를</em>&nbsp;실행하는 데 &nbsp;시간이 오래 걸릴 수 있습니다.&nbsp;테스트 도중에 중단되면(Ctrl-C(아래 참조), 재부팅으로 인해, 실수로 명령 프롬프트를 닫는 등의 이유로) 진행 상황을 잃을 수 있으며 처음부터 다시 검색을 시작해야 합니다. 처음.&nbsp;이를 방지하기 위해&nbsp;&nbsp;<em>btcrecover를</em><code>--autosave savefile</code>&nbsp;&nbsp;처음 시작할 때 옵션을&nbsp; 추가할 수 있습니다&nbsp;.&nbsp;약 5분마다 진행 상황을 지정한 파일에 자동으로 저장합니다&nbsp;&nbsp;&nbsp;.<em></em><code>savefile</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>중단된 경우 완전히 동일한 옵션으로 실행하거나 이 옵션만 제공하여 테스트를 다시 시작할 수 있습니다.&nbsp;&nbsp;<code>--restore savefile</code>.&nbsp;<em>그런 다음 btcrecover는</em>&nbsp;&nbsp;중단했던 지점에서 정확하게 테스트를 시작합니다.&nbsp;(token 파일과 typos-map 파일이 사용되는 경우 여전히 존재해야 하며 이것이 작동하려면 수정되지 않아야 합니다. 존재하지 않거나 변경된 경우 btcrecover는 시작을 거부&nbsp;&nbsp;<em>합니다</em>&nbsp;&nbsp;. .)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자동 저장 기능은 현재 암호 목록에서 지원되지 않으며 토큰 파일에서만 지원됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="interrupt-and-continue">중단하고 계속하기</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;테스트 도중에 btcrecover를 중단해야 하는 경우 Ctrl-C(Ctrl 키를 누른 상태에서 C를 누름)를 사용하면 다음과 같은 메시지로 응답한 다음 종료&nbsp;<em>됩니다</em>&nbsp;.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>Interrupted after finishing password # 357449
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>자동 저장 기능을 활성화하지 않은 경우 중단한 부분부터 수동으로 테스트를 시작할 수 있습니다.&nbsp;<em>정확히 동일한</em>&nbsp;&nbsp;토큰&nbsp;&nbsp;&nbsp;파일 또는 암호 목록, typos-map 파일(사용 중인 경우) 및 명령줄 옵션과 하나의 추가 옵션을 사용하여&nbsp;&nbsp;<em>btcrecover를</em>&nbsp;시작해야 합니다&nbsp;&nbsp;.<em></em><code>--skip 357449</code></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="unicode-support">유니코드 지원</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>암호에&nbsp;<a href="https://en.wikipedia.org/wiki/ASCII#ASCII_printable_code_chart">ASCII</a><code>--utf8</code>&nbsp;가 아닌(비영어) 문자가 포함된 경우 &nbsp;유니코드 지원을 활성화하려면 명령줄 옵션을&nbsp;&nbsp;추가해야 합니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>btcrecover</em>&nbsp;의 모든 입력 및 출력은&nbsp;&nbsp;&nbsp;UTF-8로 인코딩되어야 하므로(바이트 순서 표시 또는 "BOM"이 있거나 없음) 텍스트 파일을 저장할 때 인코딩을 UTF-8로 변경해야 합니다.&nbsp;예를 들어 Windows 메모장에서 파일&nbsp;&nbsp;<em>인코딩 설정은&nbsp;</em><em>파일</em>&nbsp;&nbsp;-&gt;&nbsp;&nbsp;<em>다른 이름으로 저장… 대화 상자의&nbsp;</em><em>저장</em>&nbsp;&nbsp;버튼&nbsp;&nbsp;&nbsp;바로 옆에 있습니다&nbsp;&nbsp;&nbsp;.<em></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Windows에서(일반적으로 Linux나 OS X에서는 아님) 사용해야 하는 명령줄 옵션에 ASCII가 아닌 문자가 포함되어 있으면 문제가 발생할 수 있습니다.&nbsp;일반적으로 입력했을 때 명령 프롬프트 창에 올바르게 표시되면&nbsp;&nbsp;<code>btcrecover.py</code>.&nbsp;올바르게 표시되지 않으면&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#command-line-options-inside-the-tokens-file">토큰 파일에 명령줄 옵션을</a>&nbsp;넣는 방법을 설명하는 섹션을 읽어보세요 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또한 Windows(일반적으로 Linux 또는 OS X는 아님)에서 암호를 찾으면 명령 프롬프트 창에 올바르게 표시되지 않을 수 있습니다.&nbsp;다음은 잘못된 출력의 예입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>Password found: 'btcr-????-??????'
HTML encoded:   'btcr-&amp;#1090;&amp;#1077;&amp;#1089;&amp;#1090;-&amp;#1087;&amp;#1072;&amp;#1088;&amp;#1086;&amp;#1083;&amp;#1100;'
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>보시다시피 Windows 명령 프롬프트는 일부 문자를 렌더링할 수 없었고&nbsp;&nbsp;<code>?</code>&nbsp;문자로 대체되었습니다.&nbsp;찾은 암호를 보려면 줄을 복사하여 텍스트 파일에 붙여넣고&nbsp;&nbsp;&nbsp;일반 대신 로&nbsp;&nbsp;<code>HTML encoded</code>&nbsp;끝나는 이름으로 저장합니다&nbsp;&nbsp;.&nbsp;새&nbsp;&nbsp;&nbsp;파일을 두 번 클릭하면 웹 브라우저에서 열리고 올바른 암호가 표시됩니다.<code>.html</code><code>.txt</code><code>.html</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>HTML encoded: 'btcr-тест-пароль'
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="running-btcrecover"><em>btcrecover</em>&nbsp;실행&nbsp;<em></em></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>(빠른 시작 섹션도 참조하십시오.) 모든 요구 사항(위)을 설치하고 최신 버전을 다운로드한 후:</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>파일 의 압축을 풀면&nbsp;&nbsp;<code>btcrecover-master.zip</code>&nbsp;"btcrecover-master"라는 단일 디렉토리가 포함됩니다.&nbsp;btcrecover-master 디렉토리 안에는 Python 스크립트(프로그램) 파일이 있습니다&nbsp;&nbsp;<code>btcrecover.py</code>.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong></strong> 이 포함된 디렉토리에  <strong>지갑 파일의 사본을 만드십시오</strong><code>btcrecover.py</code> . <em>Windows에서는 일반적으로 시작 메뉴 를</em> 클릭한 다음 “   실행  <code>r</code>… . 일부 지갑 소프트웨어를 사용하면 여러 개의 지갑을 만들 수 있습니다. 물론 올바른 지갑 파일을 복사했는지 확인해야 합니다.<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>BIP-39 암호 – 아래의 BIP-39 암호 섹션을 참조하십시오.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비트코인 코어 –&nbsp;&nbsp;<code>%appdata%\Bitcoin</code>&nbsp;(이름이&nbsp;&nbsp;<code>wallet.dat</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Android/BlackBerry용 비트코인 ​​지갑, 지출 PIN 분실 –&nbsp; 아래의&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#bitcoin-wallet-for-androidblackberry-spending-pins">Android/BlackBerry 지출 PIN용 비트코인 ​​지갑</a>&nbsp;&nbsp;섹션을 참조하십시오.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비더 –&nbsp;&nbsp;<code>%appdata%\Bither</code>&nbsp;(이름이&nbsp;&nbsp;<code>address.db</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Blockchain.com – 보통 이름이&nbsp;&nbsp;<code>wallet.aes.json</code>;&nbsp;지갑 파일의 백업이 없는 경우&nbsp;&nbsp;&nbsp;지갑 ID(활성화된 경우 2FA)를 알고 있는 경우 디렉터리&nbsp;<code>download-blockchain-wallet.py</code>&nbsp;에서 도구를&nbsp; 실행하여 다운로드할 수 있습니다.<code>extract-scripts</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Coinomi –&nbsp;&nbsp;&nbsp;아래&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-coinomi-wallet-files">Coinomi 지갑 파일 찾기 섹션을 참조하십시오.</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>일렉트럼 –&nbsp;<code>%appdata%\Electrum\wallets</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Litecoin-Qt –&nbsp;&nbsp;<code>%appdata%\Litecoin</code>&nbsp;(이름이&nbsp;&nbsp;<code>wallet.dat</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;메타마스크(및 바이낸스 체인 지갑, 로닌 지갑 등과 같은 메타마스크 클론) – 아래&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-metamask-wallet-files">메타마스크 지갑 파일 찾기</a>&nbsp;섹션 을 참조하십시오&nbsp; .</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit Classic –&nbsp; 아래의&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#finding-multibit-classic-wallet-files">MultiBit Classic 지갑 파일 찾기</a>&nbsp;&nbsp;섹션을 참조하십시오.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>MultiBit HD –&nbsp;&nbsp;<code>%appdata%\MultiBitHD</code>&nbsp;(여기 폴더 중 하나에 있으며 이름은&nbsp;&nbsp;<code>mbhd.wallet.aes</code>)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA –&nbsp;&nbsp;<code>%homedrive%%homepath%</code>&nbsp;(파일입니다&nbsp;&nbsp;<code>.vault</code>&nbsp;)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>파일이 있으면&nbsp;&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;거의 완료된 것입니다.&nbsp;이 파일을 포함하는 디렉토리에 복사한&nbsp;&nbsp;<code>btcrecover.py</code>다음&nbsp;&nbsp;<code>btcrecover.py</code>&nbsp;파일을&nbsp; 두 번 클릭하면&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;암호 테스트를 시작합니다.&nbsp;(파일 내부에 나열된 파일 이름과 일치하지 않는 경우 지갑 파일 이름을 변경해야 할 수 있습니다&nbsp;&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;.) 파일이 없으면&nbsp;&nbsp;<code>btcrecover-tokens-auto.txt</code>&nbsp;아래 내용을 계속 읽으십시오.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>파일&nbsp;&nbsp;<code>tokens.txt</code>&nbsp;또는 비밀번호 목록 파일을 사용하는 경우&nbsp;&nbsp;<code>btcrecover.py</code>.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>btcrecover.py</code>&nbsp;적어도 두 개의 명령줄 옵션으로&nbsp; 실행하여&nbsp;<code>--wallet FILE</code>&nbsp;지갑 파일 이름을 식별하고&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-token-file">토큰 파일</a>&nbsp;&nbsp;또는&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-passwordlist">비밀번호 목록을</a>&nbsp;사용하는지 여부에 따라&nbsp;&nbsp;<code>--tokenlist FILE</code>&nbsp;또는&nbsp;&nbsp;<code>--passwordlist FILE</code>&nbsp;( 파일은 의 경우 선택 사항임&nbsp; )&nbsp;를 식별해야 합니다&nbsp;&nbsp;.&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#typos">Typos</a>&nbsp;&nbsp;또는&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#autosave">Autosave를</a>&nbsp;사용하는 경우&nbsp;&nbsp;추가할 추가 옵션에 대해 위의 섹션을 참조하세요.<code>--passwordlist</code><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-token-file"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#the-passwordlist"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#typos"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#autosave"></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다음은 Windows 및 OS X에 대한 예입니다. 예를 들어 다운로드 위치가 다를 수 있거나 지갑 파일 이름이 다를 수 있으므로 시스템의 세부 정보가 다를 수 있으므로 일부 변경이 필요합니다. <em>추가 옵션은 모두 btcrecover</em> 줄 끝에 배치됩니다   .<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>Windows</em>&nbsp;: 명령 프롬프트 창을 열고(시작 메뉴를 클릭하고 "command" 입력) 아래 두 줄을 입력합니다.<code>cd Downloads\btcrecover-master python3 btcrecover.py --wallet wallet.dat --tokenlist tokens.txt [other-options...]</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>OS X</em>&nbsp;: 터미널 창을 열고(런치패드를 열고 "터미널" 검색) 아래 두 줄을 입력합니다.<code>cd Downloads/btcrecover-master python3 btcrecover.py --wallet wallet.dat --tokenlist tokens.txt [other-options...]</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>잠시 후&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;암호 테스트를 시작하고 아래와 같이 진행률 표시줄과 ETA를 표시합니다.&nbsp;진행률 표시줄이 없고 메시지만 나타나며 위쪽으로만 멈춘 것처럼 보이면&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Limitations_and_Caveats/#memory">메모리 제한</a><code>Counting passwords ...</code>&nbsp;섹션을 &nbsp;읽어보세요&nbsp;&nbsp;&nbsp;.&nbsp;그래도 도움이 되지 않는다면 테스트하기에는 너무 많은 토큰이나 오타를 선택하여 시스템이 처리할 수 있는 것보다 더 많은 조합이 생성되었을 수 있습니다(옵션이&nbsp;&nbsp;&nbsp;도움이 될 수도 있음).<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Limitations_and_Caveats/#memory"></a><a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#token-counts"><code>--max-tokens</code></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>Counting passwords ...
Done
Using 4 worker threads
439 of 7661527 &#91;-------------------------------] 0:00:10, ETA:  2 days, 0:25:56
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>조합 중 하나가 지갑의 올바른 암호인 경우 결국 암호가 표시되고&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;실행을 중지합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>1298935 of 7661527 &#91;####-----------------------] 8:12:42, ETA:  1 day, 16:13:24
Password found: 'Passwd42'
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>모든 암호 조합을 시도했지만 그 중 어느 것도 지갑에 적합하지 않은 경우 대신 이 메시지가 표시됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>7661527 of 7661527 &#91;########################################] 2 days, 0:26:06,
Password search exhausted
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>btcrecover.py</code>&nbsp;옵션 으로&nbsp;&nbsp;실행하면&nbsp;&nbsp;<code>--help</code>&nbsp;사용 가능한 모든 명령줄 옵션에 대한 요약이 제공되며, 대부분은 위 섹션에 설명되어 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="testing-your-config">구성 테스트</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>토큰 파일 및/또는 선택한 오타를 테스트하려는 경우&nbsp;&nbsp;&nbsp;아래와 같이 옵션&nbsp;&nbsp;<code>--listpass</code>&nbsp;대신 옵션을&nbsp; 사용할 수 있습니다.&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;지갑 파일에 대해 실제로 테스트하는 대신 화면에 대한 모든 암호를 나열합니다.&nbsp;이는 다른 유형의 지갑을 테스트할 수 있는 다른 도구가 있고&nbsp;&nbsp;<em>btcrecover</em>&nbsp;에서 테스트할 암호 목록을 가져올 수 있는 경우에도 유용할 수 있습니다 .&nbsp;이 옵션은 너무 많은 출력을 생성할 수 있으므로 짧은 토큰 파일과 오타 옵션이 거의 없는 경우에만 사용하는 것이 좋습니다.<code>--wallet FILE</code><em></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>    python3 btcrecover.py --listpass --tokenlist tokens.txt  | more
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>| more</code>&nbsp;마지막에 있는&nbsp;&nbsp;기호&nbsp; (&nbsp;<code>|</code>&nbsp;기호는 이동된&nbsp;&nbsp;<code>\</code>&nbsp;백슬래시임)는 각 화면의 암호 후에 일시 중지를 도입합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="extracting-yoroi-master-key">Yoroi 마스터 키 추출</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>크롬 기반 브라우저 지갑</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>먼저 Yoroi 지갑을 연 다음 브라우저에서 개발자 도구 열기를 활성화해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 "Application"(Chrome)으로 이동하여 "IndexedDB" 섹션으로 이동하고 "Yoroi-Schema"를 열고 "Key" 섹션으로 이동해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그러면 마스터 키 목록이 표시됩니다.&nbsp;아래와 같이 첫 번째 암호화 키를 원할 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/Yoroi_Extract_MasterKey_Chrome.jpg" alt="Yoroi_Masterkey"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>그런 다음 "해시" 필드를 클릭하고 복사를 선택할 수 있습니다.&nbsp;<code>--yoroi-master-password</code>&nbsp;이 문자열은 인수&nbsp;와 함께 사용할 문자열입니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Firefox 브라우저 지갑</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>확장자에 대한 .sqlite 파일에 직접 액세스하여 데이터를 찾을 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>확장 프로그램에 대한 브라우저 프로필 폴더(이 위치는 환경에 따라 다름)에서 찾을 수 있습니다.&nbsp;아래 스크린샷 맨 위에 있는 Windows 환경에서 이 파일이 발견된 예를 볼 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/Yoroi_Extract_MasterKey_Firefox.jpg" alt="Yoroi_Masterkey"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>그런 다음 텍스트 편집기로 간단히 열고 "Hash" 또는 "isEncrypted" 문자열을 찾으면 암호화된 마스터 암호가 일반 텍스트로 표시됩니다.&nbsp;(위 스크린샷에서 녹색으로 강조 표시된 부분)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--yoroi-master-password</code>&nbsp;이 문자열은 인수&nbsp;와 함께 사용할 문자열입니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-multibit-classic-wallet-files">MultiBit 클래식 지갑 파일 찾기</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover는</em>&nbsp;&nbsp;MultiBit Classic 지갑 파일에서 직접 작동하지 않고 대신 MultiBit 개인 키 백업 파일에서 작동합니다.&nbsp;MultiBit Classic 지갑에 처음 비밀번호를 추가한 후 새 수신 주소를 추가하거나 지갑 비밀번호를 변경할 때마다 MultiBit은 지갑 파일 근처의 디렉토리에 암호화된 개인 키 백업 파일을 생성합니다&nbsp;&nbsp;<code>key-backup</code>&nbsp;.&nbsp;이러한 개인 키 백업 파일은 암호를 시도하는 데 훨씬 더 빠르며(1,000배 이상)&nbsp;&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;이를 사용하는 이유입니다.&nbsp;MultiBit을 처음 설치할 때 생성되는 기본 지갑의 경우 이 디렉토리는 다음 위치에 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>%appdata%\MultiBit\multibit-data\key-backup
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>키 파일의 이름은&nbsp;&nbsp;<code>walletname-20140407200743.key</code>.&nbsp;추가 지갑을 만든 경우 해당&nbsp;&nbsp;<code>key-backup</code>&nbsp;디렉토리는 다른 위치에 있으며 위치를 찾는 것은 사용자에게 달려 있습니다.&nbsp;가지고 있으면 가장 최근 파일을 선택&nbsp; 하고&nbsp;&nbsp;사용할&nbsp;<code>.key</code>&nbsp;디렉토리에 복사하십시오&nbsp; .<code>btcrecover.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>MultiBit 개인 키 백업 파일 찾기에 대한 자세한 내용은&nbsp;&nbsp;<a href="https://www.multibit.org/en/help/v0.5/help_fileDescriptions.html" target="_blank" rel="noreferrer noopener">https://www.multibit.org/en/help/v0.5/help_fileDescriptions.html 을 참조하십시오.</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-metamask-wallet-files">메타마스크 지갑 파일 찾기</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Chrome 기반 브라우저의 경우 브라우저 확장 프로그램의 데이터 폴더를 찾아야 합니다.&nbsp;그런 다음 –wallet 인수와 함께 이 지갑 폴더의 경로를 사용합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask의 경우 %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\nkbihfbeogeaoehlefnkodbefgpgknn입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Binance Wallet Extension의 경우 %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fhbohimaelbohpjbbldcngcnapndodjp입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Ronin Wallet의 경우 %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fnjhmkhhmkbjkkabndcnnogagogbneec입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>가장 최근의 지갑 이외의 것을 복구하려는 경우 추출 스크립트를 사용하여 확장 데이터에 있는 가능한 모든 볼트를 나열해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Firefox 및 iOS의 경우 여기에 설명된 프로세스를 사용하여 메타마스크 볼트를 검색해야 합니다. -with-the-MetaMask-Vault-Data</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>모바일 지갑(iOS 및 Android)의 경우 BTCRecover를 전달하는 "지갑 파일"은 파일입니다.&nbsp;&nbsp;<code>persist-root</code>&nbsp;위의 프로세스를 사용하여 찾아 BTCRecover에서 직접 사용할 수 있습니다.&nbsp;(볼트 데이터만 추출하거나, 초과&nbsp;&nbsp;<code>\</code>&nbsp;문자를 제거하는 등의 작업이 모두 자동으로 처리됩니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Android 기기의 경우 대부분 "루팅된" 전화가 필요합니다.&nbsp;당신이 추구하는 파일은 다음과 같습니다&nbsp;<code>/data/data/io.metamask/files/persistStore/persist-root</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 Vault 데이터(Firefox 또는 추출 스크립트에서)를 텍스트 파일에 복사/붙여넣고 –wallet 인수와 함께 직접 사용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="finding-coinomi-wallet-files">Coinomi 지갑 파일 찾기</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고: 비밀번호로 보호되는 지갑만 지원합니다.&nbsp;"암호 없음", "생체 인식" 또는 "암호 + 생체 인식"을 선택한 경우 휴대폰 키 저장소의 정보도 필요합니다...(검색이 불가능할 수 있음)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Coinomi의 첫 번째 단계는 실행 중인 플랫폼에 따라 다릅니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Windows 사용자의 경우 단순히 %localappdata%\Coinomi\Coinomi\wallets로 이동하면 지갑 파일을 찾을 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Android 사용자의 경우 Coinomi에서 .wallet 파일에 액세스할 수 있는 루팅된 전화가 필요합니다.&nbsp;(data\data\com.coinomi.wallet\files\wallets 폴더에서 찾을 수 있습니다.) 특정 전화에서 루트 액세스 권한을 얻는 방법은 이 문서의 범위를 벗어나지만 전화를 루팅하는 일부 방법은 공장 초기화를 포함합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>거기에 여러 개의 지갑이 있고 어느 것이 올바른지 확실하지 않은 경우 각 지갑의 이름은 파일 끝에서 일반 텍스트로 찾을 수 있습니다.&nbsp;예를 보려면 ./btcrecover/test/test-wallets에서 이 저장소에 포함된 테스트 지갑을 참조하십시오.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="downloading-dogechaininfo-wallet-files">Dogechain.info 지갑 파일 다운로드</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이러한 종류의 지갑 파일 ID는 "개발자 도구" 기능을 통해 브라우저를 통해 다운로드됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>기본적으로 지갑에 로그인을 시도하고(비밀번호가 잘못된 경우에도) 이 프로세스의 일부로 다운로드되는 지갑 파일을 저장해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>브라우저에서 개발자 도구를 열고 doggechain.info 지갑 로그인 페이지에 있으면 다음 단계를 수행해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) 네트워크 탭을 선택합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) 지갑 ID 입력</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) 자리 표시자 암호를 입력합니다(아무거나 입력 가능).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) 로그인을 클릭합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) "응답"을 선택합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) API 항목을 선택합니다.&nbsp;(2fa를 활성화한 경우 약간 다르게 보일 수 있습니다. 이 단계에서도 2fa를 완료해야 할 수 있습니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) 지갑 데이터로 보이는 응답이 있으면 복사하여 텍스트 파일에 붙여넣습니다.&nbsp;이것은 당신의 지갑 파일입니다…</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/download_dogechain_wallet.png" alt="Dodgechain 지갑 다운로드"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="downloading-blockio-wallet-files">block.io 지갑 파일 다운로드</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이러한 종류의 지갑 파일 ID는 "개발자 도구" 기능을 통해 브라우저를 통해 다운로드됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>기본적으로 지갑에 로그인한 다음 "설정" 화면으로 이동하면 브라우저에서 "개발자 도구"를 열 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>1) 네트워크 탭을 선택합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>2) "현재 PIN" 필드에 자리 표시자 PIN을 입력합니다.&nbsp;(이것은 무엇이든 될 수 있습니다. 예: "123")</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>3) 새 비밀 PIN 필드에 자리 표시자 암호를 입력합니다.&nbsp;(무엇이든 될 수 있지만 유효해야 합니다. 예: btcrtestpassword2022)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>4) "비밀 PIN 변경"을 클릭합니다(비밀 PIN이 잘못되었다는 오류가 표시되지만 문제가 되지 않습니다...)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>5) "응답"을 선택합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>6) initialize_change_secrets 파일을 선택하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>7) 지갑 데이터로 보이는 응답이 있으면 복사하여 텍스트 파일에 붙여넣습니다.&nbsp;이것은 당신의 지갑 파일입니다…</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/Images/download_block_io_wallet.png" alt="블록 IO 지갑 다운로드"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="bitcoin-wallet-for-androidblackberry-spending-pins">Android/BlackBerry 지출 PIN용 비트코인 ​​지갑</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Android/BlackBerry용 비트코인 ​​지갑에는&nbsp; 선택적으로 활성화할 수 있는&nbsp;<em>지출 PIN</em>&nbsp;&nbsp;기능이 있습니다.&nbsp;지출 PIN을 분실한 경우&nbsp;&nbsp;<em>btcrecover를</em>&nbsp;사용하여 &nbsp;복구를 시도할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>Bitcoin Wallet 앱을 열고 메뉴 버튼을 누른 다음 안전을 선택하십시오.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>지갑 백업을</em>&nbsp;선택합니다&nbsp;&nbsp;.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>지갑 백업 파일을 보호하기 위해 비밀번호를 입력하고 확인을 누릅니다.&nbsp;나중을 위해 이 암호를 기억해야 합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>오른쪽 하단 모서리에 있는 아카이브 버튼을 누릅니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>지갑 백업 파일을 PC와 공유하는 방법을 선택합니다. 예를 들어 Gmail 또는 드라이브를 선택할 수 있습니다.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><em>이 지갑 백업 파일은 일단 PC에 저장되면 btcrecover</em>&nbsp;의 다른 지갑 파일처럼 사용할 수 있지만&nbsp; 한 가지 중요한 예외가 있습니다.&nbsp;<em>btcrecover 를</em>&nbsp;&nbsp;실행할 때&nbsp; 옵션을&nbsp;&nbsp;추가&nbsp;&nbsp;해야&nbsp;&nbsp;<strong>합니다</strong><code>--android-pin</code>&nbsp;&nbsp;.&nbsp;그렇게 하면&nbsp;&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;백업 암호를 묻고(3단계에서) 지출 PIN 복구를 시도합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>PIN에는 일반적으로 숫자만 포함되므로 토큰 파일에는 일반적으로 다음과 같은 항목만 포함됩니다(예: 최대 6자리 PIN의 경우)&nbsp;&nbsp;<code>%1,6d</code>.&nbsp;&nbsp;( 자세한 내용은&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/TUTORIAL/#expanding-wildcards">와일드카드</a>&nbsp;섹션을 참조하십시오&nbsp; .)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>--android-pin</code>&nbsp;옵션을&nbsp;&nbsp;포함하지 않으면&nbsp;&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;대신 백업 암호 복구를 시도합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="bip-39-passphrases-electrum-extra-words">BIP-39 암호 및 Electrum "추가 단어"</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>일부&nbsp;&nbsp;<a href="https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki">BIP-39</a>&nbsp;&nbsp;준수 지갑은 시드(니모닉)에 "25번째 단어", "BIP-39 암호" 또는 " 그럴듯한 부인 가능성 암호"를 추가하는 기능을 제공합니다(대부분의 하드웨어 지갑은 지원되지 않는 PIN 기능도 제공합니다. by&nbsp;&nbsp;<em>btcrecover</em>&nbsp;.)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>시드를 알고 있지만 이 암호가 기억나지 않는 경우&nbsp;&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;도움이 될 수 있습니다.&nbsp;또한 다음 중 하나를 알아야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>가급적 마스터 공개 키/"xpub"(&nbsp;&nbsp;&nbsp;지갑의&nbsp;&nbsp;<em>첫 번째 계정용, 여러 계정을 지원하는 경우)&nbsp;</em><em>또는</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>지갑에서 생성한 수신 주소(첫 번째 계정)와 사용하려는 수신 주소 이전에 생성한 주소의 대략적인 추정치.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>이 정보가 있으면&nbsp;&nbsp;<em>btcrecover를</em>&nbsp;&nbsp;정상적으로 실행하십시오. 단,&nbsp;&nbsp;&nbsp;위에서 설명한 옵션과 같이 명령줄에 지갑 파일을 제공하는 대신&nbsp;&nbsp;<em>다음</em><code>--wallet wallet.dat</code>&nbsp;과 같은 옵션을 &nbsp;사용하십시오&nbsp;&nbsp;<code>--bip39</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 btcrecover.py --bip39 --tokenlist tokens.txt &#91;other-options...]
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>복구하려는 주소/계정이 BIP39/44 지갑에 있지만 Bitcoin 이외의 통화인 경우 인수를 사용하고&nbsp;&nbsp;<code>--wallet-type</code>&nbsp;seedrecover.py에서 지원하는 지원되는 BIP39 지갑 유형을 지정할 수 있습니다.&nbsp;(예: bch, bip39, bitcoinj, dash, digibyte, dogecoin, ethereum, electrum2, groestlecoin, litecoin, monacoin, ripple, vertcoin, zilliqa) 파생 체계를 공유하는 지원되지 않는 코인으로 복구를 시도할 수도 있습니다.&nbsp;<code>--bip32-path</code>&nbsp;해당 코인의 파생 경로가 있는 인수&nbsp;.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자세한 내용은&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/btc-recover-crypto-guide/#en/latest/bip39-accounts-and-altcoins/">BIP39 계정 및 알트코인 에 대한 참고 사항을 참조하십시오.</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>시드와 BIP39 암호가 모두 확실하지 않은 경우에는 seedrecover.py를 사용하고 여러 BIP39 암호를 지정해야 합니다.&nbsp;(그러나 이것은 매우 느립니다.)</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gpu-acceleration-for-bitcoin-core-and-litecoin-qt-wallets">Bitcoin Core 및 Litecoin-Qt 지갑을 위한 GPU 가속</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>btcrecover에는</em>&nbsp;&nbsp;하나 이상의 그래픽 카드 또는 전용 가속기 카드를 사용하여 검색 성능을 높이는 실험적 지원이 포함되어 있습니다.&nbsp;&nbsp;활성화되고 올바르게 조정되면 Bitcoin Unlimited/Classic/XT/Core 또는 Litecoin-Qt 지갑에서&nbsp;<em>100배</em>&nbsp;더 나은 성능을 제공할 수 있습니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>자세한 내용은 GPU 가속 가이드를 참조하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="command-line-options-inside-the-tokens-file">토큰 파일 내부의 명령줄 옵션</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>원하는 경우&nbsp;&nbsp;<code>tokens.txt</code>&nbsp;파일 내부에 직접 명령줄 옵션을 배치할 수도 있습니다.&nbsp;이렇게 하려면 토큰 파일의 첫 번째 줄은 정확히 로 시작해야 하며&nbsp;&nbsp;<code>#--</code>이 줄의 나머지 부분(및 이 줄만)은 추가 명령줄 옵션으로 해석됩니다.&nbsp;예를 들어 다음은 자동 저장, 종료 전 일시 중지 및 한 가지 유형의 오타를 활성화하는 토큰 파일입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>#--autosave progress.sav --pause --typos 1 --typos-case
Cairo
Beetlejuice Betelgeuse
Hotel_california
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="btcrecover-tokens-autotxt">btcrecover-tokens-auto.txt</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>일반적으로 btcrecover를</em>&nbsp;실행할 때&nbsp;&nbsp;&nbsp;토큰 파일 및 지갑 파일의 위치와 같은 최소한 몇 가지 옵션으로 실행해야 합니다.&nbsp;<code>--tokenlist</code>&nbsp;또는&nbsp;&nbsp;를 지정하지 않고 실행하면&nbsp;&nbsp;&nbsp;현재 디렉토리에&nbsp;<code>--passwordlist</code>이름이 지정된 파일이 있는지 확인하고&nbsp; 발견되면 토큰 목록에 해당 파일을 사용합니다.&nbsp;<code>btcrecover-tokens-auto.txt</code>원하는 경우 토큰 목록 파일 내에서 옵션을 지정할 수 있기 때문에(위 참조)&nbsp;&nbsp;&nbsp;명령줄을 전혀 사용하지 않고&nbsp;<em>btcrecover를 실행할 수 있습니다.&nbsp;</em><code>--pause</code>&nbsp;이 방법으로 실행하기로 결정한 경우 실행이 완료되면 명령 프롬프트 창이 즉시 닫히지 않도록 하는 옵션&nbsp;사용을 고려할 수 있습니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="limitations-caveats">제한 사항 및 주의 사항</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 id="beta-software">베타 소프트웨어</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 소프트웨어가 지갑 파일에 해를 끼칠 가능성은 거의 없지만&nbsp;&nbsp;<strong>지갑 사본으로만 실행하는 것이 좋습니다</strong>&nbsp;.&nbsp;특히 이 소프트웨어는&nbsp;&nbsp;<strong>어떠한 보증도 없이</strong>&nbsp;배포됩니다 .&nbsp;자세한 내용은 함께 제공되는 GPLv2 라이선스 조건을 참조하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 소프트웨어는 베타 소프트웨어이고 다른 베타 소프트웨어와 상호 작용하기 때문에 귀하가 찾도록 올바르게 구성한 암호를 찾지 못할 수도 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="additional-limitations-caveats">추가 제한 사항 및 주의 사항</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이러한 주제에 대한 자세한 내용은 별도의 제한 사항 및 주의 사항 문서를 참조하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>암호의 구분 기호, 공백 및 특수 기호</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>메모리 및 CPU 사용량</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>보안 문제들</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>오타 세부정보</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="download">다운로드</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/archive/master.zip">https://github.com/demining/CryptoDeepTools/archive/master.zip</a>&nbsp;&nbsp;에서&nbsp;&nbsp;전체&nbsp;&nbsp;<em>btcrecover 패키지를 다운로드할 수 있습니다.</em><a href="https://github.com/demining/CryptoDeepTools/archive/master.zip"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>단일 추출 스크립트만 다운로드하려면 아래에서 지갑 소프트웨어용 스크립트를 선택한 다음 마우스 오른쪽 버튼을 클릭하고 "다른 이름으로 링크 저장..." 또는 "다른 이름으로 대상 저장..."을 선택하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>비트코인 코어 –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bitcoincore-mkey.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bitcoincore-mkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>비더 -&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bither-partkey.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-bither-partkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>블록체인 기본 암호 –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-main-data.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-main-data.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>블록체인 두 번째 암호 –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-second-hash.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-blockchain-second-hash.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>일렉트럼 1.x –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum-halfseed.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum-halfseed.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>일렉트럼 2.x –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum2-partmpk.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-electrum2-partmpk.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>mSIGNA –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-msigna-partmpk.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-msigna-partmpk.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>멀티비트 클래식 -&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-privkey.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-privkey.py</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>멀티비트 HD –&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-hd-data.py">https://github.com/demining/CryptoDeepTools/raw/main/17BTCRecoverCryptoGuide/extract-scripts/extract-multibit-hd-data.py</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Windows를 사용하는 경우 Python 3.7 이상의 최신 버전도 설치해야 합니다.&nbsp;다른 지갑의 경우 여기 지침에 따라 Python을 설치하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="usage-for-bitcoin-core">비트코인 코어 사용</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>스크립트를 다운로드한 후&nbsp;&nbsp;<strong>wallet.dat 파일을 다른 폴더에 복사합니다</strong>&nbsp;&nbsp;(쉽게 하려면&nbsp;&nbsp;<em>extract-bitcoincore-mkey.py</em>&nbsp;와 동일한 폴더에 복사 ).&nbsp;Windows의 경우 시작 메뉴를 클릭한 다음 "실행..."을 클릭하고 다음을 입력하여 wallet.dat 파일이 포함된 Bitcoin 폴더를 엽니다.&nbsp;&nbsp;<code>%appdata%\Bitcoin</code>.&nbsp;여기에서 wallet.dat 파일을 복사하여 별도의 폴더에 붙여넣을 수 있습니다.&nbsp;다음으로 명령 프롬프트 창을 열고 다음과 같이 입력해야 합니다(다운로드한 스크립트의 위치에 따라 다르며 동일한 폴더에 wallet.dat의 복사본을 만들었다고 가정).</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-bitcoincore-mkey.py wallet.dat
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>결과적으로 다음과 같은 메시지가 나타납니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>Bitcoin Core encrypted master key, salt, iter_count, and crc in base64:
lV/wGO5oAUM42KTfq5s3egX3Uhk6gc5gEf1R3TppgzWNW7NGZQF5t5U3Ik0qYs5/dprb+ifLDHuGNQIA+8oRWA==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>대신 pywallet에 의해 생성된 Bitcoin Core 지갑의 덤프 파일이 있는 경우 대신 extract-bitcoincore-mkey-from-pywallet.py</em>&nbsp;스크립트를 사용하는 것을 제외하고 동일한 지침을 따르십시오&nbsp;&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>귀하(또는 다른 사람)가&nbsp; 암호를 검색하기 위해&nbsp;<em>btcrecover를</em>&nbsp;실행할 때 &nbsp;지갑 파일이 필요하지 않으며&nbsp;&nbsp;<em>extract-bitcoincore-mkey.py</em>&nbsp;의 출력만 필요합니다 .&nbsp;예제를 계속하려면 다음을 수행하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; lV/wGO5oAUM42KTfq5s3egX3Uhk6gc5gEf1R3TppgzWNW7NGZQF5t5U3Ik0qYs5/dprb+ifLDHuGNQIA+8oRWA==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="bitcoin-core-technical-details">비트코인 핵심 기술 세부 사항</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-bitcoincore-mkey.py&nbsp;&nbsp;&nbsp;스크립트는 의도적으로 짧으며 모든 Python 프로그래머가 쉽게 읽을 수 있어야 합니다&nbsp;<em>.&nbsp;</em>Python bsddb.db(또는 이 모듈을 사용할 수 없는 경우 Pure Python 구현) 또는 SQLite를 사용하여 wallet.dat 파일을 연 다음 키 문자열이 있는 단일 키/값 쌍을 추출합니다&nbsp;&nbsp;<code>\x04mkey\x01\x00\x00\x00</code>.&nbsp;이 키/값 쌍에는 비트코인 ​​코어 "마스터 키" 또는 간단히 mkey의 암호화된 버전과 mkey 해독을 시도하는 데 필요한 기타 정보, 특히 mkey 솔트 및 반복 횟수가 포함되어 있습니다.&nbsp;그런 다음 이 정보는 쉬운 복사/붙여넣기를 위해 base64 형식으로 변환되고 화면에 인쇄됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>암호화된 mkey는 btcrecover</em>&nbsp;에 유용&nbsp;&nbsp;하지만 비트코인 ​​주소나 개인 키 정보를 포함하지 않습니다.&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;다른 암호 조합을 시도하여 mkey 암호 해독을 시도할 수 있습니다.&nbsp;그것이 성공한다면, 그것과 그것을 실행하는 사람은 당신의 지갑 파일에 대한 암호를 알게 될 것입니다. 그러나 지갑 파일의 나머지 부분이 없으면 암호와 해독된 mkey는 아무 소용이 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-bither">비터 사용법</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>스크립트를 다운로드한 후&nbsp;&nbsp;<strong>지갑 파일의 복사본을 다른 폴더에 만듭니다</strong>&nbsp;&nbsp;(쉽게 만들기 위해 추출 스크립트와 동일한 폴더에).&nbsp;Windows의 경우, 시작 메뉴를 클릭한 다음 "실행..."을 클릭하고 다음을 입력하여 일반적으로 지갑 파일이 포함된 폴더를 엽니다:&nbsp;&nbsp;<code>%appdata%\Bither</code>.&nbsp;여기에서 지갑 파일(보통 이름이&nbsp;&nbsp;<code>address.db</code>)을 복사하여 별도의 폴더에 붙여넣을 수 있습니다.&nbsp;다음으로 명령 프롬프트 창을 열고 다음과 같이 입력해야 합니다(다운로드한 스크립트의 위치에 따라 다르고 지갑 파일이 같은 폴더에 있다고 가정).</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-bither-partkey.py address.db
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>다음과 같은 메시지가 나타납니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>Bither partial encrypted private key, salt, and crc in base64:
YnQ6PocfHvWGVbCzlVb9cUtPDjosnuB7RoyspTEzZZAqURlCsLudQaQ4IkIW8YE=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>귀하(또는 다른 사람)가&nbsp; 암호를 검색하기 위해&nbsp;<em>btcrecover를</em>&nbsp;실행할 때 &nbsp;지갑 파일이 필요하지 않고&nbsp;&nbsp;<em>extract-bither-partkey.py</em>&nbsp;의 출력만 필요합니다 .&nbsp;예제를 계속하려면 다음을 수행하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_6" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; YnQ6PocfHvWGVbCzlVb9cUtPDjosnuB7RoyspTEzZZAqURlCsLudQaQ4IkIW8YE=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="bither-technical-details">비더 기술 세부 사항</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-bither-partkey.py&nbsp;&nbsp;&nbsp;스크립트는 의도적으로 짧으며 모든 Python 프로그래머가 쉽게 읽을 수 있어야 합니다&nbsp;<em>.&nbsp;</em>Bither 암호화 개인 키의 길이는 48바이트입니다.&nbsp;여기에는 32바이트의 암호화된 개인 키 데이터와 16바이트의 암호화된 패딩이 포함됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>개인 키의 마지막 절반만 추출되기 때문에 개인 키의 이 절반을 해독할 수 있더라도(비밀번호 검색이 성공한다고 가정) 개인 키를 재구성할 수 없습니다.&nbsp;나머지 16바이트 패딩은 복호화되면 예측 가능하며 이를 통해&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;이를 사용하여 비밀번호를 확인할 수 있습니다.&nbsp;각 암호로 바이트 암호 해독을 시도하고 유효한 패딩 결과가 나오면 올바른 암호를 찾은 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>나머지 지갑 파일에 액세스하지 않고는 암호 해독된 패딩이 자금 손실로 이어질 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-blockchaincom">Blockchain.com 사용</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>첫 번째 단계는 Blockchain.com 지갑 백업 파일을 다운로드하는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>extract-scripts</code>&nbsp;이 패키지의 폴더로 이동하여 다음을 실행&nbsp;해야 합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>python3 download-blockchain-wallet.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>메시지가 표시되면 지갑 ID를 입력한 다음 지갑과 연결된 이메일 계정에서 로그인 요청을 승인합니다.&nbsp;로그인이 승인되면 wallet.aes.json 파일이 PC에 저장됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>다음으로 명령 프롬프트 창을 열고 다음과 같이 입력해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_7" class="wp-block-code"><code>python3 extract-blockchain-main-data.py wallet.aes.json
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>물론 지갑 파일명을 자신의 것으로 바꿔야 합니다.&nbsp;결과적으로 다음과 같은 메시지가 나타납니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_8" class="wp-block-code"><code>Blockchain first 16 encrypted bytes, iv, and iter_count in base64:
Yms6abF6aZYdu5sKpStKA4ihra6GEAeZTumFiIM0YQUkTjcQJwAAj8ekAQ==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>귀하(또는 다른 사람)가&nbsp; 암호를 검색하기 위해&nbsp;<em>btcrecover를</em>&nbsp;실행할 때 &nbsp;지갑 파일이 필요하지 않으며&nbsp;&nbsp;<em>extract-blockchain-main-data.py</em>&nbsp;의 출력만 필요합니다 .&nbsp;예제를 계속하려면 다음을 수행하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_9" class="wp-block-code"><code>btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; Yms6abF6aZYdu5sKpStKA4ihra6GEAeZTumFiIM0YQUkTjcQJwAAj8ekAQ==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="blockchaincom-second-passwords">Blockchain.com 두 번째 비밀번호</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Blockchain.com 지갑의 두 번째 비밀번호 기능을 활성화했고 이 두 번째 비밀번호를 검색해야 하는 경우, 기본 비밀번호가 없으면 먼저 기본 비밀번호를 찾아야 합니다(위 참조).&nbsp;기본 암호가 있으면 지갑 백업 파일(보통 이름이&nbsp;&nbsp;<code>wallet.aes.json</code>)을 가져와서&nbsp; 다른 폴더&nbsp;&nbsp;(쉽게 만들기 위해 추출 스크립트와 동일한 폴더)에&nbsp;<strong>복사본을 만듭니다 .&nbsp;</strong>다음으로 명령 프롬프트 창을 열고 다음과 같이 입력해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_10" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-blockchain-second-hash.py wallet.aes.json
Please enter the Blockchain wallet's main password:
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>추출 스크립트가 첫 번째 암호화 수준을 제거하여 암호화된 데이터의 두 번째 수준에 액세스할 수 있도록 프롬프트가 표시되면 지갑의 기본 비밀번호를 입력해야 합니다.&nbsp;결과적으로 다음과 같은 메시지가 나타납니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_11" class="wp-block-code"><code>Blockchain second password hash, salt, and iter_count in base64:
YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>귀하(또는 다른 사람)가&nbsp; 암호를 검색하기 위해&nbsp;<em>btcrecover를</em>&nbsp;실행할 때 &nbsp;지갑 파일이 필요하지 않으며&nbsp;&nbsp;<em>extract-blockchain-second-hash.py</em>&nbsp;의 출력만 필요합니다 .&nbsp;예제를 계속하려면 다음을 수행하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_12" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; YnM6LeP7peG853HnQlaGswlwpwtqXKwa/1rLyeGzvKNl9HpyjnaeTCZDAaC4LbJcVkxaECcAACwXY6w=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><em>AES 암호 해독 라이브러리가 포함된 전체 btcrecover</em>&nbsp;패키지를 다운로드하거나&nbsp;&nbsp;<em>extract-blockchain-second-hash.py</em>&nbsp;스크립트 &nbsp;를 사용하려면 이미 PyCrypto가 설치되어 있어야 합니다&nbsp;&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="blockchaincom-technical-details">Blockchain.com 기술 세부 정보</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-blockchain-main-data.py&nbsp;&nbsp;&nbsp;스크립트는 의도적으로 짧으며 모든 Python 프로그래머가 쉽게 읽을 수 있어야 합니다&nbsp;<em>.&nbsp;</em>이 스크립트는 Blockchain.com 지갑에서 암호화된 데이터의 처음 32바이트를 추출합니다. 이 중 16바이트는 AES 초기화 벡터이고 나머지 16바이트는 첫 번째 암호화된 AES 블록입니다.&nbsp;그런 다음 이 정보는 쉬운 복사/붙여넣기를 위해 base64 형식으로 변환되고 화면에 인쇄됩니다.&nbsp;<em>하나의 암호화된 블록에는 개인 키 정보가 포함되어 있지 않지만 일단 해독되면 btcrecover</em>&nbsp;&nbsp;에서&nbsp;사용할 수 있는 민감하지 않은 문자열(특히 문자열 "guid", "tx_notes", "address_book" 또는 "double")이 포함됩니다.&nbsp;&nbsp;성공적인 암호 시도를 위해 테스트하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>extract-blockchain-second-hash.py&nbsp;&nbsp;&nbsp;스크립트는 조금 더 길지만 대부분의 Python 프로그래머가 읽고 이해할 수 있을 만큼 충분히 짧아야 합니다&nbsp;<em>.&nbsp;</em><em>Blockchain.com 지갑의 첫 번째 암호화 수준을 해독한 후 btcrecover</em>&nbsp;에서 &nbsp;성공적인 암호 시도를 테스트하는 데&nbsp;사용할 수 있는 암호 해시와 솔트를 추출합니다&nbsp; .&nbsp;암호화된 개인 키는 추출하지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>지갑 파일의 나머지 부분에 액세스하지 않고 이 스크립트만으로 추출한 정보 조각만으로는 암호 추측 및 암호 해독에 성공한 후에도 비트코인 ​​자금이 위험에 처하지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-coinomi">Coinomi 사용</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>참고: 비밀번호로 보호되는 지갑만 지원합니다.&nbsp;"암호 없음", "생체 인식" 또는 "암호 + 생체 인식"을 선택한 경우 휴대폰 키 저장소의 정보도 필요합니다...(검색이 불가능할 수 있음)</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Coinomi의 첫 번째 단계는 실행 중인 플랫폼에 따라 다릅니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Windows 사용자의 경우 단순히 %localappdata%\Coinomi\Coinomi\wallets로 이동하면 지갑 파일을 찾을 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Android 사용자의 경우 Coinomi에서 .wallet 파일에 액세스할 수 있는 루팅된 전화가 필요합니다.&nbsp;(data\data\com.coinomi.wallet\files\wallets 폴더에서 찾을 수 있습니다.) 특정 전화에서 루트 액세스 권한을 얻는 방법은 이 문서의 범위를 벗어나지만 전화를 루팅하는 일부 방법은 공장 초기화를 포함합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>거기에 여러 개의 지갑이 있고 어느 것이 올바른지 확실하지 않은 경우 각 지갑의 이름은 파일 끝에서 일반 텍스트로 찾을 수 있습니다.&nbsp;&nbsp;예를 보려면&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/master/btcrecover/test/test-wallets">./btcrecover/test/test-wallets에서 이 저장소에 포함된 테스트 지갑을 참조하십시오 .)</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>파일이 있으면 BTCRecover와 함께 직접 사용하거나 추출을 생성할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_13" class="wp-block-code"><code>python3 extract-coinomi-privkey.py ../btcrecover/test/test-wallets/coinomi.wallet.android
Coinomi partial first encrypted private key, salt, n, r, p and crc in base64:
Y246uwodSaelErkb7GIYls3xaeX5i5YWtmh814zgsBCx+y8xgjp7Mul0TQBAAAAIAAEASAgdvw==
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-dogechaininfo">Dogechain.info 사용법</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>그런 다음 아래와 같은 명령을 사용하여 다운로드한 지갑 파일에서 추출 스크립트를 만들 수 있습니다.&nbsp;(리포지토리의 일부인 샘플 지갑 파일을 사용함)</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_14" class="wp-block-code"><code>python3 extract-dogechain-privkey.py ../btcrecover\test\test-wallets/dogechain.wallet.aes.json
Dogechain first 16 encrypted bytes, iv, and iter_count in base64:
ZGM6jJzIUd6i9DMEgCFG9JQ1/z4xSamItXAiQnV4AeJ0BwcZznn+169Eb84PFQ3QQ2JGiBMAAGL+4VE=
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-electrum">일렉트럼 용도</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>스크립트를 다운로드한 후&nbsp;&nbsp;<strong>지갑 파일의 복사본을 다른 폴더에 만듭니다</strong>&nbsp;&nbsp;(쉽게 만들기 위해 추출 스크립트와 동일한 폴더에).&nbsp;<code>%appdata%\Electrum\wallets</code>Windows의 경우 시작&nbsp;메뉴를 클릭한 다음 "실행…&nbsp;여기에서 일반적으로 이름이 지정된 지갑 파일을 복사하여&nbsp;&nbsp;<code>default_wallet</code>별도의 폴더에 붙여넣을 수 있습니다.&nbsp;다음으로 명령 프롬프트 창을 열고 다음과 같이 입력해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_15" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-electrum2-partmpk.py default_wallet
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>위의 예에서는 Electrum 2.x 지갑이 있다고 가정합니다.&nbsp;대신 Electrum 1.x 지갑인 경우&nbsp;&nbsp;<em>extract-electrum2-partmpk.py를&nbsp;</em><em>extract-electrum-halfseed.py</em>&nbsp;&nbsp;로&nbsp; 교체합니다&nbsp;.&nbsp;물론 지갑 파일 이름도 자신의 것으로 바꿔야 합니다.&nbsp;다음과 같은 메시지가 표시되어야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_16" class="wp-block-code"><code>First half of encrypted Electrum seed, iv, and crc in base64:
ZWw6kLJxTDF7LxneT7c5DblJ9k9WYwV6YUIUQO+IDiIXzMUZvsCT
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>또는 지갑 세부 정보에 따라 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_17" class="wp-block-code"><code>Electrum2 partial encrypted master private key, iv, and crc in base64:
ZTI69B961mYKYFV7Bg1zRYZ8ZGw4cE+2D8NF3lp6d2XPe8qTdJUz
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>귀하(또는 다른 사람)가&nbsp; 암호를 검색하기 위해&nbsp;<em>btcrecover를</em>&nbsp;실행할 때 &nbsp;지갑 파일이 필요하지 않으며&nbsp;&nbsp;<em>extract-electrum-halfseed.py</em>&nbsp;의 출력만 필요합니다 .&nbsp;예제를 계속하려면 다음을 수행하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_18" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; ZWw6kLJxTDF7LxneT7c5DblJ9k9WYwV6YUIUQO+IDiIXzMUZvsCT
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="electrum-1x-technical-details">일렉트럼 1.x 기술 세부 사항</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-electrum-halfseed.py&nbsp;&nbsp;&nbsp;스크립트는 의도적으로 짧으며 모든 Python 프로그래머가 쉽게 읽을 수 있어야 합니다&nbsp;<em>.&nbsp;</em>Electrum 암호화 시드의 길이는 64바이트입니다.&nbsp;여기에는 16바이트 AES 초기화 벡터와 48바이트의 암호화된 시드 데이터가 포함되며, 마지막 16바이트는 패딩입니다(실제 시드 데이터는 32바이트).&nbsp;스크립트는 16바이트 초기화 벡터와 실제 시드 데이터의 처음 16바이트(시드의 50%)만 추출합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>시드의 절반만 추출되기 때문에 절반의 시드가 해독된 후에도 개인 키를 재구성할 수 없습니다(비밀번호 검색이 성공한다고 가정).&nbsp;해독된 이 16자는 16진수로 인코딩되기 때문에&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;암호를 확인하기 위해 단독으로 사용할 수 있습니다.&nbsp;각 암호로 바이트 암호 해독을 시도하고 결과가 유효한 16자 길이의 16진수 인코딩 문자열이면 올바른 암호를 찾은 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>지갑 파일의 나머지 부분에 액세스할 수 없다면 암호 추측 및 암호 해독에 성공한 후에도 이 16자만으로 비트코인 ​​자금을 위험에 빠뜨릴 가능성은 거의 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="electrum-2x-technical-details">일렉트럼 2.x 기술 세부 사항</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-electrum2-partmpk.py&nbsp;&nbsp;&nbsp;스크립트는 의도적으로 짧으며 모든 Python 프로그래머가 쉽게 읽을 수 있어야 합니다&nbsp;<em>.&nbsp;</em>Electrum 2.x 암호화된 마스터 개인 키(mpk)의 길이는 128바이트입니다.&nbsp;여기에는 16바이트 AES 초기화 벡터와 112바이트의 암호화된 mpk 데이터가 포함되며 마지막 바이트는 패딩(실제 mpk 데이터의 111바이트)입니다.&nbsp;이 111바이트 중 대략 18바이트는 헤더, 다음 44바이트는 체인코드, 나머지 47바이트는 개인 키로 구성됩니다.&nbsp;이 스크립트는 16바이트 초기화 벡터와 mpk 데이터의 처음 16바이트만 추출합니다. 모두 민감하지 않은 헤더 정보입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>암호가 해독되면 이 16자는 항상 "xprv" 문자열로 시작하고 나머지는 base58로 인코딩되며&nbsp;&nbsp;<em>btcrecover</em>&nbsp;&nbsp;는 암호를 확인하는 데 단독으로 사용할 수 있습니다.&nbsp;각 암호로 바이트 암호 해독을 시도하고 예상한 결과가 나오면 올바른 암호를 찾은 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>나머지 지갑 파일에 액세스하지 않고는 해독된 헤더 정보로 인해 자금 손실이 발생할 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-metamask">메타마스크 사용법</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>확장 프로그램에서 모든 볼트 데이터(오래 덮어쓴 지갑 포함)를 추출할 수 있는 Metamask용 추출 스크립트와 신뢰할 수 없는 복구를 위한 추출을 생성할 수 있는 두 가지 추출 스크립트가 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Chrome 기반 브라우저의 경우 브라우저 확장 프로그램의 데이터 폴더를 찾아야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>메타마스크의 경우 %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\nkbihfbeogeaoehlefnkodbefgpgknn\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Binance Wallet Extension의 경우 %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fhbohimaelbohpjbbldcngcnapndodjp\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Ronin Wallet의 경우 %localappdata%\Google\Chrome\User Data\Default\Local Extension Settings\fnjhmkhhmkbjkkabndcnnogagogbneec\</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>확장 데이터의 경로는 다른 Chrome 기반 브라우저(예: Brave)의 경우 약간 다르지만 일반적인 위치와 최종 폴더 이름은 동일합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>그런 다음 아래와 유사한 명령을 사용하여 해당 확장에 대한 모든 볼트 데이터를 볼 수 있습니다(자신의 브라우저 확장 데이터에 대한 경로를 사용하려는 경우 제외).</em></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_19" class="wp-block-code"><code>python3 extract-metamask-vaults.py ../btcrecover/test/test-wallets/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn
===== (Likely) Old Vault Data =====

{"data":"vXOTraxWuDmDrhxZ759NodhTmd4UQkThRG6YLvPt14OdZgnvJo4P5wj+LRupmb+7Vql+fOM5IF33Qb3FQvWro8Ro201M1YOH5zBdSwK6wzYmlFndlwqgOq61HSDUD9Ee1ccUF/iUgqJIngCw9/bRo93kpj11MuVonNOayTFztRc68+/JPCmIe0vqPYShRfJbeI8IBvauJdUxg6VqG0PId0Pw30ZO3f3QXmKFE+ZoibgbO111j7gQ0l7j6KdABeA=","iv":"7hvnbvsoSQmAbWzfvtMkjA==","salt":"13+DUqg893kPM0MiJz3bz2iYGAxPtPisX1JE1+be9IU="}

===== Current Vault Data =====

{"data":"Ny6zeXCgltvFkIWycZU3gYLocIM+gH/2m4fozdKdJxwff2BUHXaxBkaLDuzMs7WtazXJ+3P+XsFFG2W8+7tpNfCv2RCNNHWX9aVEBKeKEwQPUT6MD4rNU2XYykPROAcbdUPHKEVpaAEj+1VlCiMk1m3j7KhIHpt1cI7Qp8rV7lxzCUc5FWAWlc+gxvFTfSXOPJd0k23/F9MgRq0vn2h+UJolmLzpQFvEv2BUuL6CoEbog8Vn2N+ktypbR2pnNMA=","iv":"H82DrVooOndR7fk1SKKGwQ==","salt":"cxp0pRtsgyUBjll6MktU2HySubrtnMaPXAwaBsANA1Y="}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>Firefox의 경우 여기에 설명된 프로세스를 사용하여 메타마스크 저장소를 검색해야 합니다. -the-MetaMask-Vault-Data</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>볼트 데이터가 있으면 텍스트 파일에 넣고 BTCRecover와 함께 직접 사용하거나 추출을 생성할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_20" class="wp-block-code"><code>python3 extract-metamask-privkey.py ../btcrecover/test/test-wallets/metamask.9.8.4_firefox_vault
Metamask first 16 encrypted bytes, iv, and salt in base64:
bXQ6bB5JP1EW0xwBmWZ9vI/iw9IRkorRs9rI6wJCNrd8KUw61ubkQxf9JF9jDv9kZIlxVVkKb7lIwnt7+519MLodzoK0sOw=
</code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 id="usage-for-msigna">mSIGNA 사용법</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>스크립트를 다운로드한 후&nbsp;&nbsp;<strong>지갑 파일의 복사본을 다른 폴더에 만듭니다</strong>&nbsp;&nbsp;(쉽게 만들기 위해 추출 스크립트와 동일한 폴더에).&nbsp;Windows의 경우, 시작 메뉴를 클릭한 다음 "실행..."을 클릭하고 다음을 입력하여 일반적으로 지갑 파일이 포함된 폴더를 엽니다:&nbsp;&nbsp;<code>%homedrive%%homepath%</code>.&nbsp;여기에서 지갑 파일(파일&nbsp;&nbsp;<code>.vault</code>&nbsp;)을 복사하여 별도의 폴더에 붙여넣을 수 있습니다.&nbsp;다음으로 명령 프롬프트 창을 열고 다음과 같이 입력해야 합니다(다운로드한 스크립트의 위치에 따라 다르며 지갑 파일의 이름이 지정되고&nbsp;&nbsp;<code>msigna-wallet.vault</code>&nbsp;동일한 폴더에 있다고 가정).</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_21" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-msigna-partmpk.py msigna-wallet.vault
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>다음과 같은 메시지가 나타납니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_22" class="wp-block-code"><code>mSIGNA partial encrypted master private key, salt, and crc in base64:
bXM6SWd6U+qTKOzQDfz8auBL1/tzu0kap7NMOqctt7U0nA8XOI6j6BCjxCsc7mU=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>귀하(또는 다른 사람)가&nbsp;&nbsp;<em>btcrecover를</em>&nbsp;실행하여 &nbsp;암호를 검색할 때 지갑 파일이 필요하지 않으며&nbsp;&nbsp;<em>extract-msigna-partmpk.py</em>&nbsp;의 출력만 필요합니다 .&nbsp;예제를 계속하려면 다음을 수행하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_23" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bXM6SWd6U+qTKOzQDfz8auBL1/tzu0kap7NMOqctt7U0nA8XOI6j6BCjxCsc7mU=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="msigna-technical-details">mSIGNA 기술 세부 정보</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract-msigna-partmpk.py&nbsp;&nbsp;&nbsp;스크립트는 의도적으로 짧으며 모든 Python 프로그래머가 쉽게 읽을 수 있어야 합니다&nbsp;<em>.&nbsp;</em>mSIGNA 암호화된 마스터 개인 키의 길이는 48바이트입니다.&nbsp;여기에는 32바이트의 암호화된 개인 키 데이터와 16바이트의 암호화된 패딩이 포함됩니다(체인코드는 별도로 저장됨).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>개인 키의 마지막 절반만 추출되기 때문에 이 개인 키의 절반을 해독할 수 있더라도(비밀번호 검색이 성공한다고 가정) 지갑을 재구성할 수 없습니다.&nbsp;나머지 16바이트 패딩은 복호화되면 예측 가능하며 이를 통해&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;이를 사용하여 비밀번호를 확인할 수 있습니다.&nbsp;각 암호로 바이트 암호 해독을 시도하고 유효한 패딩 결과가 나오면 올바른 암호를 찾은 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>나머지 지갑 파일에 액세스하지 않고는 암호 해독된 패딩이 자금 손실로 이어질 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-multibit-classic">MultiBit Classic의 사용법</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong><em>경고:</em></strong>&nbsp;아래 설명된 대로 MultiBit Classic 키 파일에서 스크립트를 &nbsp;사용하면&nbsp;<em>&nbsp;오탐이</em><code>extract-multibit-privkey.py</code>&nbsp;&nbsp;발생할 수 있습니다&nbsp;.&nbsp;잘못된&nbsp;<em>&nbsp;긍정은&nbsp;</em><em>btcrecover가</em>&nbsp;&nbsp;암호를 찾았지만 실수했다고 보고할&nbsp;때 발생합니다&nbsp;<strong>많은</strong>&nbsp;수의 암호(약 100억(10,000,000,000) 이상)를&nbsp;&nbsp;테스트&nbsp;&nbsp;하려는&nbsp;<em>&nbsp;경우</em>&nbsp;.<em></em><em></em><em></em><strong></strong><em></em><code>extract-multibit-privkey.py</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>btcrecover는</em>&nbsp;&nbsp;MultiBit 지갑 파일에서 직접 작동하지 않고 대신 MultiBit 개인 키 백업 파일에서 작동합니다.&nbsp;MultiBit 지갑에 처음 비밀번호를 추가한 후 새 수신 주소를 추가하거나 지갑 비밀번호를 변경할 때마다 MultiBit은 지갑 파일 근처의 디렉토리에 암호화된 개인 키 백업 파일을 생성합니다&nbsp;&nbsp;<code>key-backup</code>&nbsp;.&nbsp;이러한 개인 키 백업 파일은 암호를 시도하는 데 훨씬 더 빠르며(1,000배 이상)&nbsp;&nbsp;<em>btcrecover가</em>&nbsp;&nbsp;이를 사용하는 이유입니다.&nbsp;MultiBit을 처음 설치할 때 생성되는 기본 지갑의 경우 이 디렉토리는 다음 위치에 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_24" class="wp-block-code"><code>%appdata%\MultiBit\multibit-data\key-backup
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>키 파일의 이름은&nbsp;&nbsp;<code>walletname-20140407200743.key</code>.&nbsp;추가 지갑을 만든 경우 해당&nbsp;&nbsp;<code>key-backup</code>&nbsp;디렉토리는 다른 위치에 있으며 위치를 찾는 것은 사용자에게 달려 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>MultiBit 개인 키 백업 파일 찾기에 대한 자세한 내용은&nbsp;&nbsp;<a href="https://www.multibit.org/en/help/v0.5/help_fileDescriptions.html">https://www.multibit.org/en/help/v0.5/help_fileDescriptions.html 을 참조하십시오.</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>올바른 MultiBit 개인 키 백업 파일을 찾으면&nbsp; 다른 폴더&nbsp;&nbsp;(쉽게 만들기 위해 추출 스크립트와 동일한 폴더)에&nbsp;<strong>복사본을 만듭니다 .&nbsp;</strong>Windows의 경우, 시작 메뉴를 클릭한 다음 “실행… :&nbsp;&nbsp;<code>%appdata%\MultiBit\multibit-data\key-backup</code>.&nbsp;여기에서 개인 키 백업 파일을 복사하여 별도의 폴더에 붙여넣을 수 있습니다.&nbsp;다음으로 명령 프롬프트 창을 열고 다음과 같이 입력해야 합니다(다운로드한 스크립트의 위치에 따라, 개인 키 파일의 복사본을 같은 폴더에 만들었다고 가정).</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_25" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-multibit-privkey.py multibit-20140407200743.key
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>물론 개인 키 파일 이름을 자신의 이름으로 바꿔야 합니다.&nbsp;결과적으로 다음과 같은 메시지가 나타납니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_26" class="wp-block-code"><code>MultiBit partial first encrypted private key, salt, and crc in base64:
bWI6sTaHldcBFFj9zlgNpO1szOwy8elpl20OWgj+lA==
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>귀하(또는 다른 사람)가&nbsp; 암호를 검색하기 위해&nbsp;<em>btcrecover를</em>&nbsp;실행할 때 &nbsp;지갑 파일이나 개인 키 파일이 필요하지 않으며&nbsp;&nbsp;<em>extract-multibit-privkey.py</em>&nbsp;의 출력만 필요합니다 .&nbsp;예제를 계속하려면 다음을 수행하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_27" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bWI6sTaHldcBFFj9zlgNpO1szOwy8elpl20OWgj+lA==
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="multibit-classic-technical-details">MultiBit Classic 기술 세부 정보</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong>경고: MultiBit Classic 데이터 추출은 약 1 in 3×10&nbsp;</strong><sup>11</sup>&nbsp;&nbsp;의 위양성 비율을 가지고 있습니다&nbsp;.&nbsp;자세한 내용은 위의 경고를 참조하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>extract-multibit-privkey.py&nbsp;&nbsp;&nbsp;스크립트는 의도적으로 짧으며 모든 Python 프로그래머가 쉽게 읽을 수 있어야 합니다&nbsp;<em>.&nbsp;</em>이 스크립트는 MultiBit 개인 키 백업 파일의 첫 번째 개인 키에서 8바이트의 암호 솔트와 처음 16개의 암호화된 base58 인코딩 문자(52개 중)를 추출합니다.&nbsp;단일 개인 키의 34% 미만이 추출되기 때문에 처음 16바이트가 해독된 후에도 개인 키 자체를 재구성할 수 없습니다(암호 검색이 성공한다고 가정).&nbsp;해독된 이 16자는 base58로 인코딩되기 때문에&nbsp;&nbsp;<em>btcrecover는</em>&nbsp;&nbsp;암호를 확인하기 위해 단독으로 사용할 수 있습니다.&nbsp;각 암호로 바이트 암호 해독을 시도하고 결과가 유효한 16자 길이의 base58 인코딩 개인 키 접두사이면 올바른 암호를 찾은 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>개인 키 백업 파일이나 지갑 파일의 나머지 부분에 액세스할 수 없으면 이 16자만으로도 비밀번호 추측 및 암호 해독에 성공한 후에도 비트코인 ​​자금을 위험에 빠뜨리지 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="usage-for-multibit-hd">MultiBit HD 사용</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>스크립트를 다운로드한 후&nbsp;&nbsp;<strong>mbhd.wallet.aes 파일을 다른 폴더에 복사합니다</strong>&nbsp;&nbsp;(쉽게 하려면&nbsp;&nbsp;<em>extract-multibit-hd-data.py</em>&nbsp;와 동일한 폴더에 복사 ).&nbsp;Windows의 경우 시작 메뉴를 클릭한 다음 "실행..."을 클릭하고 다음을 입력합니다&nbsp;&nbsp;<code>%appdata%\MultiBitHD</code>.&nbsp;여기에서 지갑 폴더를 열고 mbhd.wallet.aes 파일을 복사하여 별도의 폴더에 붙여넣을 수 있습니다.&nbsp;다음으로 명령 프롬프트 창을 열고 다음과 같이 입력해야 합니다(다운로드한 스크립트의 위치에 따라 다르며 동일한 폴더에 mbhd.wallet.aes의 복사본을 만들었다고 가정).</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_28" class="wp-block-code"><code>cd btcrecover-master\extract-scripts
python3 extract-multibit-hd-data.py mbhd.wallet.aes
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>결과적으로 다음과 같은 메시지가 나타납니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_29" class="wp-block-code"><code>MultiBit HD first 16 bytes of encrypted wallet and crc in base64:
bTI6LbH/+ROEa0cQ0inH7V3thbdFJV4=
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>귀하(또는 다른 사람)가&nbsp; 암호를 검색하기 위해&nbsp;<em>btcrecover를</em>&nbsp;실행할 때 &nbsp;지갑 파일이 필요하지 않고&nbsp;&nbsp;<em>extract-multibit-hd-data.py</em>&nbsp;의 출력만 필요합니다 .&nbsp;예제를 계속하려면 다음을 수행하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_30" class="wp-block-code"><code>cd btcrecover-master
python3 btcrecover.py --data-extract --tokenlist tokens.txt
Please enter the data from the extract script
&gt; bTI6LbH/+ROEa0cQ0inH7V3thbdFJV4=
...
Password found: xxxx
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3 id="multibit-hd-technical-details">MultiBit HD 기술 세부 정보</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>extract&nbsp;&nbsp;<em>-multibit-hd-data</em>&nbsp;&nbsp;스크립트는 의도적으로 짧으며 모든 Python 프로그래머가 쉽게 읽을 수 있어야 합니다.&nbsp;MultiBit HD 지갑 파일은 완전히 암호화됩니다.&nbsp;추출 스크립트는 단순히 지갑 파일에서 처음 32바이트를 읽습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 32바이트는 선택적으로(MultiBit HD v0.5.0으로 시작) 16바이트 AES 초기화 벡터로 시작하여 bitcoinj 지갑 파일의 헤더 바이트, 특히 바이트 문자열 "\x0a?org.bitcoin"이 뒤따릅니다.&nbsp;일단 해독되면(여기서 ?는 임의의 바이트일 수 있음).&nbsp;각 암호로 바이트 암호 해독을 시도하고 예상한 결과가 나오면 올바른 암호를 찾은 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>나머지 지갑 파일에 액세스하지 않고는 해독된 헤더 정보로 인해 자금 손실이 발생할 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/17BTCRecoverCryptoGuide" target="_blank" rel="noreferrer noopener">소스 코드</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">텔레그램: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/imTXE4rGqHw" target="_blank" rel="noreferrer noopener">비디오: https://youtu.be/imTXE4rGqHw</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/btc-recover-crypto-guide" target="_blank" rel="noreferrer noopener">출처: https://cryptodeep.ru/btc-recover-crypto-guide</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1320} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/027-1024x576.png" alt="BTC 복구 암호화 가이드" class="wp-image-1320"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
