# secp256k1 타원 곡선을 위한 유용하고 효율적인 알고리즘

<!-- wp:embed {"url":"https://www.youtube.com/embed/gFbiBCNPsFk","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/gFbiBCNPsFk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;이 기사에서는 짧은 Weierstrass 방정식에 의해 주어진&nbsp;&nbsp;필드&nbsp;&nbsp;<strong><em>GF(p)</em></strong>&nbsp;에 대한 타원 곡선&nbsp;&nbsp;<strong><em>E 에 대한 몇 가지 유용하고 효율적인 알고리즘을 고려할 것입니다.</em></strong><strong><em></em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><code>у^2&nbsp;= х^3&nbsp;+ Ах + В</code>&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>&nbsp;<strong><em>곡선 E</em>&nbsp;에 점을 생성하는 알고리즘&nbsp;<em></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>포인트 추가 알고리즘</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>더블링 포인트 알고리즘</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>정수 다중점을 찾는 알고리즘</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>정수 배수점을 찾는 알고리즘(스칼라 곱셈)</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>&nbsp;주어진 크기 d의&nbsp;&nbsp;<em>지원&nbsp;</em><em>supp</em>&nbsp;&nbsp;(&nbsp;&nbsp;<em>D)를 사용하여 곡선&nbsp;</em><em>E</em>&nbsp;&nbsp;에 대해&nbsp; 제수 D&nbsp;를 구성하는 알고리즘&nbsp;<em></em><em></em><em></em></strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong><em><sub></sub></em><em></em></strong><em>supp(D)</em>&nbsp;&nbsp;∩ {P, O} = ∅가&nbsp;<strong>&nbsp;되도록&nbsp;&nbsp;</strong><strong>&nbsp;제수&nbsp;&nbsp;</strong><strong><em>D 에서 Weil 함수&nbsp;</em></strong><strong><em>f&nbsp;&nbsp;</em></strong><strong><em><sub>n, P</sub></em></strong><strong>&nbsp;의 값을 계산하기 위한 Miller의 알고리즘&nbsp;</strong></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>&nbsp;<strong>페어링&nbsp;</strong>&nbsp;<em>웨일</em></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>유한 필드(또는 갈루아 필드)에 대한 모듈식 연산(정수)</h4>
<!-- /wp:heading -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><em>x mod n은</em>&nbsp;&nbsp;"x를 나눈 나머지 n"을 의미합니다.&nbsp;즉,&nbsp;&nbsp;<em>x = an + b</em>&nbsp;&nbsp;이고 a, b ∈ 정수이고 또한 0 ≤ b ≤ n − 1이면&nbsp;&nbsp;<em>x mod n = b</em>&nbsp;입니다 &nbsp;.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>역순</strong>&nbsp;&nbsp;:&nbsp;&nbsp;<em>ax = 1 mod n</em>&nbsp;&nbsp;이면&nbsp;&nbsp;<em>a 는&nbsp;</em><em>x mod n</em>&nbsp;&nbsp;의 역수입니다&nbsp;&nbsp;&nbsp;.&nbsp;<em>널리 사용되는 두 가지 해결</em>&nbsp;방법이&nbsp; 있습니다&nbsp;&nbsp;. •&nbsp;&nbsp;<strong><em>방법 1</em></strong><em>&nbsp;: xa mod n = 1</em>&nbsp;&nbsp;인 한&nbsp;&nbsp;<em>a &lt; n</em>&nbsp;&nbsp;에 대해 각 값을 시도합니다&nbsp;&nbsp;&nbsp;. •&nbsp;&nbsp;<strong><em>방법 2</em></strong>&nbsp;&nbsp;: 일반적으로 큰 정수의 역 문제를 해결하는 데 사용되는 유클리드 방법이므로 권장합니다. 방법 1을 사용하여 작은 정수의 역 문제를 해결합니다.<em></em><strong><em></em></strong></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>타원 곡선 점 연산</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>&nbsp;타원 곡선&nbsp;&nbsp;<em>E</em>&nbsp;상의 점&nbsp;&nbsp;<em>P(x&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;)</em>&nbsp;&nbsp;는 그&nbsp;&nbsp;<em>x&nbsp;&nbsp;</em><em><sub>0</sub></em>&nbsp;&nbsp;및&nbsp;&nbsp;<em>y&nbsp;&nbsp;</em><em><sub>0</sub></em>&nbsp;좌표가 &nbsp;필드 요소이고&nbsp;&nbsp;<em>x&nbsp;&nbsp;</em><em><sub>0</sub></em>&nbsp;&nbsp;및&nbsp;&nbsp;<em>y&nbsp;&nbsp;</em><em><sub>0</sub></em>&nbsp;좌표가 &nbsp;방정식을 만족함을 의미합니다.<em></em><em><sub></sub></em><em><sub></sub></em><em><sub></sub></em><em><sub></sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true} -->
<ol><!-- wp:list-item -->
<li><strong>타원 곡선에 점 추가</strong>&nbsp;&nbsp;:&nbsp;&nbsp;<em>P, Q</em>&nbsp;&nbsp;및&nbsp;&nbsp;<em>R을</em>&nbsp;&nbsp;타원 곡선의 세 점이라고 합니다.&nbsp;포인트 추가 P + Q = R.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>타원곡선 위의 배가 점</strong>&nbsp;&nbsp;:&nbsp;&nbsp;<em>P, Q를</em>&nbsp;&nbsp;타원곡선 위의 두 점이라 하자.&nbsp;더블링 포인트 P + P = 2P = Q</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><strong>점 곱셈</strong>  :  <em>P를</em>  방정식에서 정의된 곡선 <em>E</em>  의 한 점이라고 합니다.<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>도트 곱셈&nbsp;&nbsp;<em>nP는&nbsp;</em><em>nP = P + P + P + ... + P</em>&nbsp;&nbsp;(&nbsp;&nbsp;<em>n</em>&nbsp;&nbsp;회)&nbsp;&nbsp;&nbsp;로 정의되며&nbsp; , 여기서&nbsp;<em>n</em>&nbsp;&nbsp;은 정수입니다.&nbsp;<em>nP</em>&nbsp;&nbsp;는 또한 동일한&nbsp;&nbsp;<em>E</em>&nbsp;곡선의 한 점입니다 &nbsp;.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><em>aP = O</em>&nbsp;인 최소 자연수 a를&nbsp;&nbsp;<strong><em>P</em></strong><strong>&nbsp;의 차수&nbsp;<em></em></strong>&nbsp;&nbsp;라고 합니다&nbsp;&nbsp;&nbsp;.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>점 곱셈은 타원 곡선 암호 시스템에서 널리 요구됩니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list --></li>
<!-- /wp:list-item --></ol>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>분할기</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><strong></strong>&nbsp;곡선&nbsp;&nbsp;<em>E 의&nbsp;</em><strong>제수</strong>&nbsp;&nbsp;(제수)&nbsp;&nbsp;<em>​​D는</em>&nbsp;&nbsp;공식 합계로 작성된&nbsp;<strong><em>E</em></strong><strong>&nbsp;의 여러 점 집합을&nbsp;</strong>&nbsp;&nbsp;나타내는 편리한 방법입니다.&nbsp;<em></em><strong><em></em></strong></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/0b1/3e2/fbe/0b13e2fbec01a2ea5635bbcb1a36ade1.png" alt="secp256k1 타원 곡선을 위한 유용하고 효율적인 알고리즘" title=""/></figure>
<!-- /wp:image -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><em>E</em>&nbsp;에 대한 모든 약수의 집합은&nbsp;&nbsp;<em>Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;&nbsp;로 표시되고&nbsp;&nbsp;&nbsp;약수의 추가가 자연스러운 그룹을 형성합니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><sub>제로 약수: 이것은 모든 n P</sub>&nbsp;= 0 에 대한 약수이며&nbsp;&nbsp;&nbsp;, 제로 약수는&nbsp;&nbsp;<em>0 ∈ Div&nbsp;&nbsp;<sub>F q</sub>&nbsp;&nbsp;(E)</em>&nbsp;입니다 &nbsp;.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>필드&nbsp;&nbsp;<em>F&nbsp;&nbsp;<sub>q가</sub></em>&nbsp;&nbsp;특정하지 않은 경우 생략할 수 있으며 간단히&nbsp;&nbsp;<em>Div(E)</em>&nbsp;로 작성하여 &nbsp;약수 그룹을 나타냅니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading {"level":4} -->
<h4>함수 f를 E로 나눈 값</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>E</em>&nbsp;&nbsp;에 의한&nbsp;&nbsp;함수&nbsp;&nbsp;<em>f 의 약수는 함수&nbsp;</em><em>f</em>&nbsp;&nbsp;와&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;의 교차점(및 다중도)을 나타내는 데 사용됩니다&nbsp;&nbsp;&nbsp;.<em></em><em></em><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>페어링 웨일</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>e&nbsp;&nbsp;<sub>m</sub></em>&nbsp;으로 표시되는 Weyl 쌍은&nbsp;&nbsp;&nbsp;한 쌍의 점 P, Q ∈ E[m]를 입력으로 사용&nbsp;&nbsp;<em>하고&nbsp;&nbsp;<sub></sub></em><em><sup><sub>단위 em</sub></sup></em><em><sup>&nbsp;(&nbsp;&nbsp;<sub></sub></sup><sub>P</sub>&nbsp;&nbsp;, Q)</em>&nbsp;의 루트 _m을 &nbsp;출력으로&nbsp;&nbsp;<em><sub>생성합니다</sub></em>&nbsp;&nbsp;.&nbsp;Weyl 페어링의 이중 선형성은 다음 방정식으로 표현됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>em&nbsp;&nbsp;&nbsp;(P1&nbsp;&nbsp;<sub>+</sub>&nbsp;&nbsp;P2&nbsp;&nbsp;<sub>,</sub>&nbsp;&nbsp;Q) = em&nbsp;&nbsp;<sub>(</sub>&nbsp;&nbsp;P1&nbsp;&nbsp;<sub>,&nbsp;</sub><sub>Q</sub>&nbsp;&nbsp;) *&nbsp;&nbsp;<sub>em</sub>&nbsp;&nbsp;(P2, В),<sub></sub><sub></sub><sub></sub><sub></sub><sub></sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>em&nbsp;&nbsp;&nbsp;(P, Q1&nbsp;&nbsp;<sub>+</sub>&nbsp;&nbsp;Q2&nbsp;&nbsp;<sub>)</sub>&nbsp;&nbsp;=&nbsp;&nbsp;<sub>em</sub>&nbsp;&nbsp;(P, Q1&nbsp;&nbsp;<sub>)</sub>&nbsp;&nbsp;*&nbsp;&nbsp;<sub>em&nbsp;</sub><sub>(</sub>&nbsp;&nbsp;P, Q2&nbsp;&nbsp;<sub>)</sub>&nbsp;&nbsp;.<sub></sub><sub></sub><sub></sub><sub></sub><sub></sub><sub></sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Weil&nbsp;</strong>&nbsp;쌍&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;와&nbsp;&nbsp;<em>Q</em>&nbsp;&nbsp;는 숫자입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/5eb/b85/30f/5ebb8530fd881d89d3f396460464af79.png" alt="secp256k1 타원 곡선을 위한 유용하고 효율적인 알고리즘" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>여기서&nbsp;&nbsp;<em>S ∈ E</em>&nbsp;&nbsp;는 조건&nbsp;&nbsp;<em>S ∉ {O, P, −Q, P − Q}를</em>&nbsp;만족하는 점입니다 &nbsp;.&nbsp;(이것은 우변의 모든 양이 정의되고 0이 아님을 보장합니다.)&nbsp;&nbsp;<em>e&nbsp;&nbsp;<sub>m</sub>&nbsp;&nbsp;(P,Q) 의 값이&nbsp;</em><em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;,&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>Q</sub></em>&nbsp;&nbsp;및&nbsp;&nbsp;<em>S</em>&nbsp;&nbsp;의 선택에 의존하지 않는지&nbsp; 확인할 수 있습니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4>효율적인 웨일 페어링 계산 알고리즘</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p><em>E를</em>&nbsp;&nbsp;타원 곡선이라고 하고 P = (x&nbsp;&nbsp;P&nbsp;&nbsp;<sub>,</sub>&nbsp;&nbsp;y&nbsp;&nbsp;<sub>P</sub>&nbsp;&nbsp;) 및 Q = (x&nbsp;&nbsp;<sub>Q</sub>&nbsp;&nbsp;, y&nbsp;&nbsp;<sub>Q )를&nbsp;</sub><em>E</em>&nbsp;&nbsp;위의 0이 아닌 점이라고 합니다&nbsp;&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>λ를</em>&nbsp;P&nbsp;&nbsp;<em>와</em>&nbsp;&nbsp;Q&nbsp;&nbsp;<em>를</em>&nbsp;&nbsp;연결하는 선의 기울기&nbsp; 또는&nbsp;<em>P =</em>&nbsp;Q &nbsp;인 경우 P에서&nbsp;&nbsp;<em>E</em>&nbsp;&nbsp;에 대한 접선의 기울기&nbsp; 라고&nbsp;&nbsp;합니다. (선이 수직이면&nbsp;&nbsp;<em>λ</em>&nbsp;&nbsp;= ∞로 설정합니다.) 함수 g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;on을&nbsp; 정의합니다.&nbsp;<em>전자는</em>&nbsp;&nbsp;다음과 같습니다.<em></em><em></em><sub></sub><em></em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/dbc/8cd/efc/dbc8cdefc33de28911b8e41530a16687.png" alt="secp256k1 타원 곡선을 위한 유용하고 효율적인 알고리즘" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>그 다음에</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>div(g&nbsp;&nbsp;<sub>P, Q</sub>&nbsp;&nbsp;) = [P] + [Q] — [P + Q] —&nbsp;&nbsp;&nbsp;[&nbsp;<em>O</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>밀러 알고리즘</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>m ≥</em>&nbsp;로 두고&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;의 이진 확장을&nbsp;&nbsp;&nbsp;다음과 같이 씁니다.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>m = m&nbsp;&nbsp;<sub>0</sub>&nbsp;&nbsp;+ m&nbsp;&nbsp;<sub>1</sub>&nbsp;&nbsp;* 2 + m&nbsp;&nbsp;<sub>2</sub>&nbsp;&nbsp;* 2&nbsp;&nbsp;<sup>2</sup>&nbsp;&nbsp;+···+ m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;2&nbsp;&nbsp;<sup>n — 1</sup></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>m&nbsp;&nbsp;<sub>i</sub>&nbsp;&nbsp;∈ {0, 1}</em>&nbsp;&nbsp;및&nbsp;&nbsp;<em>m&nbsp;&nbsp;<sub>n — 1</sub>&nbsp;&nbsp;≠ 0</em>&nbsp;에 대해&nbsp;&nbsp;&nbsp;.&nbsp;다음 알고리즘은&nbsp;&nbsp;&nbsp;제수가 다음 조건을 충족하는 함수&nbsp;<em>f&nbsp;&nbsp;<sub>P 를 반환합니다.</sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] — [&nbsp;&nbsp;<em>mP</em>&nbsp;&nbsp;] — (&nbsp;&nbsp;<em>m — 1</em>&nbsp;&nbsp;) [&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;],</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>&nbsp;여기서 알고리즘에 의해 사용되는&nbsp;함수&nbsp;&nbsp;<em>g&nbsp;&nbsp;<sub>T, T</sub></em>&nbsp;&nbsp;및&nbsp;&nbsp;<em>g&nbsp;&nbsp;<sub>T, P는 (a)에서 정의됩니다.</sub></em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/bc1/d75/c60/bc1d75c6060123845b0b7f4b153096b0.png" alt="secp256k1 타원 곡선을 위한 유용하고 효율적인 알고리즘" title=""/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>특히&nbsp;&nbsp;<em>P ∈ E[m]</em>&nbsp;&nbsp;이면 div(&nbsp;&nbsp;<em>f&nbsp;&nbsp;<sub>P</sub></em>&nbsp;&nbsp;) =&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>P</em>&nbsp;&nbsp;] −&nbsp;&nbsp;<em>m</em>&nbsp;&nbsp;[&nbsp;&nbsp;<em>O</em>&nbsp;&nbsp;]입니다.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>요구 사항</h3>
<!-- /wp:heading -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li><code>Python 3.5</code></li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li><code>numpy</code></li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:code -->
<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/04AlgorithmsForSecp256k/

