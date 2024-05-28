# GitHub, GDrive, NGrok 등에서 작업하기 위해 Google Colab에 자체 터미널을 만듭니다.

<!-- wp:paragraph -->
<p>현재 기계 학습과 딥 러닝은 컴퓨터 과학 산업에서 가장 뜨거운 트렌드가 되었습니다.&nbsp;많은 개발자가 Google Colab으로 놀라운 프로젝트를 만듭니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>구글 코랩이 무엇인가요?</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>Google Colab은 GPU 및 TPU에 대한 무료 액세스를 제공하기 위해 Google에서 개발했습니다.&nbsp;Google Colab은 Jupyter Notebook의 개선된 버전이라고 정의할 수 있습니다.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>구글 코랩의 특징</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>Google Colab은 모든 최신 IDE에서 제공하는 많은 멋진 기능을 제공합니다.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><!-- wp:list-item -->
<li>로컬에 설치하지 않고도 Python 3 코드를 작성하고 실행할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Kaggle과 같은 외부 소스에서 데이터 세트를 가져올 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>작업을 Google 드라이브에 저장할 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Google 드라이브에서 작업을 가져올 수 있습니다.</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Google Colab은 또한 무료 클라우드 서비스, GPU 및 TPU와 PyTorch, Tensor Flow, Open CV와의 통합을 제공하지만 가장 중요한 것은 프로젝트를 GitHub에서 직접 가져오거나 게시할 수 있다는 것입니다.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>명령을 실행하자</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>!cat /etc/lsb-릴리스</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>DISTRIB_ID=우분투DISTRIB_RELEASE=18.04DISTRIB_CODENAME=바이오닉DISTRIB_DESCRIPTION=”우분투 18.04.5 LTS”</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>&nbsp;그래서 우리는 "Ubuntu 18.04.5 LTS"가</strong>&nbsp;있는지 확인했습니다&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>남은 일은&nbsp;&nbsp;<strong>JSON-RPC</strong>&nbsp;서비스에 대한 명령줄 인터프리터를 찾는 것입니다 .</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>인터넷을 서핑하다가 jQuery 터미널 에뮬레이터</strong>&nbsp;플러그인을 발견했습니다&nbsp;&nbsp;.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>다음으로 JS Shell 코드를 붙여넣었습니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/2d4/0b5/069/2d40b5069b1d3c566a225d7f1d93211d.png" alt="GitHub, GDrive, NGrok 등에서 작업하기 위해 Google Colab에 자체 터미널을 만듭니다."/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>다음은 기본 모듈이 있는 Python 코드입니다.</em></p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/803/3b6/c4e/8033b6c4e41df6312566d5e4d0cb655c.png" alt="GitHub, GDrive, NGrok 등에서 작업하기 위해 Google Colab에 자체 터미널을 만듭니다."/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p><em>다음</em>&nbsp;&nbsp;google.colab.kernel.invokeFunction('shell', [command])</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>인사말 이름 지정&nbsp;</em>&nbsp;: 'Terminal CryptoDeepTech'</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>프롬프트:'암호화 &gt;</p>
<!-- /wp:paragraph -->

<!-- wp:image -->
<figure class="wp-block-image"><img src="https://habrastorage.org/r/w1560/getpro/habr/upload_files/7b5/e31/b2d/7b5e31b2d08f84b29a1dfeabd47cb9ed.png" alt="GitHub, GDrive, NGrok 등에서 작업하기 위해 Google Colab에 자체 터미널을 만듭니다."/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><em></em><strong><em>&nbsp;GitHub, GDrive, NGrok</em></strong><em>&nbsp;&nbsp;에서 작업하기 위해&nbsp;</em><strong><em>Google Colab</em></strong><em>&nbsp;에서 터미널을 얻은 후&nbsp;</em><em></em><strong><em></em></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><strong>소스 코드:&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">https://github.com/demining/TerminalGoogleColab</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>텔레그램:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>동영상 자료:&nbsp;&nbsp;<a href="https://youtu.be/S2D7PI6dK08" target="_blank" rel="noreferrer noopener">https://youtu.be/S2D7PI6dK08</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:embed {"url":"https://www.youtube.com/embed/S2D7PI6dK08","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-4-3 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-4-3 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/S2D7PI6dK08
</div></figure>
<!-- /wp:embed -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->
