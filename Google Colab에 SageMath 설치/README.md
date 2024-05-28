# Google Colab에 SageMath 설치

<!-- wp:embed {"url":"https://www.youtube.com/embed/DBu0UnVe0ig","type":"rich","providerNameSlug":"вставить-обработчик","responsive":true,"className":"wp-embed-aspect-16-9 wp-has-aspect-ratio"} -->
<figure class="wp-block-embed is-type-rich is-provider-вставить-обработчик wp-block-embed-вставить-обработчик wp-embed-aspect-16-9 wp-has-aspect-ratio"><div class="wp-block-embed__wrapper">
https://www.youtube.com/embed/DBu0UnVe0ig
</div></figure>
<!-- /wp:embed -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>이 기사&nbsp;<code>SageMath</code>에서는&nbsp;<code>Google Colab</code>.&nbsp;<strong><a href="https://cryptodeeptech.ru/install-sagemath-on-fedora/" target="_blank" rel="noreferrer noopener">우리는 이전에 " Fedora 64비트(10GB) 클라우드 가상 서버에 암호 분석을 위한 SageMath 설치</a></strong>&nbsp;"라는 기사를 게시했지만&nbsp;<code>Debian</code>비트&nbsp;<code>Ubuntu</code>코인&nbsp;​​블록체인의 암호 분석을 계속하기 위해 많은 독자들이&nbsp;<code>Fedora</code>.&nbsp;우리가 아는&nbsp;<code>Google Colab</code>한&nbsp;<code>"Ubuntu 20.04.5 LTS"</code>.</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>다음 명령을 실행하여 이를 확인할 수 있습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!cat /etc/lsb-release
</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2598} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-21-1024x192.png" alt="Google Colab에 SageMath 설치" class="wp-image-2598"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>따라서&nbsp;<code>"Ubuntu 20.04.5 LTS"</code>이 버전에서는 설치만 허용합니다.<code>SageMath version 9.0, Release Date: 2020-01-01</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>표준 설치 명령 사용:</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!sudo apt-get install -y sagemath-common</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2599} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-22-1024x120.png" alt="Google Colab에 SageMath 설치" class="wp-image-2599"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>불행히도 이 버전은 제대로 작동하지 않습니다.</strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p><code>Google Colab</code>완전한 암호 분석을 위해 완전히 새로운 버전&nbsp;으로 설치합니다.<code>SageMath version 9.3</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>파일:&nbsp;우리가 게시한&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/19SageMathGoogleColab/Install_SageMath_in_Google_Colab.ipynb" target="_blank" rel="noreferrer noopener"><strong>Install_SageMath_in_Google_Colab.ipynb</strong></a><code>GitHub</code></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>공식 웹사이트로 이동합니다:&nbsp;<strong><a href="https://colab.research.google.com/" target="_blank" rel="noreferrer noopener">https://colab.research.google.com</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>"메모장 다운로드"</strong>&nbsp;옵션을 선택합니다.<strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2605} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-24.png" alt="Google Colab에 SageMath 설치" class="wp-image-2605"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>파일 다운로드:&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/19SageMathGoogleColab/Install_SageMath_in_Google_Colab.ipynb" target="_blank" rel="noreferrer noopener"><strong>Install_SageMath_in_Google_Colab.ipynb</strong></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2606} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-25.png" alt="Google Colab에 SageMath 설치" class="wp-image-2606"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p>이제 유틸리티를 통해&nbsp;<a href="https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2" target="_blank" rel="noreferrer noopener"><strong>sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</strong></a>&nbsp;를&nbsp;<code>wget</code>&nbsp;다운로드합니다 .<code>tar-file</code><a href="https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!wget https://cryptodeeptech.ru/sage-9.3-Ubuntu_20.04-x86_64.tar.bz2
!tar -xf sage-9.3-Ubuntu_20.04-x86_64.tar.bz2</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2612} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-29-1024x321.png" alt="Google Colab에 SageMath 설치" class="wp-image-2612"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>다음 디렉토리를 살펴보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>cd SageMath/</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2617} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-32-1024x110.png" alt="Google Colab에 SageMath 설치" class="wp-image-2617"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>패널을 열고 다음 폴더로 이동합니다.<code>SageMath</code></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2619} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-34.png" alt="Google Colab에 SageMath 설치" class="wp-image-2619"/></figure>
<!-- /wp:image -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong>relocate-once.py</strong>&nbsp;가 있는지 확인하십시오.<code>Python-script:</code><strong></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2618} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-33-1024x180.png" alt="Google Colab에 SageMath 설치" class="wp-image-2618"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>다음 명령으로&nbsp;<code>Python-script:</code><strong>relocate-once.py를</strong>&nbsp;실행합니다 .</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!python3 relocate-once.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2620} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-35-1024x451.png" alt="Google Colab에 SageMath 설치" class="wp-image-2620"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>모두 준비되었습니다!</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><code>SageMath</code>이제 다음 명령을&nbsp;실행해 보겠습니다 .</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>!./sage -sh</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2623} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-36-1024x304.png" alt="Google Colab에 SageMath 설치" class="wp-image-2623"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>버전 확인 명령을 실행해 보겠습니다.</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>sage -v</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2624} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-37-1024x344.png" alt="Google Colab에 SageMath 설치" class="wp-image-2624"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>괜찮은!</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>새 버전이 있습니다.&nbsp;<code>SageMath version 9.3, Release Date: 2021-05-09</code></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener">Twist Attack</a>&nbsp;알고리즘 구현&nbsp;, &nbsp;&nbsp;<code>Python-script:</code><a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.py 다운로드</a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:code -->
<pre class="wp-block-code"><code>wget https://raw.githubusercontent.com/demining/CryptoDeepTools/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2628} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-41-1024x517.png" alt="Google Colab에 SageMath 설치" class="wp-image-2628"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>이산 로그를 풀려면&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener">discrete.py를</a><em><code>(Pollard's rho algorithm for logarithms)</code></em>&nbsp;&nbsp;실행하십시오&nbsp; .<code>Python-script:</code><a href="https://github.com/demining/CryptoDeepTools/blob/bbd83042e7405508cd2e646ad1b0819da0f9c58d/18TwistAttack/discrete.py" target="_blank" rel="noreferrer noopener"></a></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>이제 개인 키를 얻으려면 다음 명령을 실행하기만 하면 됩니다.</p>
<!-- /wp:paragraph -->

