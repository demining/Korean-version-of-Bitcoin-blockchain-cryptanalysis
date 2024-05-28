# 콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다.

<!-- wp:embed {"url":"https://www.youtube.com/embed/NrQ3oNxlrlU","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/NrQ3oNxlrlU
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>지난 기사:&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">"스마트 계약에 대한 블록체인 공격 벡터 및 취약성" 에서 우리는 블록체인에 대한 알려진 모든 공격&nbsp;</a><a href="https://cryptodeeptech.ru/cold-and-hot-wallets" target="_blank" rel="noreferrer noopener">을</a>&nbsp;검토했습니다.&nbsp;<a href="https://cryptodeeptech.ru/cold-and-hot-wallets" target="_blank" rel="noreferrer noopener">지갑</a>&nbsp;.&nbsp;블록체인은 분산 원장으로 구성된 기본 기술 계층이며 합의 알고리즘에 참여하는 분산 노드가 많기 때문에 매우 안전한 데이터 구조입니다.&nbsp;블록체인을 해킹하기 위해서는 해커들이 수많은 탈중앙화 노드의 취약점을 악용해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>블록체인의 기본 보안 가정은 블록체인의 상태를 변경하기 위해 많은 노드를 해킹하는 것이 불가능하다는 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2><strong>블록체인 기술이 그렇게 안전하다면 어떻게 해킹당할 수 있을까요?</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>기술의 Achilles Heal은 클라이언트를 위해 많은 양의 암호 자산(돈)을 관리하는 기관 사용자의 중앙 집중식 특성이며 돈과 해커 사이에 있는 유일한 것은 개인 키&nbsp;&nbsp;<em>입니다</em>&nbsp;.&nbsp;개인 키는 기존 수표에 서명하는 데 수동 서명을 사용할 수 있는 것과 같은 방식으로 블록체인 트랜잭션에 서명하는 데 사용해야 합니다.&nbsp;누군가가 기관의 개인 키를 훔치면 대신 거래를 생성하고 돈을 훔칠 수 있습니다.&nbsp;은행 시스템과 달리 해킹된 거래가 생성되면 되돌릴 방법이 없습니다. 돈은 말 그대로 도난당합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>개인 키를 저장하고 보호하는 것이 왜 중요합니까?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>개인 키를 보유한 사람은 해당 키와 연결된 자산을 완전히 제어할 수 있습니다.&nbsp;블록체인 트랜잭션은 즉각적이고 취소할 수 없기 때문에 사용자는 개인 키를 비밀로 유지하는 것을 목표로 합니다.&nbsp;개인 키는 한 번만 생성되므로 개인 키를 잘못 배치하면 해당 주소와 관련된 모든 암호화 자산이 효과적으로 쓸모 없게 됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>최적의 양육권 시나리오는 아직 정의되지 않았지만 개인 키의 통제가 가장 중요한 관심사라는 것은 의심의 여지가 없습니다.&nbsp;사실 개인 키는 본질적으로 실제 자산입니다.&nbsp;본질적인 특성과 힘은 예외 없이 진정으로 보호할 방법이 없음을 의미합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>콜드 월렛</strong>&nbsp;&nbsp;"기관 관리인의 금고"는 초기에 비트코인 ​​또는 기타 암호화폐를 저장하는 하드웨어 장치로, 인터넷에서 격리된 장치입니다.&nbsp;이론적으로 콜드 월렛 솔루션은 암호화폐를 보관하는 가장 안전한 방법으로 보고되고 있습니다.&nbsp;<a href="https://cryptodeeptech.ru/cold-and-hot-wallets/#/news-room/what-is-asset-management/">일부 암호화폐 사용자는 디지털 자산을</a>&nbsp;물리적 "지갑"에 보관하는 것을 선호하며&nbsp;&nbsp;&nbsp;대부분 USB 스틱처럼 보이는 장치입니다.&nbsp;컴퓨터에 직접 연결해야만 액세스할 수 있으며 사용자가 암호화폐 자금에 액세스하고 이동하려면 인터넷 연결이 필요합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1804} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-vs-cold-wallet-1-1024x916.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1804"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Trezor, Ledger Nano S와 같은 상업적 용도로 인기 있는 몇 가지 콜드 월렛이 있으며 기업 및 기관 투자자를 위해 일부 다른 장치는 다음을 조합하여 사용합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>USB</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>이더넷</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>SD 카드</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>외부 썸 드라이브</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>HSM이 있는 전용 에어갭 머신</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>위의 하드웨어와 관련된 문제는 사용성이며 암호화 자산에 액세스하려면 콜드 월렛을 컴퓨터에 연결해야 하므로 인터넷에 노출됩니다.&nbsp;이렇게 하면 인터넷 연결을 통해 콜드 월렛 시스템이 손상되어&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">잠재적인 공격 벡터</a>&nbsp;와 잠재적인 사이버 절도에 노출됩니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>콜드 월렛 스토리지를 사용하는 것은 특히 대량의 비트코인 ​​및 기타 암호화 자산을 처리할 때 필요한 보안 예방 조치입니다.&nbsp;예를 들어, 암호화폐 거래소 또는 암호화폐 펀드 관리인은 일반적으로 즉각적인 인출을 제공하며 수십만 개의 비트코인 ​​및 기타 암호화폐 자산을 책임질 수 있습니다.&nbsp;해커가 보안 침해 시 전체 준비금을 훔칠 수 있는 가능성을 최소화하기 위해 금융 서비스 운영자는 표준 프로토콜을 따라 대부분의 준비금을&nbsp;&nbsp;<em>콜드 스토리지</em>&nbsp;에 보관 하고 매일 사용할 수 있는 자산의 적은 비율을 보유합니다. 무역 활동.&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>기본적으로 그들은 대부분의 디지털 자산의 개인 키를 서버나 연결된 다른 컴퓨터에 저장하지 않습니다.&nbsp;서버에 보관되는 유일한 금액은 예상되는 고객 인출을 충당하는 데 필요한 최소 금액입니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>디지털 자산의 개인 키를 보호하는 데 사용되는 방법:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>강력한 비밀번호로 지갑을 보호하는 데이터 암호화</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>컴퓨터 충돌 또는 사기에 대비한 디지털 지갑 백업</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>콜드 월렛은 어떤 시점에서 자금을 보내야 하고 그렇게 함으로써 양방향 통신에 의존하고 인터넷에 연결되기 때문에 진정으로 안전하지 않습니다.&nbsp;이것은 그들이 손상될 수 있고 악의적인 데이터에 감염될 수 있고&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">공격에 극도로 취약할</a>&nbsp;때입니다 .&nbsp;따라서 모든 콜드 월렛은 핫 월렛이 되어 기관 관리인의 전체 보안 이론을 무효화합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>오늘날 핫월렛은</strong>&nbsp;&nbsp;자금에 쉽게 접근하고 자동 거래를 처리할 수 있기 때문에 중요한 역할을 하지만 핫월렛의 개인 키는 항상 인터넷에 연결되어 있어야 하는 방식으로 저장됩니다.&nbsp;개인 키를 저장하는 방법에 대해 다른 접근 방식을 취하는 다양한 유형의 핫 월렛이 있습니다.&nbsp;수학적 관점에서 일부는 서로 다른 참여자 간에 개인 키를 복제하고 다른 일부는 참여자 간에 개인 키를 나눕니다.&nbsp;즉, 오늘날 핫 월렛은 개인 키를 배포하여 보안 위험을 해결합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>핫 월렛 참가자는 개인 키에 대한 통제권을 유지하므로 핫 월렛의 암호화폐 자산은 보유자의 통제하에 있습니다.&nbsp;그러나 컴퓨터나 스마트폰에 대한 액세스 권한을 얻은 악의적인 사람이나 그룹이 이론적으로 개인 키에 액세스하여 지갑을 비울 수도 있기 때문에 자산은 여전히 ​​해킹에 취약합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Hot Wallet의 주요 장점은 자동 및 빠른 액세스 트랜잭션에 사용할 수 있다는 것입니다.&nbsp;예를 들어 암호화폐 자산으로 실제로 구매하려는 개인은 핫 월렛을 사용하도록 선택할 수 있습니다. 예를 들어 해당 월렛의 보유 자산은 인터넷을 통해 양도할 수 있고 일반적으로 암호화 자산의 수는 충분히 높은 가치를 지닙니다. 해커가 훔치기 위해 투자하는 시간과 돈이 아깝습니다.&nbsp;반면에 핫 월렛은 인터넷에 지속적으로 액세스할 수 있기 때문에 보안 침해에 확실히 취약합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>다양한 유형의 핫 월렛은 모두 인터넷에 연결된 애플리케이션에 개인 키를 저장합니다.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>기본 핫월렛 – 개인키를 인터넷에서 직접 연결&nbsp;</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Multisig Native Wallet – 개인 키 복제 – 액세스 권한을 얻기 위해 두 명의 참여자만 타협하면 됩니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다자간 계산(MPC) – 2-5명의 참여자 사이에 개인 키 배포</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>2-3명의 사람이나 단체가 특정 거래를 확인해야 하는 경우에도 Multisig 방법을 살펴보면 해커 그룹은 기관 대상에 수백만 달러를 지출할 것이며 보안을 손상시키기 위해&nbsp;3명 중 2명에 대한&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">공격 벡터만 필요합니다 .&nbsp;</a>해커 그룹은 도난당한 암호화 자산에서 수억 달러를 얻을 수 있기 때문에 이를 기꺼이 수행합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>MPC 방법론도 다양한 공격 벡터에 취약합니다.&nbsp;MPC 접근 방식을 사용하면 여러 비신뢰 컴퓨터가 각각 더 큰 데이터 세트의 고유한 조각에 대해 계산을 수행하여 한 노드가 다른 노드의 세부 정보를 알지 않고도 원하는 공통 결과를 집합적으로 생성할 수 있습니다.&nbsp;트랜잭션을 실행하는 개인 키는 집합적으로 생성된 값입니다.&nbsp;MPC 지지자들은 실제 키를 담당하는 단일 컴퓨터가 없다고 주장합니다.&nbsp;<a href="https://cryptodeeptech.ru/cold-and-hot-wallets/#/product/">MPC 기반 지갑은</a>&nbsp;&nbsp;시장의 모든 하드웨어 또는&nbsp;<a href="https://en.bitcoin.it/wiki/Multisignature">&nbsp;다중 서명 지갑</a>&nbsp;&nbsp;에 대해 더 나은 솔루션이라고 합니다 .&nbsp;그들은 더 안전하고 완전히 오프 체인이며 더 높은 유연성을 제공하고 일반적으로 원장에 구애받지 않는 것으로 수학적으로 입증되었습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>안타깝게도 여러 장치에 조각이 있더라도 정교한 해커가 키를 추적하고 재구성할 수 있을 만큼 충분히 오랫동안 시스템 클러스터 내에 머무를 수 있기 때문에 여전히 완전히 안전한 솔루션은 아닙니다.&nbsp;한 대의 직원 컴퓨터나 서버를 손상시키는 경우 네트워크에서 측면으로 이동하고 서명 방법의 일부인 다른 장치를 손상시킬 수 있습니다.&nbsp;따라서 해커 그룹이 이 방법의 취약점을 찾을 수 있을 만큼 정교하고 수십억 달러를 훔치기 위해 수백만 달러를 지출할 의향이 있기 때문에 이 역시 거짓으로 판명될 수 있습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>위의 솔루션을 사용하면 악의적인 직원이 현장, 냉장 보관 시설 또는 회사에서 전적으로 관리하는 하드웨어 장치에서 키를 훔치는 것을 기본적으로 방지할 수 있습니다.&nbsp;공격자나 악의적인 직원이 단일 네트워크에 들어가 불법 거래를 승인하고 서명하는 데 필요한 모든 암호화 정보를 수집하는 것을 제한하려는 mpc 지갑 제공업체가 있지만 이 솔루션도 100% 안전하지 않고 단순합니다.&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">공격 벡터를 완화하는</a>&nbsp;것은 수십억이 위태로운 상황에서 선택 사항이 아닙니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2><strong>업계가 관심을 가져야 하는 이유는 무엇입니까?&nbsp;</strong></h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>이 기사를 작성하는 시점에서 암호 화폐의 총 시가 총액은 2,180억 달러를 초과했으며 현재 존재 10년차입니다.&nbsp;지난 10년 동안 주목할 만한 해킹이 많이 있었습니다.&nbsp;많은 양의 암호화 자산을 관리하는 모든 기관은 투자자에게 가장 강력한 보안 옵션이 기업 전체에 배포되도록 할 책임이 있습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>또한 해킹은 다양한 사이버 피해로 이어집니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>자산 절도 - 돌이킬 수 없음</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>평판 손상</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>개인 고객 데이터 도용</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>실직</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>폐업</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>근데 저건 다른 글이군요...</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>부분적으로는 FOMO 및 미디어 과대 광고에 의해 주도되는 시장에 많은 변동성이 있지만 주요 요인은 디지털 자산의 보안이며 이는 암호화폐 또는 교환 자산 평가의 가치에 영향을 미칠 수 있음을 인정하는 것이 중요합니다. 근본적으로 전체 생태계를 변화시킵니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>주요 내용:</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>핫 지갑은 항상 인터넷에 연결되어 있습니다.&nbsp;따라서 온라인 공격에 취약하지만 일상적인 사용에 더 편리합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>콜드 월렛은 대부분 인터넷에 연결되어 있지 않습니다.&nbsp;따라서 온라인 공격에 덜 취약하지만 일반적인 사용에는 덜 편리합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>지갑을 선택할 때는 보안성, 편의성, 수수료, 지원되는 코인, 보험적 요소 등을 고려해야 합니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>디지털 자산을 구매하려는 경우 저장 방법과 위치를 결정하는 것은 선택이 아니라 필수입니다.&nbsp;명목 화폐와 달리 암호&nbsp;&nbsp;<a href="https://www.coingecko.com/" target="_blank" rel="noreferrer noopener">화폐는&nbsp;</a><a href="https://www.coingecko.com/learn/what-is-a-blockchain" target="_blank" rel="noreferrer noopener">블록체인</a>&nbsp;&nbsp;에 상주하며&nbsp;&nbsp;&nbsp;지갑이라는 적절한 저장 플랫폼이 필요합니다.&nbsp;<a href="https://www.coingecko.com/learn/what-are-public-and-private-keys" target="_blank" rel="noreferrer noopener">이 지갑은 공개 및 개인 키를</a>&nbsp;통해 암호화 자산에 대한 액세스를 제공합니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>공개 키를 사용하여 암호화폐를 보내고 받고 개인 키를 사용하여 거래를 확인하고 암호화 지갑의 소유권을 증명합니다.&nbsp;공개 키는 은행 계좌 번호로, 개인 키는 핀으로 생각할 수 있습니다.&nbsp;핫 월렛과 콜드 월렛의 주요 차이점은 전자는 개인 키를 온라인에 저장하고 후자는 오프라인에 저장한다는 것입니다.&nbsp;&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이 기사에서는 핫 월렛과 콜드 월렛 논쟁, 월렛 선택 시 고려 사항, 핫 월렛과 콜드 월렛을 모두 사용하여 암호화폐 포트폴리오를 관리하는 방법에 대해 자세히 알아봅니다.&nbsp;&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="1">핫 월렛이란 무엇입니까?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>핫 지갑은 공개 키와 개인 키를 온라인에 저장하는 소프트웨어 지갑입니다.&nbsp;인터넷에 연결되어 있으면 컴퓨터나 스마트폰을 통해 액세스할 수 있습니다.&nbsp;핫 지갑은 사용하기 위해 플러그를 꽂고 뽑을 필요가 없기 때문에 매일 사용하기에 더 편리합니다. 인터넷 연결만 있으면 됩니다.&nbsp;또한 일반적으로 무료로 다운로드하여 사용할 수 있으며 누구나 쉽게 시작할 수 있는 사용자 친화적인 인터페이스를 갖추고 있습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>핫 지갑은 피싱 및 기타&nbsp;<a href="https://www.coingecko.com/learn/complete-guide-to-bitcoin-scams" target="_blank" rel="noreferrer noopener">사기</a>&nbsp;와 같은 위험에 노출되는 공개 및 개인 키를 온라인에 저장하기 때문에&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">공격에 취약합니다</a>&nbsp;.<a href="https://www.coingecko.com/learn/complete-guide-to-bitcoin-scams" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>핫월렛의 종류</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>핫 월렛에는 두 가지 유형이 있습니다. 하나는 사용자가 관리 중인 사용자 자금의 관리인 역할을 하는 중앙 집중식 거래소로 계정을 개설하는 교환 기반과 비수탁 소프트웨어 핫 월렛입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="2">거래소 기반 지갑</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>교환 기반 지갑은 중앙 집중식 교환의 일부입니다.&nbsp;중앙 집중식 거래소는 사용자 주소에 대한 개인 키를 보유하는 관리 기관입니다.&nbsp;즉, 이러한 수탁 금융 플랫폼의 고객은 기관이 보유한 핫 월렛과 콜드 월렛에 예치되기 때문에 자산을 완전히 관리할 수 없습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>안타깝게도 이로 인해 사용자는 2022년 11월 FTX의 사례에서 볼 수 있듯이 고객 자금 손실을 초래하는 특정 활동에 참여하는 거래소의 위험에 노출됩니다.&nbsp;<a href="https://www.coingecko.com/learn/what-is-proof-of-reserves-por" target="_blank" rel="noreferrer noopener">Proof of Reserves</a>&nbsp;도입으로 관리 기관이 고객의 토큰에 대해 책임을 지도록 합니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>중앙 집중식 교환 활동이 전반적으로 감소했지만, 교환 기반 지갑은 사용자가 명목 화폐로 암호화폐를 쉽게 사고 팔 수 있게 해주기 때문에 특히 소매 투자자들에게 여전히 인기가 있습니다.&nbsp;또한, 로그인 정보를 분실한 경우 해당 거래소 고객센터로 연락하시면 지갑 접근을 복구하실 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1786} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-4-1024x673.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1786"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="3">비수탁형 소프트웨어 핫 월렛</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>비수탁형 소프트웨어 핫 월렛은 모바일, 브라우저 또는 데스크톱 애플리케이션을 통해 액세스할 수 있습니다. 대부분 세 가지 모두에서 사용할 수 있습니다.&nbsp;이러한 핫 월렛의 경우 사용자는 자신의 개인 키에 대한 책임이 있으며 자금을 완전히 통제할 수 있습니다.&nbsp;즉, 뱅크런 발생 시 자금이 보관 기관에 저장되지 않기 때문에 자금이 안전하다는 의미이지만 시드 문구를 분실하면 더 이상 지갑과 그 안에 저장된 암호화폐에 액세스할 수 없습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="4">시드 문구는 무엇입니까?</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>시드 문구는 복구 문구라고도 합니다.&nbsp;이것은 12, 18 또는 24 단어의 임의 목록으로, 온체인에서 암호화 자산을 복구하기 위한 마스터 키로 사용할 수 있습니다.&nbsp;시드 문구는 공개 키를 생성하는 데 사용되는 개인 키를 생성합니다.&nbsp;월렛 소프트웨어는 일반적으로 시드 문구를 생성하여 사용자에게 안전하게 저장하기 전에 기록하도록 지시합니다.&nbsp;시드 문구는 지갑에 대한 사용자의 액세스를 잠금 해제하는 마스터 키 역할을 하므로 온라인 상태가 아닌 안전하게 저장해야 합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>시드 문구를 저장할 때 시간이 지남에 따라 색이 바래거나 물과 불에 의해 파괴될 수 있는 종이에 그냥 쓰지 마십시오.&nbsp;대신 crypto steel을 사용하여 시드 문구를 녹음하고 여러 복사본을 백업으로 만드십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>암호 관리자나 온라인 또는 장치에 시드 문구를 저장하지 마십시오.&nbsp;여기에는 사진을 찍지 않거나 Google 문서 또는 메모에 넣지 않는 것이 포함됩니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1788} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/content_Main_Table_12.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1788"/></figure>
<!-- /wp:image -->

<!-- wp:heading -->
<h2 id="5">핫 월렛의 예</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>MetaMask – 이더리움 생태계 탐색에 가장 적합&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://www.coingecko.com/learn/complete-beginners-guide-to-metamask" target="_blank" rel="noreferrer noopener">MetaMask</a>&nbsp;&nbsp;는 암호화 공간에서 가장 인기 있는 핫 지갑 중 하나이며 모든&nbsp;&nbsp;<a href="https://www.coingecko.com/learn/ethereum-virtual-machine-evm" target="_blank" rel="noreferrer noopener">EVM 호환</a>&nbsp;&nbsp;토큰을 지원합니다.&nbsp;사용하기 쉽고 데스크톱 및 모바일 장치에서 사용할 수 있습니다.&nbsp;&nbsp;게다가 네트워크를 통해 암호 교환, 전송 및 수신과&nbsp;<a href="https://www.coingecko.com/en/nft" target="_blank" rel="noreferrer noopener">NFT(대체 불가능한 토큰)</a>&nbsp;수집을 위한 추가 내장 기능이 있습니다&nbsp; .</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>교환 기반 지갑 – 손쉬운 피아트 온램프</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Exchange 기반 핫 월렛은 MetaMask와 유사하며 대부분 데스크톱 및 모바일 장치를 지원합니다.&nbsp;Exchange 기반 지갑은 대부분의 은행에 연결되어 쉽게 온보딩할 수 있으므로 새로운 암호 사용자가 브로커 대신 은행 계좌를 사용하여 암호를 직접 구매할 수 있습니다.&nbsp;지갑 서비스를 사용하려면 거래소에서 계정을 열어야 할 수도 있고 열지 않을 수도 있습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그러나 위에서 언급한 바와 같이 이러한 거래소 기반 지갑은 관리형입니다. 즉, 거래소는 기본적으로 개인 키와 코인을 보유하고 있으며 원할 때 코인을 인출할 수 있다고 약속합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Exodus – 데스크탑에 가장 적합</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><a href="https://www.exodus.com/" rel="noreferrer noopener" target="_blank">Exodus</a>&nbsp;&nbsp;는 높은 트랜잭션 속도, 사용 편의성 및 다양한 클라이언트 기능을 제공하는 데스크탑용 최고의 핫 지갑입니다.&nbsp;암호화 공간에서 가장 시각적으로 매력적이고 직관적인 지갑 중 하나입니다.&nbsp;데스크톱 전용 지갑으로 시작했지만 모바일 장치를 지원하도록 확장되었습니다.&nbsp;그러나 Windows, Linux 및 Mac 운영 체제용 Exodus 데스크톱 앱은 여전히 ​​지갑의 주요 제품입니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="6">콜드 월렛이란 무엇입니까?&nbsp;</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>콜드 또는 하드웨어 지갑은 개인 키를 오프라인에 저장하는 물리적 장치이며 비용은 $50에서 $250 사이입니다.&nbsp;콜드 월렛은 인터넷에 연결되어 있지 않기 때문에 가장 안전한 유형의 암호화폐 월렛이므로 해커가 개인 키와 하드웨어 월렛에 액세스할 수 없는 한 해커에 의해 손상될 가능성이 없습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>하드웨어 지갑은 USB 스틱이나 하드 드라이브와 유사한 물리적 장치로, 암호, PIN 및 개인 키를 장치 자체에 저장하여 작동합니다.&nbsp;실제로 컴퓨터가 맬웨어에 감염되더라도 개인 키가 인터넷에 연결되지 않는 칩에 보관되므로 콜드 월렛은 안전하게 유지됩니다.&nbsp;따라서 컴퓨터가 해킹당하거나 온라인 지갑이 손상되더라도 암호와 장치를 도난당하지 않는 한 코인은 여전히 ​​안전합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그러나 콜드 월렛은 물리적 객체이기 때문에 부주의한 취급으로 인해 손실될 위험이 있습니다.&nbsp;불행하게도 암호화 하드웨어 지갑을 분실하거나 도난당한 경우 시드 문구를 사용하여 개인 키를 재생성할 수 있습니다.&nbsp;따라서 시드 문구를 안전하게, 오프라인 및 하드 카피에 보관하는 것을 잊지 마십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>콜드 월렛은 장기 암호화 저장에 이상적이므로 거래 자금보다 암호화를 보관하는 데 더 적합합니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1790} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-9-1024x673.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1790"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="7">&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>원장</h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1792} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/content_image_265.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1792"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>출처: 렛저 나노 X</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://gcko.io/ledger">Ledger</a>&nbsp;&nbsp;는 Ledger Nano X, Ledger Nano S 및 Ledger Nano S plus 지갑을 제공하는 가장 인기 있는 암호화폐 하드웨어 지갑 제공업체 중 하나입니다.&nbsp;이러한 장치는 Blockchain Open Ledger 운영 체제라는 Ledger 운영 체제에서 실행되는 썸 드라이브 크기 정도입니다.&nbsp;또한 투명 OLED 디스플레이 화면 인터페이스가 내장되어 있고 거래 확인을 위한 2개의 탐색 버튼이 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Ledger는 Ledger Live 모바일 앱과 암호화 데이터를 저장하는 데 사용되는 보안 요소 칩으로 높은 수준의 보안을 제공합니다.&nbsp;주력 모델인 Ledger Nano X는 5,500개 이상의 토큰에 대한 암호화폐 호환성을 제공합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>안전한</h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1793} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/10712964857906.jpg" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1793"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><a href="https://shop.trezor.io/product/trezor-model-t?offer_id=15&amp;aff_id=1143">Trezor는</a>&nbsp;&nbsp;Trezor One 및 Trezor Model T를 제공하는 또 다른 잘 알려진 하드웨어 지갑입니다. Trezor Model T는 1,456개의 코인 및 토큰과 호환되며 데스크톱, 브라우저 및 Android Trezor Suite와 함께 제공됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Trezor Suite는 암호화폐를 검색 및 구매하고, 자산을 관리하고, 암호화폐를 안전하게 보낼 수 있는 사용자 인터페이스입니다.&nbsp;이렇게 하면 사용자 경험이 향상되지만 인터넷 지원 장치를 사용할 때 보안 취약점이 발생할 가능성이 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="8">지갑 선택 시 고려 사항</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>필요에 따라 핫 월렛, 콜드 월렛 또는 둘 다를 선택할 수 있습니다.&nbsp;위에서 다룬 세 가지 유형의 지갑을 이 표에서 서로 비교하는 방법을 요약했습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1794} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/Main-Table-11-1024x436.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1794"/></figure>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3>보안</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>암호화폐 지갑을 선택할 때 보안은 핵심 기능입니다.&nbsp;블록체인 기술은 안전하고 변경할 수 없는 특성으로 유명합니다.&nbsp;지갑에 최상의 보안 기능이 있는지 확인하는 것이 필요합니다.&nbsp;콜드 월렛은 피싱이나 기타 해킹 및 사기와 같은 잠재적인 사이버 보안 위험에 노출되어 항상 인터넷에 연결되어 있지 않기 때문에 핫 월렛보다 더 안전합니다.&nbsp;또한 자산에 대한 무단 액세스를 방지하기 위해 지갑에 이중 인증(2FA) 기능이 있는지 확인하십시오.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>편의&nbsp;</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>콜드 월렛은 개인 키를 오프라인에 저장하기 때문에 자금을 이체하기 위해 물리적 장치를 연결하고 웹 기반 계정에 연결해야 합니다.&nbsp;반면에 핫 월렛은 온라인 상태입니다.&nbsp;따라서 일일 거래와 같은 일상 거래에 사용하기가 훨씬 쉽습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>추가 거래 수수료</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>어떤 지갑을 사용하든 관계없이 여전히 가스 수수료가 부과됩니다.&nbsp;그러나 교환 기반 지갑에는 가스 가격에서 파생된 추가 요금이 포함될 수 있지만 교환의 기본 토큰을 보유하거나 스테이킹하는 경우 이 수수료가 면제될 수 있습니다.&nbsp;지갑을 다운로드하거나 구매하기 전에 먼저 서비스 요금을 확인하십시오.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>지원되는 코인</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>사용하려는 지갑이 투자하려는 코인을 지원하지 않을 수 있습니다. 일부 지갑은 하나의 코인만 지원합니다!&nbsp;<a href="https://wallet.mycelium.com/" rel="noreferrer noopener" target="_blank">예를 들어 균사체를</a>&nbsp;고려하십시오&nbsp;&nbsp;.&nbsp;뛰어난 기능에도 불구하고 비트코인만 지원합니다.&nbsp;따라서 실망하지 않도록 사용하기 전에 지갑의 지원되는 코인 및 토큰 목록을 확인하십시오.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>보험</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>일부 관리인은 기술적 문제 또는 도난으로 인해 손실을 입은 사용자를 위해 자산 보험을 제공합니다.&nbsp;커스터디안은 보험 상품이 다르지만 금융 기관과 공동으로 자산을 보장하는 상품을 선택하는 것이 좋습니다.&nbsp;예를 들어 바이낸스는 미국 고객을 위해 최대 $250,000의 USD 예금에 대한 보험을 제공합니다.&nbsp;<a href="https://www.fdic.gov/" rel="noreferrer noopener" target="_blank">이 정책을 구현하기 위해 연방예금보험공사(FDIC)</a>&nbsp;와 제휴했습니다&nbsp;&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="9">핫 및 콜드 월렛을 사용하여 암호화 포트폴리오 관리</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>핫월렛은 콜드월렛보다 데일리용으로 더 편리합니다.&nbsp;반면에 콜드 월렛은 핫 월렛보다 최대의 보안을 보장합니다.&nbsp;두 지갑 모두 광범위한 암호화폐를 지원합니다.&nbsp;따라서 귀하에게 이상적인 지갑은 지갑을 정기적으로 사용하는 편의성보다 자금의 안전을 우선시하는지 여부에 달려 있습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>두 가지 방법을 결합하여 두 가지 이점을 모두 누릴 수 있습니다.&nbsp;예를 들어 거래 목적으로 소량의 자금을 핫 지갑에 보관하고 나머지 자금을 장기 투자로 콜드 지갑에 보관할 수 있습니다.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>블록체인 네트워크 참여자로서 당사자는 소위 "지갑"에 의존하여 계정 및 블록체인과의 상호 작용을 관리할 수 있습니다.&nbsp;파티에는 여러 개의 키가 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>문제</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>당사자의 지갑은 키 도용으로 이어지는&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">악의적인 공격</a>&nbsp;에 취약합니다 .&nbsp;손상된 경우 공격자는 키를 사용하여 해당 당사자의 ID로 트랜잭션을 발행할 수 있습니다.&nbsp;키 손상을 방지하는 방법은 무엇입니까?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>힘:</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>보안 – 특히 인터넷에 연결되어 있을 때 키가 장치에 저장되어 있을 때 해킹될 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>유용성 – 일부 키는 블록체인 참가자가 자주 사용하는 반면 다른 키는 드물게 사용하거나 백업 역할을 할 수 있습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>해결책</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>사용자는 핫 지갑</em>&nbsp;&nbsp;과&nbsp;&nbsp;<em>콜드 지갑의</em>&nbsp;두 가지 유형의 지갑에 키를 저장할 수 있습니다&nbsp;&nbsp;.&nbsp;핫 월렛은 일반적으로 인터넷에 연결된 블록체인 게이트웨이를 말합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://i0.wp.com/research.csiro.au/blockchainpatterns/wp-content/uploads/sites/249/2020/06/hot-cold.png?ssl=1"></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="caption-attachment-311">핫 및 콜드 월렛 보관 패턴</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>핫월렛을 통해 사용자는 블록체인에 직접 트랜잭션을 발행할 수 있습니다.&nbsp;따라서 핫 지갑은 일반적으로 자주 사용되는 키를 보관합니다.&nbsp;콜드 월렛은 잠재적인 공격을 최소화하기 위해 오프라인 상태로 유지되는 키 저장소를 말합니다.&nbsp;따라서 클로드 지갑에는 일반적으로 거의 사용되지 않는 키가 포함됩니다.&nbsp;콜드 월렛은 인터넷 연결이 끊긴 모든 장치이거나 엔터티의 키를 기록하는 종이일 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>거래 서명을 위해 콜드 월렛에 저장된 키가 필요한 경우 사용자는 콜드 월렛 장치를 컴퓨터에 연결하고 해당 필드에 키를 복사하여 붙여넣어야 합니다.&nbsp;사용 빈도(예: 최근에 가장 적게 사용된 항목 및 가장 자주 사용된 항목)에 따라 2개의 지갑 간에 키 마이그레이션을 자동화하는 것도 가능합니다.&nbsp;또한 특정 키는 주로 콜드 월렛에 보관되도록 중요 키로 표시될 수 있습니다.&nbsp;트랜잭션 서명이 필요한 경우 핫 월렛에 복사할 수 있습니다.&nbsp;그러나 트랜잭션이 서명되는 즉시 핫 월렛에서 삭제되어야 합니다.&nbsp;특정 애플리케이션 설정, 블록체인 플랫폼 및 지갑 구현에서는 콜드 월렛에서 트랜잭션에 완전히 서명하고 핫 월렛을 사용하여 서명된 트랜잭션을 블록체인에 발행/릴레이하는 것도 가능합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>이익</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>보안 저장 – 콜드 월렛은 인터넷과 격리되어 있습니다.&nbsp;따라서 키를 위한 안전한 저장소를 제공합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>사용성 – 콜드 월렛이 인터넷에 연결되면(직접 또는 미들웨어를 통해) 당사자가 해당 키를 사용할 수 있으므로 이러한 보안 저장소는 키의 사용성을 보존합니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>단점</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>보안 – 핫 지갑은 비밀 키를 온라인에 저장하므로 도난에 더 취약합니다.&nbsp;콜드 월렛은 키를 복사/이전하기 위해 핫 월렛에 연결되는 순간 더 취약해집니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>사용성 – 콜드 월렛은 핫 월렛보다 안전하지만 사용자가 콜드 월렛에 연결해야 하므로 사용 편의성이 떨어집니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>관련 패턴</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://research.csiro.au/blockchainpatterns/master-sub-key/">마스터 및 서브 키 생성</a>&nbsp;패턴 에서&nbsp;&nbsp;&nbsp;마스터 키는 콜드 월렛에 보관할 수 있고 서브 키는 핫 월렛에 보관할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://research.csiro.au/blockchainpatterns/general-patterns/self-sovereign-identity-patterns/key-management-patterns/key-sharding/">키 샤딩</a>&nbsp;&nbsp;패턴은 지갑 애플리케이션에서 키를 분할 및 병합하여 손상을 최소화하는 데 사용할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>지갑 애플리케이션에 통합될 때&nbsp;&nbsp;<a href="https://research.csiro.au/blockchainpatterns/general-patterns/self-sovereign-identity-patterns/update-by-delegates/">위임 목록</a>&nbsp;&nbsp;패턴의 미리 정의된 위임이 손상된 키의 키 소유권을 대체할 수 있습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><strong>알려진 용도</strong></p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.myetherwallet.com/">MyEtherWallet은</a>&nbsp;&nbsp;이더리움에서 즉시 지불 및 출금을 위한 그래픽 인터페이스가 있는 핫 지갑입니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://trezor.io/">Trezor</a>&nbsp;&nbsp;는 사용자의 코인, 암호 및 기타 디지털 키를 저장하고 암호화하도록 설계된 암호화폐 하드웨어 지갑입니다.&nbsp;모든 개인 데이터를 저장하는 독립 메모리가 있는 단일 목적 컴퓨터입니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.ledger.com/">Ledger는</a>&nbsp;&nbsp;사용자의 개인 키를 안전한 하드웨어 장치에 저장하여 암호화폐를 보호하는 하드웨어 지갑 제품을 제공합니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 id="0391">다양한 암호화 스토리지 옵션 살펴보기</h2>
<!-- /wp:heading -->

<!-- wp:image {"id":1796} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/image-72-1024x576.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1796"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p id="df6c"><strong>각 지갑의 장단점은 무엇입니까</strong>&nbsp;?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="3fd8">핫월렛은 인터넷에 연결된 모든 암호화폐 지갑을 말합니다.&nbsp;일반적으로 핫 월렛은 더 많은 토큰을 설정, 액세스 및 수락하기가 더 쉽습니다.&nbsp;그러나 그들은 또한&nbsp;<a href="https://cryptodeeptech.ru/blockchain-attack-vectors/" target="_blank" rel="noreferrer noopener">해커 공격</a>&nbsp;, 가능한 규제 및 기타 기술적 취약성에 더 취약합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="fa90">콜드 스토리지는 인터넷에 연결되지 않은 암호화폐 지갑을 말합니다.&nbsp;전반적으로 콜드 월렛은 더 안전하지만 핫 월렛만큼 많은 암호화폐를 허용하지는 않습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="2ad2">콜드 월렛을 받아야 합니까?</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p id="5080">비트코인, 이더리움 또는 100달러 이상의 가치가 있는 기타 암호화폐를 소유하려는 경우 지금 당장 콜드 월렛을 구입할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="c451">사람들이 "Bitcoin은 당신 자신의 은행이 될 수 있는 기회를 제공합니다"라고 말하는 것을 들어보셨습니까?&nbsp;이 책임에는 장점과 단점이 있습니다.&nbsp;일반적으로 암호화폐는 중개인 수수료가 적고 복잡한 은행 규제 등이 적습니다. 그래도 자산의 안전을 보장하는 것은 귀하의 책임입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="45fe">전반적으로, 일반적으로 주머니에 보관하는 전통적인 가죽 지갑과 마찬가지로 핫 지갑에 많은 돈을 넣어 두어야 합니다.&nbsp;도둑이 일반 지갑을 훔치려고 하면 은행 계좌에 있는 돈이 아니라 주머니에 있는 돈만 잃게 됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p id="45b5">요컨대, 여기에 도움이 될 수 있는 비유가 있습니다. 핫 지갑은 시내를 돌아다니는 주머니 지갑으로 생각할 수 있습니다.&nbsp;콜드 월렛은 은행 예금입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1 id="7996">핫 월렛의 장단점</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":1} -->
<h1 id="ef48">핫 월렛을 사용하면 다음과 같은 이점이 있습니다.</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>PIN과 액세스 번호를 지갑에 입력하면 코인에 빠르게 액세스할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>투자 비용이 더 낮습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>여기에는 핫 월렛으로 기능하는 광범위한 애플리케이션 또는 소프트웨어 포트폴리오가 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>PIN 코드 또는 보안 코드를 설정해야 사용할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>그들은 당신이 운영하고 거래할 수 있도록 모든 플랫폼에 연결할 수 있습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="d294">이러한 지갑 중 하나를 사용하면 다음과 같은 단점이 있을 수 있습니다.</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>돈이 클라우드에 저장되고 사이버 사기꾼에게 더 취약하기 때문에 도난 위험이 높아집니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>항상 인터넷에 연결되어 있어야 합니다.&nbsp;그렇지 않으면 지원할 수 없기 때문에 인터넷 연결에 실패할 경우 큰 문제가 될 수 있습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="d041">콜드 월렛의 장단점</h1>
<!-- /wp:heading -->

<!-- wp:heading {"level":1} -->
<h1 id="2510">이 지갑을 사용하면 다음과 같은 이점이 있습니다.</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>이 유형의 지갑은 인터넷 없이도 작동하며 인터넷에서 많은 절도가 발생하므로 높은 수준의 보안을 제공합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>콜드 월렛은 ERC20 또는 기타 토큰 표준을 지원하며 무제한의 토큰을 지원할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>PIN 코드 또는 보안 코드를 설정해야 사용할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>어디서나 장치를 사용할 수 있습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":1} -->
<h1 id="c4a5">이러한 지갑 중 하나를 사용하면 다음과 같은 단점이 발생할 수 있습니다.</h1>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>기기를 분실할 위험이 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>이러한 유형의 장치로는 거래할 수 없습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>그것을 얻으려면 약 $ 100를 투자해야합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>다른 물리적 장치와 마찬가지로 오류, 손상 또는 읽기 문제가 발생하기 쉽습니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p id="a37a">거래를 하고 싶다면 핫 월렛이 더 나은 선택임을 기억하세요.&nbsp;그래도 가능한 한 암호화하고 가장 중요한 보안을 위해 최상의 소프트웨어를 선택하는 것이 좋습니다.&nbsp;반면에 비 거래 투자자이고 최고 수준의 보호를 원한다면 콜드 월렛이 더 나은 선택이 될 것입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>핫 지갑과 콜드 지갑은 암호화폐 자산을 안전하게 보관하기 위한 필수품입니다.&nbsp;전자가 암호화 토큰을 보내고 받는 데 사용되는 경우 후자는 누적되는 암호화폐를 취약성 없이 안전하게 보관합니다.&nbsp;핫 월렛은 토큰을 보내고 받기 위해 인터넷 연결이 필요하기 때문에 엄청난 비용이 드는 것으로 입증된 암호화 공격의 위험에 크게 노출되어 있습니다.&nbsp;따라서 많은 양의 토큰을 보유할 수 없습니다.&nbsp;여기에서 콜드 월렛의 사용이 시작됩니다.&nbsp;핫 지갑과 콜드 지갑을 모두 활용하는 것은 공격자에게 허점을 남기지 않는 암호화 취약성 관리의 안전한 관행입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>핫 지갑과 콜드 지갑 아키텍처를 이해하고 취약성의 위험을 완화하기 위해 어떻게 설정해야 하는지 알아보겠습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#What-are-hot-wallets?">핫 월렛이란 무엇입니까?</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#What-are-cold-wallets?">콜드 월렛이란 무엇입니까?</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#Hot-wallet-vs-Cold-Wallet-Differences">핫월렛 vs 콜드월렛: 차이점</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#Hot-and-cold-wallet-setupns?">핫 및 콜드 월렛 설정</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#How-does-hot-and-cold-wallet-interact?">핫 월렛과 콜드 월렛은 어떻게 상호 작용합니까?</a></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><a href="https://www.leewayhertz.com/hot-and-cold-wallet-architecture/#How-do-hot-and-cold-wallet-setups-in-big-systems-work?">대규모 시스템에서 핫 및 콜드 월렛 설정은 어떻게 작동합니까?</a></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="What-are-hot-wallets?">핫 월렛이란 무엇입니까?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>핫월렛은 항상 인터넷에 연결되어 있고 콜드월렛보다 사용자가 더 쉽게 접근할 수 있는 암호화폐 지갑입니다.&nbsp;모바일, 데스크톱 또는 웹 기반 지갑이 될 수 있으며 사용자 친화적이며 암호화 사용자 간에 통화를 쉽게 전송할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>개인 키는 앱 자체의 핫 월렛에 보관 및 암호화되어 온라인에 저장됩니다.&nbsp;여기에는 숨겨진 취약점이 있으며 해커는 이를 대상으로 시스템에 침입할 수 있습니다.&nbsp;사용 편의성으로 인해 암호화폐를 구매 및 거래하거나 잠시 후 자산을 현금화하는 데 가장 선호되는 지갑입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>핫 월렛 스토리지는 어떻게 작동합니까?</strong></h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1798} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-wallet-storage-work.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1798"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>컴퓨터나 장치에 핫 월렛 스토리지를 설치하면 실제로 암호화폐를 보유하지 않고도 암호화폐 자산을 구매, 전송 및 수신할 수 있습니다.&nbsp;대신 사용자가 트랜잭션을 시작할 수 있는 개인 키를 보유합니다.&nbsp;이는 자산을 저장하는 블록체인과 상호 작용하기 때문에 가능합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask는 오늘날 사용 가능한 가장 인기 있는 핫 지갑 중 하나입니다.&nbsp;그래서 메타마스크를 이용하여 핫월렛이 어떻게 작동하는지 설명드리겠습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Metamask는 블록체인, 특히 이더리움과 브라우저 사이의 브리지 역할을 하는 웹 브라우저 확장으로 사용할 수 있습니다.&nbsp;Metamask를 다운로드하여 설치하고 브라우저 확장 프로그램으로 추가하면 '지갑 가져오기' 또는 '지갑 생성'을 묻는 메시지가 표시됩니다.&nbsp;가져오기 지갑을 사용하면 비밀 복구 문구를 입력하여 기존 지갑을 추가할 수 있으며 후자는 새 암호화폐 지갑을 만들 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>새 지갑을 생성하는 경우 기기의 앱 또는 플랫폼을 보호하려면 새 메타마스크 비밀번호를 설정해야 합니다.&nbsp;이 암호는 비밀 복구 문구 대신 앱에 액세스하는 데 정기적으로 사용할 수 있는 문자열, 얼굴 인식 또는 지문일 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>비밀번호를 생성한 후에는 비밀 백업 문구를 복사하여 붙여넣거나 안전한 장소에 적어 두어야 합니다.&nbsp;Metamask 지갑에 있는 각 계정에 대해 개인 키가 제공됩니다.&nbsp;이 개인 키를 사용하여 암호 화폐를 잠금 해제할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="What-are-cold-wallets?">콜드 월렛이란 무엇입니까?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>콜드 월렛은 하드웨어 기반이며 오프라인에 존재합니다.&nbsp;콜드 월렛은 핫 월렛만큼 사용하기 편리하지는 않지만 훨씬 더 안전합니다.&nbsp;이 오프라인 지갑을 사용하면 온라인 해커로부터 키를 완전히 보호할 수 있습니다.&nbsp;콜드 월렛은 종이 지갑일 수도 있고 하드웨어 장치일 수도 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>종이 지갑은 개인 및 공개 키를 종이에 기록하거나 인쇄하는 전통적인 방법입니다.&nbsp;피싱 공격에 취약하지 않기 때문에 키를 안전하게 저장하는 방법입니다.&nbsp;하드웨어 지갑은 키를 저장하는 USB 또는 Bluetooth 장치 형태의 외부 장치입니다.&nbsp;콜드월렛은 유동성이 적기 때문에 암호화폐 자산을 장기간 구매하고 보유하려는 사람들에게 가장 적합합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>오프라인 콜드월렛과 온라인 핫월렛 간의 거래를 위해서는 하드웨어 장치를 인터넷이 가능한 다른 장치(주로 컴퓨터)에 플러그를 사용하여 연결한 다음 콜드월렛에서 핫월렛으로 필요한 금액을 이체해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3><strong>콜드 월렛 스토리지는 어떻게 작동합니까?</strong></h3>
<!-- /wp:heading -->

<!-- wp:image {"id":1800} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-wallet-storage-work-1.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1800"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>콜드 월렛 자체로는 블록체인에 연결하여 거래를 완료할 수 없습니다.&nbsp;사용자가 거래에 콜드 월렛을 사용하려면 인터넷에 연결된 장치에 연결해야 합니다.&nbsp;그러나 이것은 개인 키를 보안 위협에 노출시키지 않습니다.&nbsp;어떻게 작동하는지 봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>콜드 월렛 스토리지는 크게 콜드 월렛 코어와 콜드 게이트웨이의 두 가지 구성 요소로 나눌 수 있습니다.&nbsp;콜드 월렛 코어는 인터넷에 액세스할 수 없고 완전히 에어갭이지만 콜드 게이트웨이는 인터넷에 연결됩니다.&nbsp;콜드 월렛의 콜드 게이트웨이에서 트랜잭션이 생성된 다음 오프라인 콜드 월렛 코어에서 서명됩니다.&nbsp;따라서 사용자가 x개의 토큰을 다른 지갑으로 보내려는 경우 인터넷이 연결된 콜드 게이트웨이에서 트랜잭션이 생성되지만 트랜잭션 서명은 오프라인으로 수행됩니다.&nbsp;트랜잭션이 서명된 후 콜드 월렛 코어에서 공개되거나 온라인으로 방송됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>이를 더 잘 이해하기 위해 콜드 월렛 ELLIPAL의 예를 들어 보겠습니다.&nbsp;ELLIPAL은 본질적으로 안전한 콜드 지갑인 에어갭 하드웨어 지갑입니다.&nbsp;인터넷과 완전히 격리되어 있으며 무단 액세스, 해킹, 맬웨어 및 기타 온라인 공격을 방지하도록 설계되었습니다.&nbsp;따라서 트랜잭션을 시작하려면 사용자는 블록체인에 연결하기 위한 프록시 역할을 하는 ELLIPAL 모바일 앱을 설치해야 합니다.&nbsp;ELLIPAL 지갑을 통한 전체 거래 프로세스는 다음 단계로 요약할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li>사용자는 앱에서 트랜잭션을 시작합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>앱에서 콜드 월렛의 확인을 요청합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>하드웨어 지갑은 개인 키를 통해 트랜잭션에 서명합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>승인 후 앱에서 거래를 완료합니다.</li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 id="Hot-wallet-vs-Cold-Wallet-Differences">핫월렛 vs 콜드월렛: 차이점</h2>
<!-- /wp:heading -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th scope="col"></th><th scope="col"><strong>핫 월렛</strong></th><th scope="col">콜드 월렛</th></tr></thead><tbody><tr><td><strong>인터넷 연결</strong></td><td>온라인</td><td>오프라인</td></tr><tr><td><strong>접근성</strong></td><td>쉽게 접근 가능</td><td>낮은 접근성</td></tr><tr><td><strong>명백</strong></td><td>소프트웨어 기반 지갑&nbsp;무형의</td><td>물리적 지갑&nbsp;그래서 유형의</td></tr><tr><td><strong>유형</strong></td><td>모바일, 웹 또는 데스크탑 지갑</td><td>종이 또는 하드웨어 지갑</td></tr><tr><td><strong>안전</strong></td><td>해킹 및 공격에 취약합니다.&nbsp;따라서 덜 안전합니다.</td><td>해킹 및 공격에 대한 위협이 적습니다.&nbsp;그래서 더 안전하게</td></tr><tr><td><strong>편의</strong></td><td>쉽고 편리한</td><td>덜 편리함</td></tr><tr><td><strong>비용</strong></td><td>저렴</td><td>더 비싼</td></tr><tr><td><strong>유용성</strong></td><td>소량의 암호를 저장하는 것이 가장 좋습니다.</td><td>많은 양의 암호 화폐를 저장하는 것이 가장 좋습니다.</td></tr></tbody></table></figure>
<!-- /wp:table -->

<!-- wp:heading -->
<h2 id="Hot-and-cold-wallet-setupns?">핫 및 콜드 월렛 설정</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>핫월렛을 이용한 거래는 쉽고 간편하지만 보안위협으로 인해 대량의 암호화폐를 보관하는 데 사용할 수 없습니다.&nbsp;멀웨어 공격 및 피싱과 같은 보안 위협에 가장 취약한 콜드 월렛에 많은 양의 암호화폐를 보관하는 것이 좋습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>위험을 피하기 위해 지갑을 설정하는 한 가지 중요한 방법은 자금의 온라인 노출을 줄이는 핫 지갑과 콜드 지갑을 결합하는 것입니다.&nbsp;여기에서 각 지갑은 다른 용도로 설정됩니다.&nbsp;핫월렛은 받는 지갑과 보내는 지갑의 역할을 합니다.&nbsp;받는 지갑은 거래소로 들어오는 자금을 관리하고 보내는 지갑은 거래 및 거래를 위해 암호화폐를 보내는 데 사용됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>발신 및 수신 지갑 모두 온라인 서버에서 호스팅되므로 암호화 취약성의 위험을 줄이기 위해 두 지갑에 보관된 자금의 수를 최소화해야 합니다.&nbsp;나머지 암호화폐는 콜드 월렛에 보관해야 합니다.&nbsp;이렇게 하면 보안이 손상될 경우 대부분의 자산을 안전하게 보호할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="How-does-hot-and-cold-wallet-interact?">핫 월렛과 콜드 월렛은 어떻게 상호 작용합니까?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>귀하에게 전송된 모든 자금이 귀하의 수신 지갑으로 이동함에 따라 귀하의 수신 지갑에 암호화폐가 축적되어 암호화 취약점이 발생할 가능성이 있습니다.&nbsp;따라서 대부분을 콜드 월렛으로 보내고 일부는 보내는 월렛으로 보내야 합니다.&nbsp;암호화폐가 부족할 때 보내는 지갑으로 이체하려면 받는 지갑에 최소 금액이 있어야 하며 이렇게 하면 보내는 지갑이 필요할 때마다 충분한 암호화폐를 보유할 수 있습니다.&nbsp;그러나 받는 지갑으로 자금이 안정적으로 들어오지 않고 보내는 지갑에 통화가 급히 필요하다고 가정합니다.&nbsp;이 경우 콜드 월렛에서 보내는 월렛으로 필요한 금액을 송금할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="Content:HotandColdWalletArchitecture-Howtomitigatecryptovulnerability?">암호화 취약점을 완화하는 방법은 무엇입니까?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>총 200 ETH를 소유하고 있고 언제든지 자금의 30% 이상을 위험에 빠뜨리고 싶지 않다고 가정합니다.&nbsp;이 계산을 기반으로 맬웨어 공격의 심각도를 줄이려면 지갑당 최대 및 최소 임계값을 설정해야 합니다.&nbsp;따라서 받는 지갑에는 최소 10 ETH, 최대 20 ETH가 있어야 합니다.&nbsp;마찬가지로 보내는 지갑은 최소 20 ETH, 최대 40 ETH를 보유해야 합니다.&nbsp;나머지 자산은 콜드 월렛에 보관해야 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>발신 및 수신 지갑에 대한 임계값을 설정한 경우 이를 준수하고 설정된 금액이 한도를 초과하거나 감소하지 않도록 하십시오.&nbsp;초과자금은 취약점이 생기기 쉬우며, 한도 미만이면 필요할 때 필요한 금액을 생산할 수 없습니다.&nbsp;따라서 항상 충분한 양의 자금을 유지하십시오.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="How-do-hot-and-cold-wallet-setups-in-big-systems-work?">대규모 시스템에서 핫 및 콜드 월렛 설정은 어떻게 작동합니까?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>핫 지갑과 콜드 지갑 설정은 다양하며 각 설정은 개발자의 요구 사항과 사고 과정을 기반으로 설계되었습니다.&nbsp;다음 인포그래픽을 통해 빅 시스템에서 핫 월렛과 콜드 월렛 설정이 어떻게 설계되는지 이해해 봅시다.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":1802} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/hot-and-cold-wallet-setups-in-big-systems-work-696x1024.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1802"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>위의 인포그래픽에서 한 사람이 x개의 토큰을 다른 사용자에게 보내려면 애플리케이션의 프런트 엔드에 요청을 입력하고 API 레이어 또는 앱의 백엔드에서 가져옵니다.&nbsp;백엔드는 입력 요청을 지갑 서버로 전송합니다.&nbsp;일반적인 지갑 아키텍처에서 지갑 서버는 노드, 데이터베이스, API 또는 트랜잭션 서비스 관리와 같은 여러 마이크로 서비스를 처리합니다.&nbsp;이 경우 사용자 입력이 트랜잭션 서비스와 관련되므로 요청이 이 마이크로 서비스로 전송됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>그런 다음 트랜잭션 서비스는 지갑과 관련된 모든 서비스를 처리하는 지갑 마이크로 서비스에 요청을 보냅니다.&nbsp;지갑 마이크로서비스는 플랫폼마다 다를 수 있습니다.&nbsp;위의 인포그래픽에서 지갑 마이크로서비스에는 다음이 포함됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><strong>핫 월렛을 위한 자금 관리 –&nbsp;</strong>&nbsp;위험 노출을 방지하기 위해 암호 오버플로 또는 적자 없이 항상 임계값을 유지하도록 합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>허용된 IP –&nbsp;</strong>&nbsp;도메인이나 서버에 액세스할 수 있는 사람의 수를 허용한 몇 개의 신뢰할 수 있는 IP 주소로 제한합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>토큰 –&nbsp;</strong>&nbsp;x개의 ETH 또는 x개의 SOL과 같은 토큰을 관리하고 추적합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>서비스 모니터링 –&nbsp;</strong>&nbsp;이 마이크로서비스는 모든 서비스가 결함 없이 작동하는지 확인합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>임계값 –&nbsp;</strong>&nbsp;지갑에 필요한 금액이 있는지 또는 다른 사람에게 보내지 않는지 확인합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>2단계 인증 –&nbsp;</strong>&nbsp;지갑 생태계에 접근하기 전에 두 번 신원을 확인해야 하는 보안 프로세스입니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>알림 –&nbsp;</strong>&nbsp;성공적인 거래 완료 알림과 같은 중요한 문제에 대해 사용자에게 알립니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>KMS –&nbsp;</strong>&nbsp;키 관리 시스템 또는 KMS는 키를 안전하게 생성, 저장 및 관리하는 데 도움이 됩니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>핫 지갑 회전&nbsp;</strong></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>트랜잭션 입력이 트랜잭션 서비스에서 지갑 마이크로서비스로 전달되면 위의 모든 마이크로서비스가 수행됩니다.&nbsp;모든 서비스가 완료되고 핫 월렛에 충분한 수의 토큰이 있는지 확인되면 x개의 토큰이 수신자에게 전송됩니다.&nbsp;그러면 트랜잭션이 성공적으로 완료되었다고 합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>결론</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>핫 지갑과 콜드 지갑을 모두 병합하면 사용자와 서비스 제공자 모두에 대한 암호화 공격의 위험을 완화할 수 있습니다.&nbsp;하나는 암호화폐 거래에 사용되고 다른 하나는 암호화폐를 안전하게 보관하는 데 사용되는 두 지갑의 이점을 제공함으로써 편안한 중간 지점 역할을 합니다.&nbsp;암호화폐가 등장한 초기에는 핫월렛만 유행했지만 요즘은 콜드월렛을 많이 사용하고 있습니다.&nbsp;또한 핫 지갑과 콜드 지갑을 혼합하는 것은 엄청난 이점으로 인해 암호화 전문가와 서비스 제공 업체 사이에서 점차 주목을 받고 있습니다.&nbsp;따라서 하나의 지갑만 사용하는 것은 구식이며 사람들은 추가 보안 수단으로 핫 지갑과 콜드 지갑을 결합하는 이점을 점차 깨닫습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Cold-and-Hot-Wallets" target="_blank" rel="noreferrer noopener">GitHub</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">텔레그램: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://youtu.be/NrQ3oNxlrlU" target="_blank" rel="noreferrer noopener"><strong>비디오: https://youtu.be/NrQ3oNxlrlU</strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/cold-and-hot-wallets" target="_blank" rel="noreferrer noopener">출처: https://cryptodeep.ru/cold-and-hot-wallets</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":1817} -->
<figure class="wp-block-image"><img src="https://cryptodeeptech.ru/wp-content/uploads/2022/12/030-1-1024x576.png" alt="콜드 및 핫 지갑은 취약점을 찾아 블록체인에 대한 다양한 공격을 제거합니다." class="wp-image-1817"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