pip3 install numpy</code></pre>
<!-- /wp:code -->

<!-- wp:code -->
<pre class="wp-block-code"><code>├── Curves.py             &lt;- Набор данных эллиптических кривых
├── Divisor.py            &lt;- Создать делитель
├── EllipticCurve.py      &lt;- Классы эллиптической кривой и точки на эллиптической кривой
├── EuclideanAlg.py       &lt;- Расширенный алгоритм Евклида
├── Helper.py             &lt;- Вспомогательные функции (обратные биты, мощность по модулю) 
├── Pairing.py            &lt;- Спаривания Вейля, а так же Алгоритм Миллера
├── Tests.py              &lt;- Модульные тесты для функций
├── Tonelli_ShanksAlg.py  &lt;- Алгоритм Тонелли – Шенкса
├── main.py               &lt;- main
</code></pre>
<!-- /wp:code -->

<!-- wp:heading {"level":3} -->
<h3></h3>
<!-- /wp:heading -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/04AlgorithmsForSecp256k" target="_blank" rel="noreferrer noopener">원천</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>텔레그램:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>동영상 자료:&nbsp;&nbsp;<a href="https://youtu.be/gFbiBCNPsFk" target="_blank" rel="noreferrer noopener">https://youtu.be/gFbiBCNPsFk</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/gFbiBCNPsFk","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/gFbiBCNPsFk
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
