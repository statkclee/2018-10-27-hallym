---
layout: workshop      # DON'T CHANGE THIS.
carpentry: "swc"    # what kind of Carpentry (must be either "lc" or "dc" or "swc")
venue: "한림대학교"        # brief name of host site without address (e.g., "Euphoric State University")
address: "강원도 춘천시 한림대학길 1 공학관 1116-3호"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "kr"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "kr"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "37.8863, 127.7358"       # decimal latitude and longitude of workshop venue (e.g., "41.7901128,-87.6007318" - use https://www.latlong.net/)
humandate: "2018년 10월 27-28일"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "10:00 am - 18:00 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2018-10-27      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2018-10-28        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["이광춘"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["이지현"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["kwangchun.lee.7@gmail.com"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes:   "https://pad.carpentries.org/2018-10-27-hallym"          # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite: "51353898894"          # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

{% comment %} See instructions in the comments below for how to edit specific sections of this workshop template. {% endcomment %}

{% comment %}
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'make workshop-check' *before* committing to make sure that changes are good.
{% endcomment %}

{% comment %}
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">워크샵 일반 정보</h2>

{% comment %}
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/intro.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/intro.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/intro.html %}
{% endif %}

{% comment %}
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
{% endcomment %}
{% if page.carpentry == "swc" %}
  {% include sc/who.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/who.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/who.html %}
{% endif %}

{% comment %}
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use https://itouchmap.com/latlong.html to find the lat/long of an
  address.
{% endcomment %}
{% if page.latlng %}
<p id="where">
  <strong>장소:</strong>
  {{page.address}}.
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  혹은
  <a href="//maps.google.com/maps?q={{page.latlng}}">구글지도(Google Maps)</a>을 참조하세요.
</p>
{% endif %}

{% comment %}
  DATE

  This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>일시:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>사전 준비사항:</strong> 워크샵에 참여하시는 분은 관리자 권한을 갖는 맥, 리눅스, 윈도우 운영체제가 탐재된 노트북을 지참하셔야 합니다. 
  (스마트폰, 태블릿, 크롬북 등은 권장하지 않음) <a href="#setup">아래</a> 설정 표기된 데이터과학 컴퓨팅을 위한 사전 소프트웨어 팩키지를 설치하셔야 됩니다.  

  {% if page.carpentry == "swc" %}
  Software Carpentry's
  {% elsif page.carpentry == "dc" %}
  Data Carpentry's
  {% elsif page.carpentry == "lc" %}
  Library Carpentry's
  {% endif %}
  <a href="{{site.swc_site}}/conduct.html">행동강령(code of conduct)도</a> 필히 준수하셔야 합니다. 
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>접근성(Accessibility):</strong> 소프트웨어 카펜트리는 누구나 워크샵에 참석할 수 있도록 최선을 다하고 있습니다.
  워크샵 조직위는 다음을 확인했습니다:
</p>
<ul>
  <li>휠체어/스쿠터를 타고 강의실에 입장할 수 있습니다.</li>
  <li>화장실도 마찬가지로 휠체어/스쿠터로 이용가능합니다.</li>
</ul>
<p>
  워크샵 이전에 모든 강의자료는 제공되고, 워크샵 조직위에 미리 알려주시면 필요한 경우 출력물 제공도 가능합니다. 
  수화 통역사나 수유시설처럼 학습 용이성을 증진시킬 수만 있다면 다음 전자우편으로 연락주시면 최대한 제공할 수 있도록 노력할 것입니다.
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>연락처</strong>:
  추가 정보가 필요한 경우 전자우편주소
  {% if page.email %}
    {% for email in page.email %}
      {% if forloop.last and page.email.size > 1 %}
        or
      {% else %}
        {% unless forloop.first %}
        ,
        {% endunless %}
      {% endif %}
      <a href='mailto:{{email}}'>{{email}}</a>
    {% endfor %}
  {% else %}
    to-be-announced
  {% endif %}
  로 연락주세요.
