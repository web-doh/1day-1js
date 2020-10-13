# 1D-1JS
# 1Day 1JS challenge(with Wes Bos)

## 기간 (8월21일~ , 주말은 제외~!)
  - Vanilla JS 연습 (site에서 제공하는 기본 템플릿을 바탕으로 JS, CSS 파일 수정)
  
  - Day 폴더 내 wesbos 폴더 - 'index-FINISHED.html' 파일: 'wesbos의 솔루션' 
  - Day 폴더 내 wesbos 폴더 - 'index-START.html'파일: 기본 템플릿
  - Day 폴더 안에 있는 파일들: 직접 작성 또는 수정한 파일

## Day1: Drum-kit (20/08/21)
  ### function
  - 키보드를 누르면 드럼 사운드 on

  ### wesbos의 솔루션
  1. keydown 이벤트로 눌러진 keycode와 동일한 key값을 가진 audio 실행
    (add classList로 스타일도 변경)
  2. forEach 문으로 transition이 끝나는 key에서 removeTransition 

  ### 개선방향
  1. transitionend 이벤트에 forEach 대신 event delegation 사용 (성능 개선)
  2. playSound()로 묶여진 함수를 playSound & addTransition로 분리 (더 명확하게 인지)

## Day2: Clock (20/08/24)
  ### function
  - 아날로그 시계로 현재 시각 보여주기 

  ### wesbos의 솔루션
  1. setInterval을 사용하여 초침,분침,시침(position-absolute)을 1초마다 rotate
     - new Date().get api를 이용하여 각도 계산 

  ### 개선방향
  1. 배경화면 랜덤 변경 함수 추가 (DOMContentLoaded, Math)
  2. Styling customize

## Day3: CSS Variables (20/08/25)
  ### function
  - input(type ="range") 슬라이드 조절시 css styling 요소가 사이트에 바로바로 변경 적용
  - 사이트 내 이미지의 blur, padding, base color(border) 변경

  ### wesbos의 솔루션
  1. HTML input 안의 name과 CSS 내 :root요소 이름 동일하게 설정 
     -> document.documentElement로 css 파일내 :root 요소 변경 
     - HTML: input에 data-sizing 추가해서 range의 value 값에 unit 적용 
  2. input 요소들에 forEach 문으로 change, mousemove 이벤트 핸들

  ### 개선방향
  1. text가 있는 사이트의 전체적인 변화를 볼 수 있도록 input 조절 요소 변경 
  - 제목과 본문 각각의 font-size, 본문 뒤 배경색의 opacity, base color, highlight color 변경
  2. Styling customize 

## Day4: Array Cardio-1 (20/08/26)
  ### function
  - array의 api 사용 능력 향상을 위한 훈련! 
  - filter(), map(), sort(), reduce()

## Day5: Flex panel gallery (20/08/27)
   ### function
   - panel 클릭할 때마다 classList.toggle 되어 펼쳐졌다가 접었다 하기 

   ### wesbos의 솔루션
   1. forEach 문으로 click,transitionend 이벤트 추가 
      1) panel click -> panel open
      2) panel open -> flex 관련 스타일 변경(transitionend) -> sub-text 보이는 애니메이션 효과 

   ### 개선방향
   1. 다른 panel 클릭 -> 기존에 open 되어있던 panel은 닫히도록 변경 
      => filter로 열려있는 panel list 반환 
          -> open 돼있던 panel은 closing(classList.remove) 
   2. Styling customize 
   
## Day6: Type ahead (20/09/03)
   ### function
   ### wesbos의 솔루션
   ### 개선방향

## Day7: Array Cardio-2 (20/08/31)
  ### function
  - array의 api 사용 능력 향상을 위한 훈련! 
  - some(), every(), find(), findIndex()

## Day8: Fun with HTML Canvas (20/09/01)
   ### function
   ### wesbos의 솔루션
   ### 개선방향

