# 스마트 계약에 대한 공격으로부터 생태계의 전반적인 보안 향상

<!-- wp:embed {"url":"https://www.youtube.com/embed/HVh_cbsgSMg","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/HVh_cbsgSMg
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>선행 실행 AKA 트랜잭션 주문 종속성</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>University of Concordia는 프론트 러닝을 "향후 거래 및 거래에 대한 특권적인 시장 정보에 대한 사전 액세스로부터 기업이 이익을 얻는 행동 과정"으로 간주합니다.&nbsp;시장의 미래 이벤트에 대한 이러한 지식은 착취로 이어질 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>예를 들어, 특정 토큰의 대량 구매가 발생할 것임을 알면 악의적인 행위자가 해당 토큰을 미리 구매하고 과도한 구매 주문으로 인해 가격이 상승하면 토큰을 판매하여 이익을 얻을 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">금융 시장에서는 오랫동안 전면 실행 공격이 문제였으며, 블록체인의 투명한 특성으로 인해 암호화폐 시장에서 문제가 다시 발생하고 있습니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 문제에 대한 해결책은 계약마다 다르기 때문에 보호하기 어려울 수 있습니다.&nbsp;가능한 솔루션에는 트랜잭션을 일괄 처리하고 사전 커밋 체계를 사용하는 것이 포함됩니다. 즉, 사용자가 나중에 세부 정보를 제출할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeep.ru/doc/SoK_Transparent_Dishonesty_Front-Running_Attacks_on_Blockchain.pdf" target="_blank" rel="noreferrer noopener"><strong>PDF: SoK: 투명한 부정직: 블록체인에 대한 전방 공격</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>프런트 러닝</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>모든 트랜잭션은 실행되기 전에 짧은 시간 동안 mempool에서 볼 수 있기 때문에 네트워크 관찰자는 블록에 포함되기 전에 작업을 보고 반응할 수 있습니다.&nbsp;이것이 악용될 수 있는 방법의 예는 구매 주문 트랜잭션을 볼 수 있고 첫 번째 트랜잭션이 포함되기 전에 두 번째 주문이 브로드캐스트되고 실행될 수 있는 분산형 거래소를 사용하는 것입니다.&nbsp;특정 계약 자체로 귀결되기 때문에 이를 방지하는 것은 어렵습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>원래 전통적인 금융 시장을 위해 만들어진 프론트 러닝은 승자의 이익을 위해 혼돈을 주문하는 경주입니다.&nbsp;금융 시장에서 정보의 흐름은 일부 정보를 가장 먼저 알고 반응함으로써 단순히 이익을 얻을 수 있는 중개자를 탄생시켰습니다.&nbsp;이러한 공격은 대부분 주식 시장 거래 및 후이즈 게이트웨이와 같은 초기 도메인 레지스트리 내에서 이루어졌습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>선행 실행(/ˌfrəntˈrəniNG/)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>명사</em>&nbsp;: 선행;</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em>STOCK MARKET</em>&nbsp;고객에게 정보를 제공하기 전에 중개인과 투자 분석가가 제공한 사전 정보를 거래하는 마켓 메이커의 관행입니다.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":3} -->
<h3 id="taxonomy">분류</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://arxiv.org/abs/1902.05164">분류법</a>&nbsp;을 정의하고&nbsp;&nbsp;&nbsp;각 그룹을 다른 그룹과 구별함으로써 문제를 논의하고 각 그룹에 대한 해결책을 찾기가 더 쉬워집니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">다음과 같은 선행 공격 범주를 정의합니다</a>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>배수량</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>삽입</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>억압</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4 id="displacement">배수량</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>첫 번째 유형의 공격인&nbsp;&nbsp;<em>변위 공격</em>&nbsp;에서는 &nbsp;Mallory(적대자)가 자신의 기능을 실행한 후 Alice(사용자)의 기능 호출이 실행되는 것이&nbsp;중요&nbsp;&nbsp;<strong>하지 않습니다 .&nbsp;</strong>Alice는 고아가 되거나 의미 있는 효과 없이 실행될 수 있습니다.&nbsp;변위의 예는 다음과 같습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>Alice는 도메인 이름을 등록하려고 시도하고 Mallory는 먼저 도메인 이름을 등록합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Alice는 현상금을 받기 위해 버그를 제출하려고 시도하고 Mallory는 버그를 훔쳐 먼저 제출합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>경매에서 입찰을 제출하려는 Alice와 그것을 복사하는 Mallory.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><code>gasPrice</code>&nbsp;이 공격은 일반적으로 네트워크 평균보다 높게, 종종 10 이상의 배수로&nbsp;증가시켜 수행됩니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="insertion">삽입</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이러한 유형의 공격의 경우&nbsp;&nbsp;&nbsp;원래 함수 호출이 거래 후에 실행되는 것이 적에게&nbsp;<strong>중요 합니다.&nbsp;</strong>삽입 공격에서 Mallory가 기능을 실행한 후 계약 상태가 변경되고 이 수정된 상태에서 실행하려면 Alice의 원래 기능이 필요합니다.&nbsp;예를 들어 Alice가 블록체인 자산에 대해 최고 가격보다 더 높은 가격으로 구매 주문을 하면 Mallory는 두 개의 트랜잭션을 삽입합니다. 그녀는 최고 가격으로 구매한 다음 동일한 자산을 Alice의 약간 더 높은 구매 가격으로 판매하도록 제안합니다. .&nbsp;그런 다음 Alice의 거래가 실행되면 Mallory는 자산을 보유하지 않고도 가격 차이로 이익을 얻습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>변위 공격과 마찬가지로 이것은 일반적으로 가스 가격 경매에서 Alice의 거래를 능가하여 이루어집니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>거래 주문 의존성</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>트랜잭션 주문 종속성은 스마트 계약의 경쟁 조건과 동일합니다.&nbsp;예를 들어, 한 함수가 보상 비율을 설정하고 인출 함수가 해당 비율을 사용하는 경우;&nbsp;그런 다음 인출 트랜잭션은 결국 인출될 금액에 영향을 미치는 변경 보상 함수 호출에 의해 전면 실행될 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-114">SWC-114</a>&nbsp;참조&nbsp;<a href="https://swcregistry.io/docs/SWC-114"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="suppression">억압</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>Block Stuffing</em>&nbsp;공격으로 알려진 억제 공격에서&nbsp;&nbsp;&nbsp;Mallory는 자신의 기능을 실행한 후 Alice가 자신의 기능을 실행하지 못하도록 지연시키려고 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>"Fomo3d" 게임의 첫 승자와 다른 온체인 핵의 경우가 그러했습니다.&nbsp;공격자는&nbsp; 모든 가스를 소비&nbsp;<code>gasPrice</code>&nbsp;하고&nbsp;&nbsp;<code>gasLimit</code>&nbsp;블록의&nbsp;&nbsp;<code>gasLimit</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>변형</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">이러한 각 공격에는&nbsp;&nbsp;<em>비대칭</em>&nbsp;&nbsp;및&nbsp;&nbsp;<em>대량</em>&nbsp;의 두 가지 변형이 있습니다 .</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>경우에 따라 Alice와 Mallory는 서로 다른 작업을 수행합니다.&nbsp;예를 들어 Alice는 제안을 취소하려고 하고 Mallory는 먼저 제안을 이행하려고 합니다.&nbsp;우리는 이것을&nbsp;&nbsp;<em>비대칭 변위</em>&nbsp;라고 부릅니다 .&nbsp;다른 경우에 Mallory는 대규모 기능 세트를 실행하려고 합니다. 예를 들어 Alice와 다른 사람들은 블록체인에서 회사가 제공하는 제한된 주식 세트를 구매하려고 합니다.&nbsp;우리는 이것을&nbsp;&nbsp;<em>벌크 변위</em>&nbsp;라고 부릅니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="mitigations">완화</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>선행 실행은 이더리움과 같은 퍼블릭 블록체인에서 널리 퍼진 문제입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>가장 좋은 해결 방법은&nbsp;&nbsp;주로 트랜잭션 순서 또는 시간의 중요성을 제거하여&nbsp;<strong>애플리케이션에서 선행 실행의 이점을 제거하는 것입니다.&nbsp;</strong>예를 들어, 시장에서는 일괄 경매를 구현하는 것이 더 나을 것입니다(이는 또한 고주파 거래 문제로부터 보호합니다).&nbsp;또 다른 방법은 사전 커밋 체계를 사용하는 것입니다(“나중에 세부 정보를 제출하겠습니다”).&nbsp;세 번째 옵션은 거래에서 허용 가능한 최대 또는 최소 가격 범위를 지정하여 가격 하락을 제한함으로써 선행 실행 비용을 완화하는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>트랜잭션 순서 지정:</strong><code>gasPrice</code>&nbsp;Go-Ethereum(Geth) 노드는 &nbsp;주소 논스를&nbsp;&nbsp;기반으로 트랜잭션을 정렬합니다&nbsp; .&nbsp;그러나 이로 인해 현재 채굴 중인 블록에 포함되기 위해 네트워크 참여자 간에 가스 경매가 발생합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>기밀성:</strong>&nbsp;&nbsp;또 다른 접근 방식은 트랜잭션의 가시성을 제한하는 것입니다. 이는 "커밋 및 공개" 체계를 사용하여 수행할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>간단한 구현은 첫 번째 트랜잭션에서 데이터의 keccak256 해시를 저장한 다음 데이터를 공개하고 두 번째 트랜잭션에서 해시에 대해 확인하는 것입니다.&nbsp;그러나 거래 자체가 의도와 담보 가치를 유출할 수 있다는 점에 유의하십시오.&nbsp;보다 안전한 향상된 커밋 및 공개 체계가 있지만 작동하려면 더 많은 트랜잭션이 필요합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>블록 가스 제한이 있는 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이더리움 블록체인에서 모든 블록에는 가스 제한이 있습니다.&nbsp;블록 가스 제한의 이점 중 하나는 공격자가 무한 트랜잭션 루프를 생성하는 것을 방지하지만 트랜잭션의 가스 사용량이 이 제한을 초과하면 트랜잭션이 실패합니다.&nbsp;이로 인해 몇 가지 다른 방식으로 DoS 공격이 발생할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><a href="https://github.com/allpaca/smart-contract-attack-vectors/blob/master/attacks/dos-gas-limit.md#unbounded-operations"></a>무제한 작업</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>블록 가스 한도가 문제가 될 수 있는 상황은 여러 주소로 자금을 보내는 경우입니다.&nbsp;악의적인 의도가 없더라도 이것은 쉽게 잘못될 수 있습니다.&nbsp;지불할 사용자 수가 너무 많으면 가스 한도가 최대가 되어 트랜잭션이 성공하지 못할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 상황은 또한 공격으로 이어질 수 있습니다.&nbsp;악의적인 행위자가 상당한 양의 주소를 생성하기로 결정하고 각 주소는 스마트 계약에서 적은 금액의 자금을 지불받는다고 가정합니다.&nbsp;효과적으로 수행되면 거래가 무기한 차단되어 추가 거래가 진행되지 않을 수도 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 문제에 대한 효과적인 해결책은 현재의 푸시 결제 시스템에서 풀 결제 시스템을 사용하는 것입니다.&nbsp;이렇게 하려면 각 지불을 자체 트랜잭션으로 분리하고 수신자가 함수를 호출하도록 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>어떤 이유로든 지정되지 않은 길이의 배열을 반복해야 하는 경우 최소한 잠재적으로 여러 블록을 사용하고 다음 예제와 같이 여러 트랜잭션에서 수행될 수 있다고 예상하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; msg.gas &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3><a href="https://github.com/allpaca/smart-contract-attack-vectors/blob/master/attacks/dos-gas-limit.md#block-stuffing"></a>블록 스터핑</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>어떤 상황에서는 지정되지 않은 길이의 배열을 반복하지 않더라도 블록 가스 제한으로 계약을 공격할 수 있습니다.&nbsp;공격자는 충분히 높은 가스 가격을 사용하여 거래가 처리되기 전에 여러 블록을 채울 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 공격은 매우 높은 가스 가격으로 여러 트랜잭션을 발행하여 수행됩니다.&nbsp;가스 가격이 충분히 높고 트랜잭션이 충분한 가스를 소비하는 경우 전체 블록을 채우고 다른 트랜잭션이 처리되지 않도록 할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이더리움 거래는 발신자가 스팸 공격을 억제하기 위해 가스를 지불해야 하지만 경우에 따라 그러한 공격을 감행하기에 충분한 인센티브가 있을 수 있습니다.&nbsp;예를 들어 도박 Dapp인 Fomo3D에서 블록 스터핑 공격이 사용되었습니다.&nbsp;이 앱에는 카운트다운 타이머가 있었고 사용자가 키를 마지막으로 구매하면 잭팟을 터뜨릴 수 있었습니다. 단, 사용자가 키를 구매할 때마다 타이머가 연장됩니다.&nbsp;공격자는 키를 구입한 다음 다음 13개 블록과 행을 채워 잭팟을 터뜨릴 수 있었습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이러한 공격이 발생하지 않도록 하려면&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">애플리케이션에 시간 기반 작업을 통합하는 것이 안전한지 신중하게 고려하는 것이 중요합니다.</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>서비스 거부</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="dos-with-unexpected-revert">(예기치 않은) 되돌리기가 있는 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>간단한 경매 계약을 고려하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>공격자가 모든 지불을 되돌리는 폴백 기능이 있는 스마트 계약을 사용하여 입찰하면 공격자는 모든 경매에서 이길 수 있습니다.&nbsp;이전 리더를 환불하려고 할 때 환불에 실패하면 되돌립니다.&nbsp;<em>이는 악의적인 입찰자가 자신의 주소로 환불이 항상</em>&nbsp;실패 하도록 하면서 리더가 될 수 있음을 의미합니다&nbsp;&nbsp;&nbsp;.&nbsp;이런 식으로 다른 사람이 함수를 호출하는 것을 방지&nbsp;&nbsp;<code>bid()</code>&nbsp;하고 영원히 리더로 남을 수 있습니다.&nbsp;&nbsp;권장 사항은 앞에서 설명한 대로 대신&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">풀 결제 시스템을</a>&nbsp;설정하는 것입니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또 다른 예는 사용자(예: 크라우드 펀딩 계약의 후원자)에게 비용을 지불하기 위해 계약이 배열을 통해 반복될 수 있는 경우입니다.&nbsp;각 지불이 성공했는지 확인하려는 것이 일반적입니다.&nbsp;그렇지 않다면 되돌려야 합니다.&nbsp;문제는 하나의 호출이 실패하면 전체 지불 시스템을 되돌리므로 루프가 완료되지 않는다는 것입니다.&nbsp;하나의 주소가 오류를 강제하기 때문에 아무도 돈을 받지 못합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>다시 한 번 권장되는 솔루션은&nbsp;&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">푸시 결제보다 풀을 선호하는</a>&nbsp;것입니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-113">SWC-113</a>&nbsp;참조&nbsp;<a href="https://swcregistry.io/docs/SWC-113"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="dos-with-block-gas-limit">블록 가스 제한이 있는 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>각 블록에는 소비할 수 있는 가스의 양과 수행할 수 있는 양의 계산에 대한 상한선이 있습니다.&nbsp;이것이 블록 가스 한도입니다.&nbsp;사용된 가스가 이 한도를 초과하면 트랜잭션이 실패합니다.&nbsp;이로 인해 몇 가지 가능한 서비스 거부 벡터가 발생합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-a-contract-via-unbounded-operations">무제한 작업을 통한 계약의 가스 제한 DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이전 예에서 또 다른 문제를 발견했을 수 있습니다. 한 번에 모든 사람에게 지불하면 블록 가스 한도에 도달할 위험이 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이로 인해 의도적인 공격이 없더라도 문제가 발생할 수 있습니다.&nbsp;그러나 공격자가 필요한 가스의 양을 조작할 수 있다면 특히 나쁩니다.&nbsp;이전 예의 경우 공격자는 여러 주소를 추가할 수 있으며 각 주소는 아주 작은 환불을 받아야 합니다.&nbsp;따라서 각 공격자의 주소를 환불하는 가스 비용은 결국 가스 한도를 초과하여 환불 트랜잭션이 전혀 발생하지 않도록 차단할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것이&nbsp;&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">푸시 지불보다 풀을 선호하는</a>&nbsp;또 다른 이유입니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>알 수 없는 크기의 배열을 반드시 반복해야 하는 경우 잠재적으로 여러 블록을 사용하도록 계획해야 하므로 여러 트랜잭션이 필요합니다.&nbsp;다음 예와 같이 이동한 거리를 추적하고 해당 지점에서 다시 시작할 수 있어야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; gasleft() &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>함수의 다음 반복을 기다리는 동안 다른 트랜잭션이 처리되는 경우 나쁜 일이 발생하지 않도록 해야 합니다&nbsp;&nbsp;<code>payOut()</code>&nbsp;.&nbsp;따라서 꼭 필요한 경우에만 이 패턴을 사용하세요.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-the-network-via-block-stuffing">블록 스터핑을 통한 네트워크의 가스 제한 DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>계약에 무한 루프가 포함되어 있지 않더라도 공격자는 충분히 높은 가스 가격으로 계산 집약적인 트랜잭션을 배치하여 여러 블록에 대해 다른 트랜잭션이 블록체인에 포함되지 않도록 할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이를 위해 공격자는 전체 가스 한도를 소비하는 여러 트랜잭션을 발행할 수 있으며, 다음 블록이 채굴되는 즉시 포함될 수 있을 만큼 충분히 높은 가스 가격이 포함됩니다.&nbsp;어떤 가스 가격도 블록에 포함되는 것을 보장할 수는 없지만 가격이 높을수록 가능성이 높아집니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>공격이 성공하면 다른 트랜잭션은 블록에 포함되지 않습니다.&nbsp;때로 공격자의 목표는 특정 시간 이전에 특정 계약에 대한 트랜잭션을 차단하는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 공격은&nbsp;&nbsp;&nbsp;도박 앱인 Fomo3D에서&nbsp;<a href="https://solmaz.io/2018/10/18/anatomy-block-stuffing/">수행되었습니다 .&nbsp;</a>이 앱은 "키"를 구입한 마지막 주소에 보상하도록 설계되었습니다.&nbsp;키를 구매할 때마다 타이머가 연장되었고 타이머가 0이 되면 게임이 종료되었습니다. 공격자는 키를 구입한 다음 타이머가 트리거되고 지불금이 해제될 때까지 연속으로 13개의 블록을 채웠습니다.&nbsp;공격자가 보낸 트랜잭션은 각 블록에서 790만 가스를 사용했기 때문에 가스 한도는 몇 개의 작은 "전송" 트랜잭션(각각 21,000가스 사용)을 허용했지만 함수에 대한 호출은 허용하지 않았습니다(300,000+ 가스 비용)&nbsp;&nbsp;<code>buyKey()</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>블록 스터핑 공격은 특정 기간 내에 조치가 필요한 모든 계약에 사용할 수 있습니다.&nbsp;그러나 모든 공격과 마찬가지로 예상 보상이 비용을 초과할 때만 수익성이 있습니다.&nbsp;이 공격의 비용은 채워야 하는 블록 수에 정비례합니다.&nbsp;다른 참가자의 행동을 방지하여 큰 보상을 받을 수 있는 경우 귀하의 계약이 그러한 공격의 대상이 될 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2>(예기치 않은) 되돌리기가 있는 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>DoS(서비스 거부) 공격은 사용자에게 자금을 보내려고 할 때 기능에서 발생할 수 있으며 기능은 해당 자금 이체의 성공에 의존합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것은 나쁜 행위자가 만든 스마트 계약으로 자금이 전송되는 경우 문제가 될 수 있습니다. 단순히 모든 지불을 되돌리는 폴백 기능을 만들 수 있기 때문입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>예를 들어:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 예에서 볼 수 있듯이 공격자가 모든 지불을 되돌리는 폴백 기능이 있는 스마트 계약에서 입찰하는 경우 환불이 불가능하므로 아무도 더 높은 입찰을 할 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것은 또한 공격자가 존재하지 않으면 문제가 될 수 있습니다.&nbsp;예를 들어 배열을 반복하여 사용자 배열에 비용을 지불하고 싶을 수 있으며 물론 각 사용자에게 적절한 비용이 지불되었는지 확인하고 싶을 것입니다.&nbsp;여기서 문제는 한 번이라도 결제에 실패하면 그 기능이 되돌려져 아무도 돈을 받지 못한다는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>이 문제에 대한 효과적인 해결책은 현재의 푸시 결제 시스템에서 풀 결제 시스템을 사용하는 것입니다.&nbsp;이렇게 하려면 각 지불을 자체 트랜잭션으로 분리하고 수신자가 함수를 호출하도록 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>contract auction {
    address highestBidder;
    uint highestBid;
    mapping(address =&gt; uint) refunds;

    function bid() payable external {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            refunds&#91;highestBidder] += highestBid; // record the refund that this user can claim
        }

        highestBidder = msg.sender;
        highestBid = msg.value;
    }

    function withdrawRefund() external {
        uint refund = refunds&#91;msg.sender];
        refunds&#91;msg.sender] = 0;
        (bool success, ) = msg.sender.call.value(refund)("");
        require(success);
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1>서비스 거부</h1>
<!-- /wp:heading -->

<!-- wp:heading -->
<h2 id="dos-with-unexpected-revert">(예기치 않은) 되돌리기가 있는 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>간단한 경매 계약을 고려하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// INSECURE
contract Auction {
    address currentLeader;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt; highestBid);

        require(currentLeader.send(highestBid)); // Refund the old leader, if it fails then revert

        currentLeader = msg.sender;
        highestBid = msg.value;
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>공격자가 모든 지불을 되돌리는 폴백 기능이 있는 스마트 계약을 사용하여 입찰하면 공격자는 모든 경매에서 이길 수 있습니다.&nbsp;이전 리더를 환불하려고 할 때 환불에 실패하면 되돌립니다.&nbsp;<em>이는 악의적인 입찰자가 자신의 주소로 환불이 항상</em>&nbsp;실패 하도록 하면서 리더가 될 수 있음을 의미합니다&nbsp;&nbsp;&nbsp;.&nbsp;이런 식으로 다른 사람이 함수를 호출하는 것을 방지&nbsp;&nbsp;<code>bid()</code>&nbsp;하고 영원히 리더로 남을 수 있습니다.&nbsp;&nbsp;권장 사항은 앞에서 설명한 대로 대신&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">풀 결제 시스템을</a>&nbsp;설정하는 것입니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또 다른 예는 사용자(예: 크라우드 펀딩 계약의 후원자)에게 비용을 지불하기 위해 계약이 배열을 통해 반복될 수 있는 경우입니다.&nbsp;각 지불이 성공했는지 확인하려는 것이 일반적입니다.&nbsp;그렇지 않다면 되돌려야 합니다.&nbsp;문제는 하나의 호출이 실패하면 전체 지불 시스템을 되돌리므로 루프가 완료되지 않는다는 것입니다.&nbsp;하나의 주소가 오류를 강제하기 때문에 아무도 돈을 받지 못합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>address&#91;] private refundAddresses;
mapping (address =&gt; uint) public refunds;

// bad
function refundAll() public {
    for(uint x; x &lt; refundAddresses.length; x++) { // arbitrary length iteration based on how many addresses participated
        require(refundAddresses&#91;x].send(refunds&#91;refundAddresses&#91;x]])) // doubly bad, now a single failure on send will hold up all funds
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>다시 한 번 권장되는 솔루션은&nbsp;&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">푸시 결제보다 풀을 선호하는</a>&nbsp;것입니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-113">SWC-113</a>&nbsp;참조&nbsp;<a href="https://swcregistry.io/docs/SWC-113"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="dos-with-block-gas-limit">블록 가스 제한이 있는 DoS</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>각 블록에는 소비할 수 있는 가스의 양과 수행할 수 있는 양의 계산에 대한 상한선이 있습니다.&nbsp;이것이 블록 가스 한도입니다.&nbsp;사용된 가스가 이 한도를 초과하면 트랜잭션이 실패합니다.&nbsp;이로 인해 몇 가지 가능한 서비스 거부 벡터가 발생합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-a-contract-via-unbounded-operations">무제한 작업을 통한 계약의 가스 제한 DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이전 예에서 또 다른 문제를 발견했을 수 있습니다. 한 번에 모든 사람에게 지불하면 블록 가스 한도에 도달할 위험이 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이로 인해 의도적인 공격이 없더라도 문제가 발생할 수 있습니다.&nbsp;그러나 공격자가 필요한 가스의 양을 조작할 수 있다면 특히 나쁩니다.&nbsp;이전 예의 경우 공격자는 여러 주소를 추가할 수 있으며 각 주소는 아주 작은 환불을 받아야 합니다.&nbsp;따라서 각 공격자의 주소를 환불하는 가스 비용은 결국 가스 한도를 초과하여 환불 트랜잭션이 전혀 발생하지 않도록 차단할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이것이&nbsp;&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/development-recommendations/general/external-calls/">푸시 지불보다 풀을 선호하는</a>&nbsp;또 다른 이유입니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>알 수 없는 크기의 배열을 반드시 반복해야 하는 경우 잠재적으로 여러 블록을 사용하도록 계획해야 하므로 여러 트랜잭션이 필요합니다.&nbsp;다음 예와 같이 이동한 거리를 추적하고 해당 지점에서 다시 시작할 수 있어야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>struct Payee {
    address addr;
    uint256 value;
}

Payee&#91;] payees;
uint256 nextPayeeIndex;

function payOut() {
    uint256 i = nextPayeeIndex;
    while (i &lt; payees.length &amp;&amp; gasleft() &gt; 200000) {
      payees&#91;i].addr.send(payees&#91;i].value);
      i++;
    }
    nextPayeeIndex = i;
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>함수의 다음 반복을 기다리는 동안 다른 트랜잭션이 처리되는 경우 나쁜 일이 발생하지 않도록 해야 합니다&nbsp;&nbsp;<code>payOut()</code>&nbsp;.&nbsp;따라서 꼭 필요한 경우에만 이 패턴을 사용하세요.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="gas-limit-dos-on-the-network-via-block-stuffing">블록 스터핑을 통한 네트워크의 가스 제한 DoS</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>계약에 무한 루프가 포함되어 있지 않더라도 공격자는 충분히 높은 가스 가격으로 계산 집약적인 트랜잭션을 배치하여 여러 블록에 대해 다른 트랜잭션이 블록체인에 포함되지 않도록 할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이를 위해 공격자는 전체 가스 한도를 소비하는 여러 트랜잭션을 발행할 수 있으며, 다음 블록이 채굴되는 즉시 포함될 수 있을 만큼 충분히 높은 가스 가격이 포함됩니다.&nbsp;어떤 가스 가격도 블록에 포함되는 것을 보장할 수는 없지만 가격이 높을수록 가능성이 높아집니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>공격이 성공하면 다른 트랜잭션은 블록에 포함되지 않습니다.&nbsp;때로 공격자의 목표는 특정 시간 이전에 특정 계약에 대한 트랜잭션을 차단하는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 공격은&nbsp;&nbsp;&nbsp;도박 앱인 Fomo3D에서&nbsp;<a href="https://solmaz.io/2018/10/18/anatomy-block-stuffing/">수행되었습니다 .&nbsp;</a>이 앱은 "키"를 구입한 마지막 주소에 보상하도록 설계되었습니다.&nbsp;키를 구매할 때마다 타이머가 연장되었고 타이머가 0이 되면 게임이 종료되었습니다. 공격자는 키를 구입한 다음 타이머가 트리거되고 지불금이 해제될 때까지 연속으로 13개의 블록을 채웠습니다.&nbsp;공격자가 보낸 트랜잭션은 각 블록에서 790만 가스를 사용했기 때문에 가스 한도는 몇 개의 작은 "전송" 트랜잭션(각각 21,000가스 사용)을 허용했지만 함수에 대한 호출은 허용하지 않았습니다(300,000+ 가스 비용)&nbsp;&nbsp;<code>buyKey()</code>&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>블록 스터핑 공격은 특정 기간 내에 조치가 필요한 모든 계약에 사용할 수 있습니다.&nbsp;그러나 모든 공격과 마찬가지로 예상 보상이 비용을 초과할 때만 수익성이 있습니다.&nbsp;이 공격의 비용은 채워야 하는 블록 수에 정비례합니다.&nbsp;다른 참가자의 행동을 방지하여 큰 보상을 받을 수 있는 경우 귀하의 계약이 그러한 공격의 대상이 될 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":1} -->
<h1>외부 통화</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":4} -->
<h4 id="use-caution-when-making-external-calls">외부 전화를 걸 때 주의하세요</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>신뢰할 수 없는 계약을 호출하면 여러 가지 예기치 않은 위험이나 오류가 발생할 수 있습니다.&nbsp;외부 호출은 해당 계약&nbsp;&nbsp;<em>또는</em>&nbsp;&nbsp;그것이 의존하는 다른 계약에서 악성 코드를 실행할 수 있습니다.&nbsp;따라서 모든 외부 호출은 잠재적인 보안 위험으로 취급되어야 합니다.&nbsp;외부 통화를 제거하는 것이 불가능하거나 바람직하지 않은 경우 이 섹션의 나머지 부분에 있는 권장 사항을 사용하여 위험을 최소화하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="mark-untrusted-contracts">신뢰할 수 없는 계약 표시</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>외부 계약과 상호 작용할 때 상호 작용이 잠재적으로 안전하지 않다는 것을 분명히 하는 방식으로 변수, 메서드 및 계약 인터페이스의 이름을 지정하십시오.&nbsp;이는 외부 계약을 호출하는 자체 기능에 적용됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_1" class="wp-block-code"><code>// bad
Bank.withdraw(100); // Unclear whether trusted or untrusted

function makeWithdrawal(uint amount) { // Isn't clear that this function is potentially unsafe
    Bank.withdraw(amount);
}

// good
UntrustedBank.withdraw(100); // untrusted external call
TrustedBank.withdraw(100); // external but trusted bank contract maintained by XYZ Corp

function makeUntrustedWithdrawal(uint amount) {
    UntrustedBank.withdraw(amount);
}
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="avoid-state-changes-after-external-calls">외부 호출 후 상태 변경 방지</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>원시 호출</em>&nbsp;&nbsp;( 형식&nbsp;&nbsp;<code>someAddress.call()</code>)&nbsp; 을&nbsp;사용하든&nbsp;&nbsp;<em>계약 호출</em>&nbsp;&nbsp;( 형식&nbsp;&nbsp;<code>ExternalContract.someMethod()</code>)을 사용하든 악성 코드가 실행될 수 있다고 가정합니다.&nbsp;악성 코드가 아니더라도&nbsp;&nbsp;<em>호출</em><code>ExternalContract</code>&nbsp;하는 &nbsp;모든 계약에 의해 악성 코드가 실행될 수 있습니다&nbsp;&nbsp;&nbsp;.<em></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>한 가지 특별한 위험은 악성 코드가 제어 흐름을 하이재킹하여 재진입으로 인한 취약성을 초래할 수 있다는 것입니다.&nbsp;(&nbsp;&nbsp;&nbsp;이 문제에 대한 더 자세한 논의는&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/attacks/reentrancy/">재진입을 참조하십시오).</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>신뢰할 수 없는 외부 계약을 호출하는 경우&nbsp;&nbsp;<em>호출 후 상태 변경을 피하십시오</em>&nbsp;.&nbsp;이 패턴은 때때로&nbsp;&nbsp;<a href="http://solidity.readthedocs.io/en/develop/security-considerations.html?highlight=check%20effects#use-the-checks-effects-interactions-pattern">checks-effects-interactions 패턴</a>&nbsp;이라고도 합니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-107">SWC-107</a>&nbsp;참조&nbsp;<a href="https://swcregistry.io/docs/SWC-107"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="dont-use-transfer-or-send"><code>transfer()</code>&nbsp;또는 를&nbsp;&nbsp;사용하지 마십시오&nbsp;&nbsp;<code>send()</code>.</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>.transfer()</code><code>.send()</code>&nbsp;수신자에게 정확히 2,300 가스를 전달합니다&nbsp;&nbsp;.&nbsp;이 하드코딩된 가스 지원금의 목표는&nbsp;&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/attacks/reentrancy/">재진입 취약점을</a>&nbsp;방지하는 것이었지만 이는 가스 비용이 일정하다는 가정 하에서만 의미가 있습니다.&nbsp;최근&nbsp;&nbsp;<a href="https://eips.ethereum.org/EIPS/eip-1884">EIP 1884가</a>&nbsp;&nbsp;이스탄불 하드포크에 포함되었습니다.&nbsp;EIP 1884에 포함된 변경 사항 중 하나는 작업의 가스 비용이 증가하여&nbsp;&nbsp;<code>SLOAD</code>&nbsp;계약의 폴백 기능에 2300 가스 이상의 비용이 발생한다는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>.transfer()</code>&nbsp;사용을 중지 하고&nbsp;&nbsp;<code>.send()</code>&nbsp;대신 사용하는&nbsp;&nbsp;것이 좋습니다&nbsp;&nbsp;<code>.call()</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_2" class="wp-block-code"><code>// bad
contract Vulnerable {
    function withdraw(uint256 amount) external {
        // This forwards 2300 gas, which may not be enough if the recipient
        // is a contract and gas costs change.
        msg.sender.transfer(amount);
    }
}

// good
contract Fixed {
    function withdraw(uint256 amount) external {
        // This forwards all available gas. Be sure to check the return value!
        (bool success, ) = msg.sender.call.value(amount)("");
        require(success, "Transfer failed.");
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p>재진입 공격을 완화하는 데&nbsp;&nbsp;<code>.call()</code>&nbsp;아무런 도움이 되지 않으므로 다른 예방 조치를 취해야 합니다.&nbsp;<a href="https://solidity.readthedocs.io/en/develop/security-considerations.html?highlight=check%20effects#use-the-checks-effects-interactions-pattern">재진입 공격을 방지하려면 checks-effects-interactions 패턴을</a>&nbsp;사용하는 것이 좋습니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="handle-errors-in-external-calls">외부 호출 오류 처리</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><code>address.call()</code>Solidity는 원시 주소( ,&nbsp;&nbsp;<code>address.callcode()</code>,&nbsp;&nbsp;<code>address.delegatecall()</code>및 )&nbsp;&nbsp;에서 작동하는 저수준 호출 방법을 제공합니다&nbsp;&nbsp;<code>address.send()</code>.&nbsp;이러한 하위 수준 메서드는 예외를 throw하지 않지만&nbsp;&nbsp;<code>false</code>&nbsp;호출에서 예외가 발생하면 반환됩니다.&nbsp;반면에&nbsp;&nbsp;<em>계약 호출</em>&nbsp;&nbsp;(예:&nbsp;&nbsp;<code>ExternalContract.doSomething()</code>)은 자동으로 throw를 전파합니다(예를 들어&nbsp;&nbsp;<code>ExternalContract.doSomething()</code>&nbsp;will도&nbsp; throws&nbsp;<code>throw</code>&nbsp;인 경우&nbsp;&nbsp;<code>doSomething()</code>&nbsp;).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>하위 수준의 호출 방법을 사용하기로 선택한 경우 반환 값을 확인하여 호출이 실패할 가능성을 처리해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_3" class="wp-block-code"><code>// bad
someAddress.send(55);
someAddress.call.value(55)(""); // this is doubly dangerous, as it will forward all remaining gas and doesn't check for result
someAddress.call.value(100)(bytes4(sha3("deposit()"))); // if deposit throws an exception, the raw call() will only return false and transaction will NOT be reverted

// good
(bool success, ) = someAddress.call.value(55)("");
if(!success) {
    // handle failure code
}

ExternalContract(someAddress).deposit.value(100)();
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-104">SWC-104</a>&nbsp;참조&nbsp;<a href="https://swcregistry.io/docs/SWC-104"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="favor-pull-over-push-for-external-calls">&nbsp;외부 통화에 대해&nbsp;<em>풀</em>&nbsp;&nbsp;보다&nbsp;&nbsp;<em>푸시</em>&nbsp;선호&nbsp;</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>외부 호출은 실수로 또는 의도적으로 실패할 수 있습니다.&nbsp;이러한 실패로 인한 피해를 최소화하려면 각 외부 호출을 호출 수신자가 시작할 수 있는 자체 트랜잭션으로 격리하는 것이 좋습니다.&nbsp;이는 특히 사용자가 자금을 자동으로 푸시하는 것보다 자금을 인출하도록 하는 것이 더 나은 결제와 관련이 있습니다.&nbsp;<a href="https://consensys.github.io/smart-contract-best-practices/attacks/denial-of-service/">(이것은 또한 가스 한도 문제</a>&nbsp;의 가능성을 줄입니다&nbsp;&nbsp;.) 단일 트랜잭션에서 여러 이더 전송을 결합하지 마십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_4" class="wp-block-code"><code>// bad
contract auction {
    address highestBidder;
    uint highestBid;

    function bid() payable {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            (bool success, ) = highestBidder.call.value(highestBid)("");
            require(success); // if this call consistently fails, no one else can bid
        }

       highestBidder = msg.sender;
       highestBid = msg.value;
    }
}

// good
contract auction {
    address highestBidder;
    uint highestBid;
    mapping(address =&gt; uint) refunds;

    function bid() payable external {
        require(msg.value &gt;= highestBid);

        if (highestBidder != address(0)) {
            refunds&#91;highestBidder] += highestBid; // record the refund that this user can claim
        }

        highestBidder = msg.sender;
        highestBid = msg.value;
    }

    function withdrawRefund() external {
        uint refund = refunds&#91;msg.sender];
        refunds&#91;msg.sender] = 0;
        (bool success, ) = msg.sender.call.value(refund)("");
        require(success);
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><a href="https://swcregistry.io/docs/SWC-128">SWC-128</a>&nbsp;참조&nbsp;<a href="https://swcregistry.io/docs/SWC-128"></a></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading {"level":4} -->
<h4 id="dont-delegatecall-to-untrusted-code">신뢰할 수 없는 코드에 delegatecall을 사용하지 마십시오.</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이&nbsp;&nbsp;<code>delegatecall</code>&nbsp;함수는 호출자 계약에 속한 것처럼 다른 계약에서 함수를 호출하는 데 사용됩니다.&nbsp;따라서 호출 수신자는 호출 주소의 상태를 변경할 수 있습니다.&nbsp;안전하지 않을 수 있습니다.&nbsp;아래 예는 사용이 어떻게&nbsp;&nbsp;<code>delegatecall</code>&nbsp;계약의 파기 및 잔액 손실로 이어질 수 있는지 보여줍니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre id="__code_5" class="wp-block-code"><code>contract Destructor
{
    function doWork() external
    {
        selfdestruct(0);
    }
}

contract Worker
{
    function doWork(address _internalWorker) public
    {
        // unsafe
        _internalWorker.delegatecall(bytes4(keccak256("doWork()")));
    }
}
</code></pre>
<!-- /wp:code -->

<!-- wp:paragraph -->
<p><code>Worker.doWork()</code>&nbsp;배포된 컨트랙트의 주소를&nbsp;&nbsp;<code>Destructor</code>&nbsp;인수로&nbsp; 사용하여 를 호출&nbsp;하면&nbsp;&nbsp;<code>Worker</code>&nbsp;컨트랙트는 자폭합니다.&nbsp;신뢰할 수 있는 계약에만 실행을 위임하고 사용자 제공 주소에는 절대 위임하지 마십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>Front-running은 Ethereum DApps에서 널리 퍼진 문제입니다.&nbsp;DApp 개발자는 선행 실행을 염두에 두고 DApp을 설계할 마음가짐이 반드시 있는 것은 아닙니다.&nbsp;이것은 주제를 제시하고 이러한 유형의 공격에 대한 인식을 높이려는 시도입니다.&nbsp;이러한 공격을 완화하기 위해 일부 DApp 수준 애플리케이션 로직을 구축할 수 있지만, 다양한 DApp 범주에 걸친 편재성은 블록체인 수준의 완화가 더 효과적일 수 있음을 시사합니다.&nbsp;우리는 이것을 중요한 연구 분야로 강조합니다.&nbsp;우리는 기업이 다가오는 거래 및 거래에 대한 특권적인 시장 정보에 대한 사전 액세스로부터 이익을 얻는 조치 과정으로 선행 실행을 고려합니다.&nbsp;선행매매는 1970년대 이후 금융상품 시장의 쟁점이 되었습니다.&nbsp;블록체인 기술의 출현으로 프론트 러닝은 우리가 여기에서 탐구하는 새로운 형태로 다시 등장했습니다.&nbsp;블록체인의 탈중앙화되고 투명한 특성에 의해 유발됩니다.&nbsp;이 백서에서 우리는 이더리움 블록체인에 배포된 상위 25개의 가장 활동적인 분산 응용 프로그램(DApps)에 걸쳐 흩어져 있는 지식 체계와 선행 실행 사례를 사용합니다.&nbsp;또한 Status.im의 ICO(Initial Coin Offering)에 대한 자세한 분석을 수행하고 선행 토큰 구매를 나타내는 비정상적인 채굴자의 행동에 대한 증거를 보여줍니다.&nbsp;마지막으로 제안된 솔루션을 유용한 범주로 매핑합니다.&nbsp;im ICO(Initial Coin Offering) 및 선행 토큰 구매를 나타내는 비정상적인 채굴자의 행동에 대한 증거를 보여줍니다.&nbsp;마지막으로 제안된 솔루션을 유용한 범주로 매핑합니다.&nbsp;im ICO(Initial Coin Offering) 및 선행 토큰 구매를 나타내는 비정상적인 채굴자의 행동에 대한 증거를 보여줍니다.&nbsp;마지막으로 제안된 솔루션을 유용한 범주로 매핑합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Improving-Overall-Security" target="_blank" rel="noreferrer noopener">GitHub</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">텔레그램: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/HVh_cbsgSMg" target="_blank" rel="noreferrer noopener"><strong>비디오: https://youtu.be/HVh_cbsgSMg</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeeptech.ru/improving-overall-security" target="_blank" rel="noreferrer noopener">출처: https://cryptodeeptech.ru/improving-overall-security</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1999} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2023/03/035-1-1024x576.png" alt="스마트 계약에 대한 공격으로부터 생태계의 전반적인 보안 향상" class="wp-image-1999"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeeptech.ru/category/cryptanalysis/">암호해독</a></p>
<!-- /wp:paragraph -->