<!-- wp:code -->
<pre class="wp-block-code"><code>python3 discrete.py</code></pre>
<!-- /wp:code -->

<!-- wp:image {"id":2654} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/image-43-1024x548.png" alt="Google Colab에 SageMath 설치" class="wp-image-2654"/></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong>Sage Math&nbsp;</strong><strong>9.3은</strong>&nbsp;&nbsp;이산 로그 문제를 해결합니다.&nbsp;<em><code>(Pollard's rho algorithm for logarithms)</code></em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><br>이제 모든 것이 제대로 작동합니다!</strong></p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p><strong><a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener">비트코인 지갑의 개인 키를 10진수 형식으로 받은 다음 암호 분석을 위해 Twist Attack</a></strong>&nbsp;전용 기사의 지침을 따라야 합니다.&nbsp;<strong><a href="https://cryptodeeptech.ru/twist-attack/" target="_blank" rel="noreferrer noopener"></a></strong></p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:paragraph -->
<p><strong><a href="https://github.com/demining/Install-SageMath-in-Google-Colab" target="_blank" rel="noreferrer noopener">원천</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">텔레그램: https://t.me/cryptodeeptech</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://youtu.be/DBu0UnVe0ig" target="_blank" rel="noreferrer noopener">비디오: https://youtu.be/DBu0UnVe0ig</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong><a href="https://cryptodeep.ru/install-sagemath-in-google-colab" target="_blank" rel="noreferrer noopener">출처: https://cryptodeep.ru/install-sagemath-in-google-colab</a></strong></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity"/>
<!-- /wp:separator -->

<!-- wp:image {"id":2669} -->
<figure class="wp-block-image"><img src="https://cryptodeep.ru/wp-content/uploads/2023/04/037-1-1024x576.png" alt="Google Colab에 SageMath 설치" class="wp-image-2669"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>&nbsp;<a href="https://cryptodeep.ru/category/%d0%ba%d1%80%d0%b8%d0%bf%d1%82%d0%be%d0%b0%d0%bd%d0%b0%d0%bb%d0%b8%d0%b7/">암호해독</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 class="wp-block-heading">탐색 후</h2>
<!-- /wp:heading -->