## Day9: Dev tool (20/09/02)
  ### function
  - 개발자 도구 console 창 배우기
  - log, 문자열 치환, warn, error, info, assert(testing), 
    clear, dir(Viewing DOM Elements -> properties)
    grouping(groupCollapsed & groupEnd), count

## Day10: Hold shift & Checkbox (20/09/04)
  ### function
  - shift key를 누르고 체크박스 다중 선택시, 사이에 있는 체크박스들도 함께 체크

  ### wesbos의 솔루션
  1. checkbox 누르면, lastChecked에 어떤 checkbox인지 저장
  2. check && shiftKey를 누른 상태이면, forEach 루프로 inBetween(boolean)값 변경
  3. inBetween(true)인 체크 박스 모두 체크 상태로 변경

  ### 개선방향 
  1. forEach 대신 event delegation 사용 (=> 결과 : 성능이 저하됨ㅠ)
  2. 맨 처음에 shiftkey 누르고 클릭하면, 클릭한 박스 밑으로 모두 체크됨 
      => shift && checked 된 체크박스 index 받기 
         index 값이 모두 양수인 경우(두 개 이상이 선택된 경우)만
          -> 중간 체크박스가 checked 상태로 변경하도록 수정 

## Day11:Custom Video Player (20/09/08 - 20/09/09)
  ### function
  - 비디오 플레이어 조작 기능 커스텀 
  
  ### wesbos의 솔루션 
  1. 비디오 재생 조작 : play-btn 클릭,비디오 재생 등의 event 실행시 togglePlay,updateButton 함수 작동 
  2. 비디오 재생 시간 표시 : 비디오 timeupdate event 실행시 handleProgress 함수(비디오 기본 속성 - video.currentTime,video.duration 이용) 작동
  3. 비디오 재생 시간 조작 : slider 조작시 scrub(속성 - e.offsetX,progress.offsetWidth,video.duration 이용), skip(video.currentTime 이용) 작동
 
  ### 개선방향 
  1. volume 버튼 클릭시 mute 기능 추가 (mutedControl,updateVolBtn)
  2. playbackRate 조작시 현재 몇 배속으로 재생 중인지 display
  3. 영상 description 추가하여 재생되는 동영상 시간 display (displayPlayTime)

## Day12: Key Sequence Detect (20/09/07)
  ### function
  - 설정해놓은 secret code와 사용자가 누른 연속된 키보드 키가 동일한 경우,
    로그 창: 성공 메세지 + 스크린: 
  ### wesbos의 솔루션 
  1. pressed keyboard를 array(pressed)로 받기 
  2. splice로 secret code의 길이를 넘지 않게 array(pressed) 길이 조절
  3. join으로 text화하여 code와 pressed 문구 비교 후
     정답일 경우 - console 창으로 정답 축하 문자
                - add cornify ~ !
  ### 개선방향 
  1. 처음 페이지에 들어가면 빈 화면이라서 사용자가 뭘 해야하는지 알 수 없음 
      => 힌트 제공! (1. code : rainbow -> color 힌트!
                    2. code : month 뒤집기(ex- yaM, tsuguA) -> 뒤집힌 text 힌트!)
  2. 대문자, 소문자 구분 없이 정답이 될 수 있게 REGEXP 이용                  
  3. 답을 맞추면 나오는 로그 문자 ding dong 이 눈에 잘 띄지 않음 
      => 로그 창에 스타일 입히기 


## Day13: Slide in OnScroll (20/09/14)
  ### function
  - 스크롤을 내리거나 올릴 때, 이미지가 fade-in 되는 효과
  - scroll 이벤트가 될 때마다 컴퓨터가 작업 처리할 경우 발생하는 낭비 처리

  ### wesbos의 솔루션
  1. function checkSlide: window에 scroll 이벤트를 등록하여, 일정 위치만큼 스크롤되면 이미지가 보이도록 처리
     1) 일정 위치 계산 : img의 offsetTop,height 등 / window의 scrollY,innerHeight
     2) 값 비교 : img와 window의 속성 비교(조건문)에 따라 classList 추가 or 삭제
  2. function debounce: scroll 이벤트가 일어나도 일정 시간 간격으로만 func 작동
     - setTimeout, apply() 등 