</p>

<!-- 
<hr/>
{% comment %} 
 SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
{% if site.carpentry == "swc" %} 
<p><a href="{{ site.swc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.swc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "dc" %}
<p><a href="{{ site.dc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.dc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% elsif site.carpentry == "lc" %}
<p><a href="{{ site.lc_pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.lc_post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>
{% endif %}
 -->

<hr/>


{% comment %}
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">워크샵 일정</h2>

{% if page.carpentry == "swc" %}
  {% include sc/schedule.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/schedule.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/schedule.html %}
{% endif %}

{% comment %}
  Collaborative Notes

  If you want to use an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  채팅, 받아적기, URL과 실습 코드 공유를 위해서 <a href="{{page.collaborative_notes}}">Etherpad 문서</a>를 사용합니다.
</p>
{% endif %}

<hr/>

{% comment %}
  SYLLABUS

  Show what topics will be covered.

  1. If your workshop is R rather than Python, remove the comment
     around that section and put a comment around the Python section.
  2. Some workshops will delete SQL.
  3. Please make sure the list of topics is synchronized with what you
     intend to teach.
  4. You may need to move the div's with class="col-md-6" around inside
     the div's with class="row" to balance the multi-column layout.

  This is one of the places where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}
<h2 id="syllabus">강의 계획서(Syllabus)</h2>

{% if page.carpentry == "swc" %}
  {% include sc/syllabus.html %}
{% elsif page.carpentry == "dc" %}
  {% include dc/syllabus.html %}
{% elsif page.carpentry == "lc" %}
  {% include lc/syllabus.html %}
{% endif %}

<hr/>

{% comment %}
  SETUP

  Delete irrelevant sections from the setup instructions.  Each
  section is inside a 'div' without any classes to make the beginning
  and end easier to find.

  This is the other place where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
{% endcomment %}

<h2 id="setup">프로그램 설치</h2>