## Day14: JS refence vs copy (20/09/10)
  ### summary
  - reference 타입과 primitive 타입 비교
  - index 파일내 정리 
    
## Day15: LocalStorage (20/09/17)
  ### function
  - 브라우저를 재접속해도 기존에 입력한 값들이 그대로 유지 

  ### wesbos의 솔루션 
  1. localStorage에 값 저장
  2. event delegation으로 checkbox 선택 

  ### 개선방향
  1. checkbox 클릭시 한번에 선택 혹은 해제되는 기능 추가
     - checkbox에 click 이벤트 실행되면, 조건문으로 checkbox 상태 확인 후 forEach문 활용하여 전체 check or 해제
  2. 목록 삭제 기능 추가
     - 전체 삭제 시, localStorage.clear() 
     - 부분 삭제 시, localStorage.removeItem(key)

## Day16: Mousemove shadow (20/09/11)
  ### function
  - 마우스가 움직이는 정도에 따라 그림자 4개가 각각 다른 방향으로 움직이기

  ### wesbos의 솔루션 
  1. text가 담긴 컨테이너의 offsetWidth,offsetHeight를 받기 
  2. 마우스가 움직이는 offsetX,offsetY 값 측정 
     - container 내의 text에 마우스가 올라간 경우, offset의 기준이 text가 됨 
        -> e.target.offsetLeft,offsetTop을 이용하여 offset의 기준을 container로 조정
  3. 그림자 4개가 동일한 규칙 내에서 서로 다른 방향으로 움직일 수 있도록 px값 설정
     - 위에서 구한 측정값들로 그림자가 이동할 위치 지정 
 
  ### 향후 사용 방법
  1. 홈페이지 title에 효과를 주고 싶을 떄
     (그림자 위치가 마우스 방향에 맞춰 살짝 바뀌는 정도로 응용 가능할 듯) 

## Day17: Sort without Articles (20/09/15)
  ### function
  - html 파일에 적지 않고, JS로 영화 목록을 알파벳 순서로 나열 후 display

  ### wesbos의 솔루션 
  1. 영화 목록 array 형태로 저장
  2. replace().trim(): 정규표현식으로 제목 맨 앞 단어가 'a, an, the'인 경우 삭제
  3. 알파벳 순으로 sort()한 뒤, map()이용하여 각각의 제목을 li 태그로 변경 -> join()으로 텍스트화
  4. innerHTML을 이용하여 ul 태그에 li태그 삽입 

  ### 향후 사용 방법
  - 동적인 리스트 생성시 사용 (데이터를 JS 파일에 분리하여 관리)

## Day18: Adding up times with reduce (20/09/16)
   ### function
   - 목록에 포함된 비디오의 재생시간의 총합 구하기
   
   ### wesbos의 솔루션
   1. video list -> map(): dataset.time에 저장된 데이터 배열 반환
                 -> map()(split & map(parseFloat)): 'mins:secs' (string) 데이터를 secs(float) 데이터로 변환하여 새 배열 반환
   2. total time: reduce() -> 총 재생시간(secs) 반환
   3. Math.floor와 %,/ 연산자를 이용하여 총 재생시간을 h,m,s로 변환

   ### 개선방향 
   1. video list에서 video를 삭제 혹은 삭제 취소가 가능하도록 
      => classList.toggle('remove__list') -> filter(): classList에 remove__list가 포함된 경우 계산에서 제외 
   2. calculate 버튼 추가하여, 리스트 변경되어도 재계산이 가능하도록
      => addEventListener('click') 등록 
   3. 화면에 각각의 비디오 재생시간과 총 합계가 표시되지 않음 
      => textContent 속성 이용하여 display 되도록  
   
## Day19