<p>  
  {% if page.carpentry == "swc" %}
  소프트웨어(Software Carpentry)
  {% elsif page.carpentry == "dc" %}
  Data Carpentry
  {% elsif page.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  워크샵에 참석하기 위해서 다음에 기술된 소프트웨어를 설치한다. 워크샵 시작 전에 모든 소프트웨어가 제대로 설치되었는지 확인해야 한다. (혹은 적어도 설치 프로그램을 다운로드 받아온다.)
  추가로 최신 웹브라우저(파이어폭스/크롬 등) 버전이 필요하다.
</p>
<p>
  설치과정에서 흔히 발견되는 이슈를 목록으로 관리하고 있다. 
  강사나 조교에게 <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">환경설정 문제와 해결책 위키 웹페이지</a>가 도움이 될 수 있다.
</p>

<div id="shell"> {% comment %} S

tart of 'shell' section. {% endcomment %}
  <h3>Bash 쉘 (Bash Shell)</h3>

  <p>
    Bash는 가장 일반적으로 사용되는 쉘 중의 하나다. 쉘을 사용하면 컴퓨터로 더 많은 작업을 더 빠르게 할 수 있는 동력을 제공받을 수 있다.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">윈도우(Windows)</h4>
      <a href="https://www.youtube.com/watch?v=339AEqk9c-8">동영상 튜토리얼(Video Tutorial)</a>
      <ol>
        <li>Git for Windows <a href="https://git-for-windows.github.io/">installer</a>를 다운로드 받는다.</li>
        <li>installer를 실행하고 다음 절차를 따라 한다:
          <ol>
            {% comment %} Git 2.18.0 Setup {% endcomment %}
            <li>
            	(Git이 설치된 경우 2번) "Next" 버튼을 4번 클릭한다.
            	Information, location, components, start menu 화면에서 설정을 전혀 변경할 필요가 없다.
            </li>
            <li>
                <strong>
                “Use the nano editor by default”을 선택하고 “Next”를 클릭한다.
                </strong>
            </li>
            {% comment %} Adjusting your PATH environment {% endcomment %}
            <li>
                "Use Git from the Windows Command Prompt" 선택을 유지하고 "Next"를 클릭한다.
                상기 작업과정을 잊게 되면, 워크샵에 필요한 프로그램이 정상적으로 동작하지 않게된다.
                이런 일이 발생되면 적절한 선택옵션을 선택해서, 설치프로그램을 재실행한다.
            </li>
            {% comment %} Choosing the SSH executable {% endcomment %}
            <li>"Next"을 클릭한다.</li>
            {% comment %} Configuring the line ending conversions {% endcomment %}
            <li>
                "Checkout Windows-style, commit Unix-style line endings"을 선택하고 "Next"를 클릭한다.
            </li>
            {% comment %} Configuring the terminal emulator to use with Git Bash {% endcomment %}
            <li>
              <strong>
                "Use Windows' default console window"을 선택하고 "Next"를 클릭한다.
              </strong>
            </li>
            {% comment %} Configuring experimental performance tweaks {% endcomment %}
            <li>"Install"을 클릭한다.</li>
            {% comment %} Installing {% endcomment %}
            {% comment %} Completing the Git Setup Wizard {% endcomment %}
            <li>"Finish"를 클릭한다.</li>
          </ol>
        </li>
        <li>
          "HOME" 환경변수가 설정되지 않은 경우(혹은, 환경변수 설정법을 모르는 경우):
          <ol>
            <li>명령 프롬프트를 연다 (즉, 시작메뉴를 열고 <code>cmd</code>을 입력하고 [Enter]를 친다.)</li>
            <li>
              다음에 나온 명령어를 명령 프롬프트에 정확하게 타이핑한다:	
              <p><code>setx HOME "%USERPROFILE%"</code></p>
            </li>
            <li>[Enter]를 치게 되면, <code>SUCCESS: Specified value was saved.</code></li> 메시지가 나온다.
            <li><code>exit</code>를 타이핑하고 [Enter]를 쳐서 명령 프롬프트를 빠져나온다.</li>
          </ol>
        </li>
      </ol>
      <p>Git Bash 프로그램이 설치되면 Git과 Bash 모두 사용가능하게 된다.</p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">맥(macOS)</h4>
      <p>
      	모든 맥 OS에서 기본 쉘은 bash라서 별도로 설치할 필요가 없다. 터미널(<code>/Applications/Utilities</code>)에서 bash를 사용할 수 있다. 워크샵에서 터미널을 바로가기로 고정한다.
        Git 설치에 대해서 <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">video tutorial</a>을 참조하면 터미널을 여는 방법이 소개되어 있다.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">리눅스(Linux)</h4>
      <p>
        기본 쉘이 bash다. 하지만 만약 컴퓨터 설정이 다르게 되어 있다면, 터미널을 열어 <code>bash</code>를 타이핑한다. 별도의 추가 설치가 불필요하다.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'shell' section. {% endcomment %}

<div id="git"> {% comment %} Start of 'Git' section. GitHub browser compatability
           is given at https://help.github.com/articles/supported-browsers/{% endcomment %}
  <h3>Git</h3>
  <p>
    Git은 현존하는 최강의 버젼 제어 시스템(version control system)이다. 
    Git을 사용해서 누가(who) 무엇(what)에 언제(when) 변경을 했는지 추적할 수 있다. 또한 <a href="https://github.com/">github.com</a>에 공유 혹은 공개 버젼의 코드를 쉽게 갱신할 수도 있다.
    크롬(Chrome), 불여우(Firefox), 사파리(Safari) 혹은 인터넷 익스플러로 버전 9이상 <a href="https://help.github.com/articles/supported-browsers/">호환되는 웹브라우저</a>가 필요하다.
  </p>
  <p>
  	버전관리 Git 수업에 <a href="https://github.com/">github.com</a> 계정이 필요하다.
  	기본 GitHub 계정은 무료다. 아직 GitHub 계정이 없는 경우 계정 생성을 강력히 권장한다.
  	대신에 노출되는 개인정보에 대해서는 다시 한번 검토하기를 바란다.
  	예를 들어, 마이크로소프트가 인수한 GitHub에 <a href="https://help.github.com/articles/keeping-your-email-address-private/">instructions
    for keeping your email address private</a> 게시글을 검토할 필요가 있따.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="git-windows">윈도우</h4>
      <p>
      	Git은 앞서 기술된 Bash 설치할 때 컴퓨터에 설치된다.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-macosx">맥(macOS)</h4>
      <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">동영상 튜토리얼(Video Tutorial)</a>
      <p>
        <strong>OS X 10.9 버전 이상에 대해서</strong>, 
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">목록</a>에서 
        가장 최신 "mavericks" 설치자를 다운로드 받아 맥용 Git(Git for Mac)을 설치한다.
        다운로드 받은 설치파일은 개발자용으로 인증된 것이 아니라서,
        .pkg 파일 위에 우클릭(컨트롤 클릭)해서 열고 팝업 윈도우에 Open을 클릭한다.        
        Git을 설치한 후에 <code>/Applications</code> 폴더에는 아무것도 없는데 Git이 명령라인 프로그램이라서 그렇다.
        <strong>OS X (10.5-10.8) 이전 버전에 대해서</strong> "snow-leopard" 라는 이름이 붙은
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">available here</a> 목록에서 가장 최신 
        설치자를 사용한다. 
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-linux">리눅스(Linux)</h4>
      <p>
      	Git이 컴퓨터에 설치되어 있지 않다면,
      	배포판 팩키지 관리자를 통해서 설치한다.
      	데비안/우분투 배포판의 경우 <code>sudo apt-get install git</code>,
      	페도라 배포판의 경우 <code>sudo dnf install git</code> 명령어를 사용해서 설치한다.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'Git' section. {% endcomment %}

<div id="editor"> {% comment %} Start of 'editor' section. {% endcomment %}
  <h3>텍스트 편집기(Text Editor)</h3>

  <p>
  	코드를 작성할 때, 키워드에 대해 자동 색상 기능을 갖는 코드작성에 최적화된 텍스트 편집기를 갖추면 최상이다.
  	맥OS나 리눅스의 경우 기본설치된 텍스트 편집기는 Vim으로 지정되어 있는데 직관적이지 않은 것으로 악명이 높다.
  	Vim을 사용하다 꼬이게 되면 Esc 키를 누른 후에 <code>:q!</code> (콜론, 소문자 'q', 느낌표)를 입력하고 나서
  	엔터키를 치게 되면 쉘로 빠져나온다.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="editor-windows">Windows</h4>
      <p>
      	워크샵에서 강사가 사용할 기본 편집기는 나노(nano)다.
      	나노 편집기는 Git 설치할 때 따라서 함께 설치된다.
      </p>
      <p>
      	학습참가자가 사용할 수 있는 다른 편집기에는 
        <a href="https://notepad-plus-plus.org/">Notepad++</a>,
        <a href="https://www.sublimetext.com/">Sublime Text</a>이 있다.
        <strong>시스템 경로에 편집기 설치 디렉토리를 추가해야하는 점에 유의한다.</strong>
        경로설정에 도움이 필요한 경우 강사에게 부탁한다.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-macosx">맥(macOS)</h4>
      <p>
        워크샵에서 강사가 사용할 기본 편집기는 나노(nano)다.
        나노 편집기를 여는 방법에 대해서 <a href="https://www.youtube.com/watch?v=9LQhwETCdwY ">동영상 튜토리얼(video tutorial)</a>에 
        나온 Git 설치방법을 참고한다. 나노는 맥에 기본 설치되어 있다.
      </p>
      <p>
        학습참가자가 사용할 수 있는 다른 편집기에는 
        <a href="https://www.barebones.com/products/textwrangler/">Text Wrangler</a>,
        <a href="https://www.sublimetext.com/">Sublime Text</a>가 있다.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-linux">리눅스(Linux)</h4>
      <p>
        워크샵에서 강사가 사용할 기본 편집기는 나노(nano)다.
        나노는 리눅스에 기본 설치되어 있다.
      </p>
      <p>
        학습참가자가 사용할 수 있는 다른 편집기에는 
        <a href="https://wiki.gnome.org/Apps/Gedit">Gedit</a>,
        <a href="https://kate-editor.org/">Kate</a>,
        <a href="https://www.sublimetext.com/">Sublime Text</a>가 있다.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'editor' section. {% endcomment %}

<div id="python"> {% comment %} Start of 'Python' section. Remove the third paragraph if
           the workshop will teach Python using something other than
           the Jupyter notebook.
           Details at https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility {% endcomment %}
  <h3>Python</h3>

  <p>
    <a href="https://python.org">Python</a> is a popular language for
    research computing, and great for general-purpose programming as
    well.  Installing all of its research packages individually can be
    a bit difficult, so we recommend
    <a href="https://www.anaconda.com/distribution/">Anaconda</a>,
    an all-in-one installer.
  </p>

    <p>
      Regardless of how you choose to install it,
      <strong>please make sure you install Python version 3.x</strong>
      (e.g., 3.6 is fine).
    </p>

    <p>
      We will teach Python using the <a href="https://jupyter.org/">Jupyter notebook</a>,
      a programming environment that runs in a web browser. For this to work you will need a reasonably
      up-to-date browser. The current versions of the Chrome, Safari and
      Firefox browsers are all
      <a href="https://jupyter-notebook.readthedocs.io/en/stable/notebook.html#browser-compatibility">supported</a>
      (some older browsers, including Internet Explorer version 9
      and below, are not).
    </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="python-windows">Windows</h4>
      <a href="https://www.youtube.com/watch?v=xxQ0mzZ8UvA">Video Tutorial</a>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#windows">https://www.anaconda.com/download/#windows</a> with your web browser.</li>
        <li>Download the Python 3 installer for Windows.</li>
        <li>Install Python 3 using all of the defaults for installation <em>except</em> make sure to check <strong>Make Anaconda the default Python</strong>.</li>
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="python-macosx">macOS</h4>
      <a href="https://www.youtube.com/watch?v=TcSAln46u9U">Video Tutorial</a>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#macos">https://www.anaconda.com/download/#macos</a> with your web browser.</li>
        <li>Download the Python 3 installer for OS X.</li>
        <li>Install Python 3 using all of the defaults for installation.</li>
      </ol>
    </div>
    <div class="col-md-4">
      <h4 id="python-linux">Linux</h4>
      <ol>
        <li>Open <a href="https://www.anaconda.com/download/#linux">https://www.anaconda.com/download/#linux</a> with your web browser.</li>
        <li>Download the Python 3 installer for Linux.<br>
          (The installation requires using the shell. If you aren't
           comfortable doing the installation yourself
           stop here and request help at the workshop.)
        </li>
        <li>
          Open a terminal window.
        </li>
        <li>
          Type <pre>bash Anaconda3-</pre> and then press
          tab. The name of the file you just downloaded should
          appear. If it does not, navigate to the folder where you
          downloaded the file, for example with:
          <pre>cd Downloads</pre>
          Then, try again.
        </li>
        <li>
          Press enter. You will follow the text-only prompts. To move through
          the text, press the space key. Type <code>yes</code> and
          press enter to approve the license. Press enter to approve the
          default location for the files. Type <code>yes</code> and
          press enter to prepend Anaconda to your <code>PATH</code>
          (this makes the Anaconda distribution the default Python).
        </li>
        <li>
          Close the terminal window.
        </li>
      </ol>
    </div>
  </div>
{% comment %}
  <p>
  Once you are done installing the software listed above,
  please go to <a href="setup/index.html">this page</a>,
  which has instructions on how to test that everything was installed correctly.
  </p>
{% endcomment %}
</div> {% comment %} End of 'Python' section. {% endcomment %}

<div id="r"> {% comment %} Start of 'R' section. {% endcomment %}
  <h3>R</h3>

  <p>
  	<a href="https://www.r-project.org">R</a>은 프로그래밍 언어로 
  	데이터 탐색, 시각화, 통계분석에 특히 강점이 있다. 
  	R을 사용하는데 <a href="https://www.rstudio.com/">RStudio</a>를 사용한다.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="r-windows">윈도우</h4>
      <a href="https://www.youtube.com/watch?v=q0PjTAylwoU">동영상 튜토리얼(Video Tutorial)</a>
      <p>
      	R을 설치하려면 <a href="https://cran.r-project.org/index.html">CRAN</a>에서 
      	<a href="https://cran.r-project.org/bin/windows/base/release.htm">.exe 파일</a>을 다운로드 
      	해서 실행한다.
      	또한, <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>도 
      	설치한다.
      	주의할 점은 사용자(user) 계정과 관리자(admin) 계정을 따로 갖고 있는 경우 
      	관리자(administrator)로 설치해야 한단. 관리자 설치방법은 더블클릭 대신에 .exe 파일 위에 우클릭하고 
      	"Run as administrator"를 선택하면 된다. 이렇게 설치하지 않게 되면 나중에 R 팩키지 설치단계에서 문제가 
      	발생한다.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-macosx">맥(macOS)</h4>
      <a href="https://www.youtube.com/watch?v=5-ly3kyxwEg">동영상 튜토리얼(Video Tutorial)</a>
      <p>
      	<a href="https://cran.r-project.org/index.html">CRAN</a> 웹사이트에서 
      	<a href="https://cran.r-project.org/bin/macosx/R-latest.pkg">.pkg 파일</a>을 
      	다운로드 해서 실행한다.
      	또한, <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>도 
      	설치한다.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-linux">리눅스(Linux)</h4>
      <p>
      	<a href="https://cran.r-project.org/index.html">CRAN</a>에서 해당 배포판에 적합한 
      	바이너리 파일을 다운로드 하거나,
      	팩키지 관리자를 사용한다. 예를 들어 데비안/우분투 배포판의 경우 
      	<code>sudo apt-get install r-base</code>, 페도라의 경우 <code>sudo dnf install R</code>
      	명령어를 실행한다.
      	또한, <a href="https://www.rstudio.com/products/rstudio/download/#download">RStudio IDE</a>도 
      	설치한다.
      </p>
    </div>
  </div>
</div> {% comment %} End of 'R' section. {% endcomment %}

<div id="sql"> {% comment %} Start of 'SQLite' section. {% endcomment %}
  <h3>SQLite</h3>

  <p>
  	SQL은 데이터베이스와 함께 사용하는 특수한 프로그래밍 언어다.
  	워크샵에서 <a href="https://www.sqlite.org/">SQLite</a>라는 단순한 데이터베이스 관리자를 사용한다.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="sql-windows">윈도우</h4>
      <p>
        <a href="https://www.sqlite.org/download.html">
          {% if page.carpentry == "swc" %}
          Software Carpentry
          {% elsif page.carpentry == "dc" %}
          Data Carpentry
          {% elsif page.carpentry == "lc" %}
          Library Carpentry
          {% endif %}
          윈도우 설치자(Windows Installer)
	</a>
	    를 통해 윈도우용 SQLite를 설치한다.
	    나노(nano) 편집기 환경설정하는데 설치자를 사용했다면, 다시 실행할 필요는 없다.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="sql-macosx">맥(macOS)</h4>
      <p>
      	맥OS의 경우 SQLite는 사전 설치되어 있다.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="sql-linux">리눅스</h4>
      <p>
        리눅스의 경우 SQLite는 사전 설치되어 있다.
      </p>
    </div>
  </div>

  <p><strong>아나콘다를 설치한 경우, <a href="https://github.com/ContinuumIO/anaconda-issues/issues/307"><code>readline</code>지원 안 되는</a>
  	SQLite 사본이 함께 설치되는데, 필요한 경우 강사가 회피하는 법(workround)을 알려줄 것이다.</strong></p>
</div> {% comment %} End of 'SQLite' section. {% endcomment %}

<div id="openrefine"> {% comment %} Start of 'OpenRefine' section. {% endcomment %}
  <h3>OpenRefine</h3>
  <p>
    For this lesson you will need <em>OpenRefine</em> and a
    web browser. <em>Note:</em> this is a Java program that runs on your machine (not in the cloud).
    It runs inside a web browser, but no web connection is needed.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="openrefine-windows">Windows</h4>
      <p>
        Check that you have either the Firefox or the Chrome browser installed and set as your default browser.
        <strong>OpenRefine runs in your default browser.</strong>
        It will not run correctly in Internet Explorer.
      </p>
      <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a></p>
      <p>Create a new directory called OpenRefine.</p>
      <p>Unzip the downloaded file into the OpenRefine directory by right-clicking and selecting "Extract ...". </p>
      <p>Go to your newly created OpenRefine directory.</p>
      <p>Launch OpenRefine by clicking <code>google-refine.exe</code> (this will launch a command prompt window, but you can ignore that - just wait for OpenRefine to open in the browser).</p>
      <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="openrefine-mac">Mac</h4>
      <p>Check that you have either the Firefox or the Chrome browser installed and set as your default browser. <strong>OpenRefine runs in your default browser.</strong> It may not run correctly in Safari.</p>
      <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a>.</p>
      <p>Create a new directory called OpenRefine.</p>
      <p>Unzip the downloaded file into the OpenRefine directory by double-clicking it.</p>
      <p>Go to your newly created OpenRefine directory.</p>
      <p>Launch OpenRefine by dragging the icon into the Applications folder.</p>
      <p>Use <code>Ctrl-click/Open ... </code> to launch it.</p>
      <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="openrefine-linux">Linux</h4>
      <p>Check that you have either the Firefox or the Chrome browser installed and set as your default browser. <strong>OpenRefine runs in your default browser.</strong></p>
      <p>Download software from <a href="http://openrefine.org/">http://openrefine.org/</a>.</p>
      <p>Make a directory called OpenRefine.</p>
      <p>Unzip the downloaded file into the OpenRefine directory.</p>
      <p>Go to your newly created OpenRefine directory.</p>
      <p>Launch OpenRefine by entering <code>./refine</code> into the terminal within the OpenRefine directory.</p>
      <p>If you are using a different browser, or if OpenRefine does not automatically open for you, point your browser at <a href="http://127.0.0.1:3333/">http://127.0.0.1:3333/</a> or <a href="http://localhost:3333">http://localhost:3333</a> to use the program.</p>
    </div>
  </div>
</div> {% comment %} End of 'OpenRefine' section. {% endcomment %}

{% comment %}
<div id="vm">
  <h3>Virtual Machine</h3>

  <p>
    Some instructors prefer to have learners use a virtual machine (VM)
    rather than install software on their own computers.  If your
    instructors have chosen to do this, please:
  </p>
  <ol>
    <li>
      Install <a href="https://www.virtualbox.org/">VirtualBox</a>.
    </li>
    <li>
      Download our <a href="{{site.swc_vm}}">VM image</a>.
      <strong>Warning:</strong> this file is 1.7 GByte, so please
      download it <em>before</em> coming to your workshop.
    </li>
    <li>
      Load the VM into VirtualBox by selecting "Import Appliance" and
      loading the <code>.ova</code> file.
    </li>
  </ol>
</div>
{% endcomment %}