## Day20: Speech Recognition (20/09/18)
   ### function
   - 음성 인식해서 화면에 텍스트로 나타내는 기능 만들기 
   
   ### wesbos의 솔루션
   - SpeechRecognition의 속성, 이벤트, 메서드를 이용
   1. SpeechRecognition의 새로운 object를 생성
   2. 'result' 이벤트가 실행되면, 마이크로 인식한 음성을 텍스트로 변환하기
      - event의 results 속성으로 데이터를 받아와 map()을 이용하여 transcript 속성만 분리
      -> join(): arr 형태의 결과값을 string으로 변경 
      -> replace(regex,word): 똥과 관련된 단어를 이모티콘으로 순화
  3. createElement와 append 속성을 이용하여 텍스트 화면에 display
  4. html: 텍스트를 받아오는 div 박스에 contenteditable 속성 추가하여 오타 직접 수정할 수 있도록

  ### 개선방향
  1. 영어로 설정된 언어를 한국어로 변경 (recognition.lang = 'ko-KR';)
  2. wesbos의 솔루션 중 2,3번의 기능(원래 addEventListener에 바로 등록)을 함수(audioTrans)로 분리하여 가독성 높이기
  3. 화면에서 글자가 넘칠 때, 현재 실행 중인 텍스트에 포커스되도록 -> scrollIntoView() 추가
  4. css styling : 폰에서 음성인식 프로그램에 말 거는 것처럼 디자인 변경  

## Day21: Geolocation (20/09/21)
   ### function
   - 방향 인식해서 나침반으로 표현하기
   
   ### wesbos의 솔루션
   1. geolocation의 API 중 watchPosition을 사용 -> 장치의 위치가 바뀔 때마다 자동으로 새로운 위치를 받아와 콜백함수 처리
   2. 받아온 data 중 coord.speed와 coords.heading 속성 -> 기계의 속도 값과 나침반 방향을 수정

   ### 향후 사용 방법
   -모바일 나침반 혹은 속도 측정 어플 

## Day22: Follow Along Link Highlighter (20/09/22)
   ### function
   - 마우스가 hyperlink 걸린 단어 위에 올라가면 단어가 highlight!  

   ### wesbos의 솔루션
   1. createElement로 하이라이트 색상이 적용될 span 컨테이너('.highlight')를 생성
   2. addEventListener로 'mouseenter' 이벤트가 진행되면 highlightLink 함수가 실행되도록 설정
      -> a 태그 전체에 forEach문으로 등록 
   3. getBoundingClientRect()로 이벤트가 발생된 하이퍼링크 텍스트의 위치, 크기 등의 속성을 가져옴
   4. '.highlight'가 이벤트 발생 위치로 이동하도록 3번에서 얻은 속성을 이용하여 position 설정  

   ### 개선방향
   1. 이벤트 등록시 forEach문 대신 event delegation 사용 
      -> parent node에 이벤트 등록 후, a tag 선택시에만 이벤트 함수 실행 
   2. highlight 될 때, 글자 색상도 변경하도록 
      -> classList.add('a_font') : 폰트 색상 변경 
      -> classList.remove('a_font') : 다음 이벤트 발생 시, 다른 텍스트에 'a-font' 클래스가 적용되어 있다면 삭제
   3. Styling customize (디자인 변경 및 media query 추가 -> 반응형)
   
   - highlighter가 이리저리 옮겨지는 애니메이션 효과를 원하지 않는다면, 
     span 컨테이너를 추가로 만들지 않고, 선택된 a tag에 classList를 추가하거나 삭제하는 방식이 더 간단하기도..!

## Day23: Speech synthesis (20/09/25)
   ### function
   - 원하는 텍스트를 적은 뒤, 목소리,속도,음을 선택하면 컴퓨터가 읽어주는 기능 

   ### wesbos의 솔루션
   1. speechSynthesis: 음성서비스 컨트롤(pause, speak 관련)
      - 'voiceschanged' 이벤트 실행시, getVoice() 
        -> 받아온 voice list 중 원하는 언어만 filter 
        -> option창에 전달(map,join)
      - cancel() & speak(): stop 혹은 speak 버튼 클릭시, 음성 재생 혹은 정지 
   2. SpeechSynthesisUtterance(): 음성 설정 변경(voice,pitch 등과 관련)
      - 조절하고자 하는 pitch, rate, text를 한번에 option으로 묶은 후, forEach문에 'change' 이벤트 리스너 등록 
        -> 변경된 value값 받아와서 instance의 프로퍼티 값으로 설정해줌
      - voice 도 유사한 방식으로 'change' 이벤트 리스너 등록

   ### 개선방향
   1. 초기 voice option 선택창에 'select a voice'문구가 먼저 보이도록 변경
      - voiceDropdown.innerHTML = voiceList; => voiceDropdown.innerHTML += voiceList; 
   2. range 값이나 text 창 변경되어도 바로 음성 재생되지 않고, speak 눌러야만 재생되도록 변경 

## Day24: Sticky Nav (20/09/23-24)
   ### function
   - 스크롤해서 Navigation bar가 스크린 최상단으로 가면 최상단에 그대로 고정

   ### wesbos의 솔루션
   1. CSS - logo: overflow - hidden, max-width - 0으로 설정하여 스크린에서 보이지 않도록
   2. 윈도우에 스크롤되면 body에 'fixed' class가 부여
      -> 윈도우에서 y축으로 스크롤된 수치가 navbar의 offsetTop 값보다 커질 경우, body 태그의 classList에 'fixed' 추가 
         1) navbar의 CSS : position - fixed, logo의 max-width - 500px 설정
         2) body의 style : padding-top - navbar의 높이만큼 떨어지도록 설정                    
      -> 반대인 경우, classList에서 'fixed' 제거
       
   ### 개선방향 
   1. 직관적으로 이해하기 편하도록, body태그 대신 navbar에 'fixed' class 추가 
   2. Styling customize
      - 디자인 변경 및 media query 추가(크기 단위: rem 사용)
      - Day16에서 진행했던 '마우스 움직이면 그림자 위치 이동' 방법을 메인 타이틀에 추가 적용 

## Day25: Event Capture, Propagation, Bubbling and Once (20/09/24)
   ### summary
  - Event Propagation: bubbling 과 capturing 이해
  - addEventListener의 capture, once 옵션 이해
  - if (e.target !== e.currentTarget) return 구문과 stopPropagation() 차이 이해 

## Day26: Stripe Follow Along Nav (20/10/05)
   ### function
   - nav 메뉴에 마우스 올라갈 경우, 하단 드롭 메뉴 보이기

   ### wesbos의 솔루션
   1. nav 메뉴에 addEventListener를 등록하여 mouse가 올라간 경우, 
      - classList를 add : 하단 드롭 메뉴 display: none -> display: block & opacity: 0 -> opacity: 1
   2. mouse가 nav 메뉴에서 벗어난 경우,
      - classList를 remove  
   3. 하단 드롭 메뉴의 background는 따로 div 태그로 분리
      - 하단 드롭 메뉴와 nav 바 자체의 getBoundingClientRect() 속성을 이용하여 background의 크기 및 위치 지정 
   
   ### 개선방향
   1. Styling customize
      - 디자인 변경 

## Day27: Click and Drag (20/10/07)
   ### function
   - 마우스로 이미지를 잡고 움직이면, 이미지가 x축으로 스크롤

   ### wesbos의 솔루션
   1. items에 mousedown 이벤트 발생한 경우, 
      - 변수에 마우스가 클릭된 상태라는 것을 저장
      - 브라우저에서 현재 마우스가 클릭된 지점의 x 좌표와 scrollbar가 x축으로 얼만큼 움직였는지 변수에 저장
      - items classList에 'active' 추가 (css style - cursor 스타일 및 scale 변경)
   2. items에 mouseleave과 mouseup 이벤트가 발생한 경우,
      - 변수에 마우스가 클릭되지 않은 상태임을 저장
      - items classList에서 'active' 제거  
   3. items에 mousemove 이벤트가 발생한 경우,
      - 마우스가 클릭되지 않은 상태이면 return
      - default event 방지 
      - 스크롤할 크기 : 마우스가 x축으로 움직인 위치와 1에서 구한 x좌표의 차이를 계산 (얼만큼 휘리릭 넘길 것인지 배수로 지정)
      - items의 scrollLeft: 1에서 구한 scrollLeft와 스크롤할 크기의 차이를 계산

   ### 개선방향
   1. addEventListener에 직접 설정하지 않고, function으로 분리 
      -> 중복 작성 방지, readable
   2. Styling customize
      - 디자인 변경 

   ### 향후 사용 방법
      - 이미지 갤러리나 음원사이트에서 최신 앨범 소개할 때 등 

## Day28: Video Speed Controller (20/10/06)
   ### function
   - 동영상과 분리된 bar를 이용하여 동영상 재생속도를 조절
   
   ### wesbos의 솔루션
   1. bar 위에서 마우스가 움직('mousemove')이면 이벤트 발생, function 실행 
   2. function 
      - event 발생 지점의 pageY와 bar의 offsetTop, offsetHeight 속성: 현재 마우스 위치가 전체 bar에서 어느 정도 비율을 차지 하는지 계산 
      - 위에서 계산한 비율과 사용자가 지정한 최대 및 최소 재생속도를 이용하여, playbackRate 산출
      - video.playbackRate 속성을 이용하여 재생속도 조절
                  
   ### 개선방향 
   1. 비율 계산시, (e.pageY - this.offsetTop)는 직관적 X -> e.offsetY 속성만 이용하여 계산
   2. bar에 이벤트 등록시, 마우스가 올라가서 움직일때마다 속도 변경돼서 조절 어려움 -> 'mousedown' 으로 변경하여 이벤트 적용!
   3. main title에 gradient 적용 (background에 그라디언트 지정 후, -webkit-background-clip: text; -webkit-text-fill-color: transparent; 설정) 

## Day29: Countdown Timer (20/10/12-13)
   ### function
   - 설정된 시간이 적혀있는 버튼을 누르거나 입력창에 시간을 입력할 경우, 타이머가 시작되는 기능

   ### wesbos의 솔루션
   1. button에 click event 발생시, 타이머 시작 함수(startTimer()) 실행
   2. setInterval API: 
      - seconds --; 와 같이 숫자를 직접 1씩 차감하는 경우, 스크롤링하거나 브라우저가 멈추는 경우 등 작동이 안될 떄 에러 발생
        -> Date.now()와 타이머 설정 시간을 이용하여, 매초마다 남은 시간을 계산해서 보여주는 방법이 나음 
      - setInterval 실행 시, 즉시 실행 x -> 실행 전에 설정 시간 display 지정
   3. 설정 시간 display: displayTimeLeft()
      -  html 버튼 태그에 dataset으로 시간 속성 지정 후, textContent 이용하여 display 
      - setInterval 실행할 때마다 displayTimeLeft(seconds) 실행
   4. 타이머가 끝나는 시각 display : displayEndTime()
      - new Date() & getHours(),getMinutes() 이용
   5. form에 submit event 발생시, 
      - preventDefault()로 기본 제출 이벤트 방지
      - input창에 입력된 value 값 받아와서 시간 설정 후, timer 실행

   ### 개선방향 
   1. 타이머가 끝나면 알람소리가 들리도록 설정 : Audio.play(),pause()
   2. stop 버튼 추가 : stopTimer() 함수 추가 
      - 타이머 작동할 때 stop 버튼 클릭시, timer 정지, restart 버튼으로 변경 
      - restart 버튼 클릭시, timer 재시작 (endTime 재설정) 
   3. form 태그에 submit 이벤트 등록할 떄, 함수를 따로 작성하여 가독성 up!
   4. input 작성 후 기록 남지 않도록, html에 'autocomplete=off' 추가

## Day30
