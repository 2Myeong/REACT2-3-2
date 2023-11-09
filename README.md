# 이명규 201930121

## 23.11.09


## 13주차 23.05.25

### <span style="color:yellow" >14장- 컨텍스트 </span>
### <span style="color:green" >14.5 여러개의 컨텍스트 사용하기</span>
+ context_Provider 중첩사용
+ 두개 이상의 컨텍스트 값이 자주 함께 사용될 경우 모든 값을 한 번에 제공해 주는 별도의 render prop 컴포넌트를 직접 만드는 것을 고려

### UseContext
+ 함수형 컴포넌트에서 컨텍스트를 사용하기 위해 컴포넌트를 매번 consumer컴포넌트로 감싸주는 것보다 Hook 사용(7장)
### <span style="color:yellow" >15장- 스타일링 </span>


## 12주차 23.05.18
### <span style="color:yellow" >14장- 컨텍스트 </span>
+ 컨텍스트는 리액트 컴포넌트들 사이에서 데이트를 기존의 props를 통해 전달하는 방식 대신 컴포넌트 트리를 통해 곧바로 컴포넌트에 전달하는 새로운 방식을 제공
+ 어떤 컴포넌트에되 쉽게 데이터 접근 가능
+ 따로따로 props에 전달 대신 데이터를 필요로 하는 컴포넌트에 곧바로 전달 가능

+ 주로 로그인 여부 / 로그인 정보 / UI테마 등에 사용
+ props를 통해 데이터를 전달하는 기존 방식 = 실제 데이터를 사용하는 컴포넌트까지의 길이가 길어 복잡해짐 + 반복적 코드 재사용으로 비효율성, 가독성 하락 => 컨텍스트 사용시 해결가능
### <span style="color:green" >컨텍스트 사용하기 전 고려부분</span>
+ 컴포넌트와 컨텍스트가 연동되면 재사용성 떨어짐
+ 다른 레벨의 많은 컴포넌트가 데이터를 필요로 하는 경우 아니면 props 통한 데이터 절달 방식이 적합
### <span style="color:green" >컨텍스트API</span>
1. React createContext
    + 컨텍스트를 생성하기 위한 함수
    + 파라메타에는 기본값
    + 하위 컴포넌트에서는 가장 가까운 상위 레벨의 provider로부터 컨텍스트를 받게 되지만, 만일 Privider을 찾을 수 없다면 기본값 사용
2. Context Provider
    + context provider 컴포넌트로 하위 컴포넌트를 감싸주면 모든 하위 컴포넌트들의 데이터에 접근 가능
    + Provider 컴포넌트는 value라는 props => 이 props 가 하위 컴포넌트(cousumer)에 전달
3. Class contextType
    + Provider 하위에 있는 클래스 컴포넌트에서 컨텍스트의 데이터에 접근하기 위해 사용
    + 더이상 사용 x 
4. Context Consumer
    + 함수형 컴포넌트에서 context consumer 을 사용하여 컨텍스트르 구독 가능
    + 컴포넌트의 지식으로 함수가 올 수 있는데 이것을 function as a child라 부름
    + Context consumer로 감싸면 자식으로 들어가는 함수가 현재 컨텍스트의 value을 받아 리액트 노트로 리턴
    + 함수로 전달되는 value = Provider의 vaule prop
5. Context displayName
    + 컨텍스트 객체는 displayName 이라는 문자열 속성 가짐

### <span style="color:yellow" >13장- 합성 </span>
+ 여러개의 컴포넌트 합쳐서 새로운 컴포넌트를 만드는것
1. Containment(담다, 포함하다, 격리하다)
    + 특정 컴포넌트가 하위 컴포넌트를 포함하는 형태의 합성방법
    + 컴포넌트에 따라서는 어떤 자식 엘리먼트가 들어올지 예상 가능
    + 범용적 박스 역할을 하는 Sidebar / Diolog 같은 컴포넌트에서 자주 확인
2. Specialization (특수화, 전문화)
    + 웰컴 다이얼로그는 특별한 케이스
    + 범욕적 개념을 구별이 되게 구체화하는 것을 특수화
    + 객체지향 언어에서는 상속을 사용하여 특수화를 구현
    + 리엑트 = 합성을 사용해 특수화 구현
3. Containment + Specialization 같이 사용



## 11주차 23.05.11
### <span style="color:yellow" >12장- state 끌어올리기 </span>
### <span style="color:green" >입력 컴포넌트 추출하기</span>
### <span style="color:green" ></span
+ 


## 10주차 23.05.04
### <span style="color:yellow" >10장- 리스트와 키 </span>
### <span style="color:green" >리스트와 키란 무엇인가 </span>
+ 리스트 = 변수나 객체 하나로 묶어 놓은 배열 / 키 = 각 객체나 아이템 구분 도와주는 고유 값
+ 리엑트에서 배열과 키를 사용하는 반복되는 다수의 엘리먼트를 쉽게 랜더랑 가능
### <span style="color:green" >다수의 컨포넌트 렌더링하기 </span>
+ 컨포넌트를 화면에 반복적으로 나타내야 할 경우 엘리먼트를 map() 함수를 이용해 랜더링
### <span style="color:green" >리스트와 키 </span>
+ 리스트에서의 키 = 아이템을 구별하는 고유 문자열
+ 리스트에서 아이템이 변경, 추가, 제거의 구분을 위해 사용
+ 키는 같은 리스트에 있는 엘리언트 사이에서만 교유한 값이면 됨

### <span style="color:yellow" >11장 - 폼 </span>
### <span style="color:green" >폼이란 </span>
+ 폼은 기본적 사용자로부터 입력을 받기 위한 양식에서 사용
### <span style="color:green" >제어 컨포넌트 </span>
+ 사용자가 입력한 값에 접근하고 제어할 수 있도록 해주는 컴포넌트 / 모든 데이터를 state에서 관리
### <span style="color:green" >textarea 태그 </span>
+ REACT에서는 state 를 통해 태그의 value라는 attribute를 변경하여 텍스트를 표시
### <span style="color:green">File input 태그 </span>
+ 그 값이 읽기 전용이므로 리엑트에서는 비제이 컴포넌트 됨







## 9주차 23.04.27
### <span style="color:yellow" >8장- 이벤트 핸들러 </span>
#### <span style="color:green">이벤트 핸들러 추가하는 방법 ? </span>
- 버튼 클릭 시 handleClick()함수 호출
- bind 사용x 시 this.handleClick은 글로벌 스코프에서 호출
- bind 시용하지 않기 위해서는 화살표 사용(p.250)
- 클래서형 => 함수형
     1. 함수 안에 함수로 정의
     2. row function을 사용해서 정의
- 함수형에서는 onClick에서 바로 handleClick을 넘기면 됨

#### <span style="color:green">Arguments 전달하기</span>
+ 함수 정의 시 Parameter / 매개변수, 사용 시는 Argument / 인자라 부름
+ 이벤트 핸들러에 매개변수 전달 하는 경우 多
+ event라는 매개변수 = react에서의 이벤트 객체 의미
+ p.254 이벤트 핸들러 매개변수 전달 참고

### <span style="color:yellow" >9장- 조건부 렌더링 </span>
#### <span style="color:green">조건부 렌더링이란?</span>
+ props로 받은 isLoggedIn 이 true이면 UserGreetind 을 , false면 GuestGreeting return => 이 같은 렌더링 = 조건부 랜더링
#### <span style="color:green">엘리멘트 변수</span>
+ 렌더링 해야할 컴포넌트를 변수처럼 사용한는 것 = 엘리멘탈 변수 (p.272 참고)
#### <span style="color:green">인라인 조건</span>
+ 필요한 곳에 직접 넣이 사용 방식
    1. 인라인if
        + if 사용x 하고 동일 효과을 내기 위해 &&논리연산자 사용
    2. 인라인 if-else
        + 삼항 연산자를 사용 조건문 ? 참일 경우 : 거짓일 경우
        + 문자열 혹은 엘리먼트를 넣어서 사용 가능
#### <span style="color:green">컨포넌트 렌더링 막기</span>
+ 랜더링하고 싶지 않을 때는 null 리턴하면 됨!


## 8주차 <중간고사>

## 7주차 23.04.13
### <span style="color:yellow" >7장- 훅 </span>
### 1. 훅
+ 클래스 컨포넌트에 생성자에서 state 정의, setState()함수=> state업데이트 / 함수형 컨포넌트 별도 state정의, 컨포넌트 생성주기 맞춰 어떤 코드 실행되도록 못함
+ 함수형 컨포넌트에서 state / 별도 생명주기 함수 기능 사용케 해주기 위해서 만들어진 기능 = <span style="color:red">HOOK</span>
+ 함수형 컨포넌트도 훅 사용 시 = 클래스 컴포넌트 기능 동일 사용 구현케 됨
+ useState = 함수형 컨포넌트에서 state을 사용할 수 있게 해주는 HOOK

#### useEffect 
+ 사이드 이펙트 수행
+ 부수적으로 다른 효과 있는 것! = 랜더링 외 실행 하는 부수적 코드
+ ex 네트워크 리퀘스트. DOM수동조작, 로깅
+ 첫 파라미터 = 이펙트 함수 , 두번째 파라미터 = 의존성 배열
        <br>useEffect(이펙트함수, 의존성배열);
#### useMemo
+ useMeMO() / Memoizde value 리턴
#### useCallback
#### useRef
+ 레퍼런스(특정 컨포넌트 접근 가능 객체)를 사용하기 위한 훅

### 2. 훅 규칙
+ 첫 규칙 = 최상의 레벨(최상위 컨포넌트) 에서만 호출해야한다
<br> 반복문 , 조건문에서 사용x
+ 두번째 규칙 = 리액트 함수형 컨포넌트에서만 호출해야한다
<br>일반 자바스크립트 사용x

## 6주차 23.04.06
### 컨포넌트 추출
+ 여려개 컨포넌트로 분리 가능
+ 부모 컨피포에서 일부 추출해서 새로운 컨포넌트 생성 가능
+ 1컨포 = 1 기능 이상적 기능
+ <span style="color:pink"> 나 자신의 프로필을 만드는 컨포넌트 생성  - index.js / chapter05 내용 추가</span>

### <span style="color:yellow" >6장</span>
### 1.State
+ 리액트 컨포넌트의 상태(컨포넌트의 데이터) 의미
+ 세부적으로는 변경 가능한 데이터
+ State가 변하면 다시 렌더링이 되므로 렌더링과 관련된 값만 state에 포함 시켜야함
+ 자바스크립트의 객체일 뿐!
+ 변경시 setstate() 사용

### 2. 셍명주기
+ 컴포넌트의 생성 시점 , 사용시점 , 종료 시점
+ constructor 실행 -> 컨포넌트 생성
+ 생성 직후 <span style="color:pink" >conpoentDidMount()</span> 함수 실행
+ 소멸 전까지 여러번 랜더링
+ 랜더링 = props, setState(), forceUpdate() 에 의해 상태 변경
+ 랜더링 이후 = <span style="color:pink" >componentDinUpdate()</span> 함수 호출
+ 마지막 컨포넌트 언마운트 시 = <span style="color:pink" >compomentWillUnmount()</span> 함수 호출



## 5주차 23.03.30
### 1. 엘리먼트
+ Elements are the smallest building blocks of React apps = 리액트 앱의 가장 작은 빌딩 블록
+ 리액트 엘리먼트 = DOM 엘리먼트 가상표현

### 2. 엘리머트 생김새
+ 객체 형태로 존재
+ 내부 모든 children(컴포넌트, 속성) 포함 일반 js 겍체
+ 불변성 = 엘리먼트 생성 후 children / attributes 변경 불가
+ 변경된 엘리먼트를 보여주려면 새로운 엘리먼트 생성 후 변경

### 3. 엘리먼트 렌더링하기
+ 리액트만으로 만들어진 모든 웹 사이트 하나의 Root DOM node 있음
+ 하지만 웹 사이트에 추가적 리액트 연동 = 다수의 Root DOM node 생성

### 4. (시계) 만들기

### 5. 컨포넌트
+ 리엑트 = 컨포넌트 기반 구조
+ 작은 컨포넌트 여려개 = 큰 컨포넌트 / 큰 컨포넌트 여려개 = 페이지 구성
+ 최근 => 함수형 컨포넌트 주 사용
+ 이름은 항상 대문자 시작 (소문자는 DOM태그로 인식하므로 x)


### 6. Props
+ property = 속성의미
+ 컨포넌트 속성 = Props
+ 어떤 Props를 사용하냐에 다른 엘리먼트 출력
+ 다양한 정보를 담고 있는 자바스크립트 객체
+ 읽기 전용 = 변경불가

### Pure / Impure 함수
+ Pure 함수 = 인수로 받은 정보가 함수 내부에서 변하지 않은 함수
+ Impure 함수 = 인수로 받은 정보가 함수 내부에서 변하는 함수



## 4주차 23.03.23
### 1.위치변경
+ README.md 백업
+ local 저장소 이름 변경/삭제
+ 새 프로젝트 생성 npx create-react-app 23-react1
+ README.md 덮어쓰기
+ GITHUB 저장소 삭제
+ 로컬에서 푸시
+ GITHUB 저장소 확인

### 2.JSX 특징
+ 객체 표현
    - Babel은 JSX를 호출로 컴파일
### 3.JSX 역할
+ 내부적으로 XML/HTML 코드 자바스크립트로 변환
+ REACT가 createElement 할경우 자동 자바스크립트 변환
+ 만일 JS 작엽할 경우 직접 createElement함수 자용해야 함
+ JSX는 가독성을 높여주는 역할

### 4. JSX의 장점
+ 코드 간결
+ 가독성 향상
+ injection Attack 이라는 해킹 방법 방어 탁월 > 보안 강함

### 5. JSX 사용법
+ 모든 자바스크립트 문법 지원
+ 자바스크립트 문법과 XML / HTML 문법 섞어서 사용
+ 아래 코드 2번 라인처럼 섞어 사용
+ HTML / XML 에 자바스크립트 코드 사용하고 싶으면 {} 괄호 사용
+ 태그 속성값을 넣을 때는 
    - 큰따음표 사이 문자열 넣기
    - 중괄호 사이 자바스크립트 코드 넣기
## 3주차 23.03.16
### 1. 개발 툴 설치 및 유지
+ chocolatey.org 에서 Find package에서 검색 및 설치 
### 2. node.js / npm 설치
+ node.js -> LTS 버젼 설치 -> default으로 진행

+ <node.js 버젼 확인>
    - node --version
    - node -v
+ <npm 버젼 확인>
    - npm -v
    - npm --version

### 3. 리엑트의 정의

+ A JavaScript library for building user interfaces - 사용자 인터페이스를 만들기 위한 자바스크립트 라이브러리

+ 리엑트의 개념 정리 : 
    - 복잡한 시아트 쉽게 구축 및 관리 = SPA를 쉽고 빠르게 만들수 있게 해주는 도구
### 4. 리엑트의 장점

+ < 빠른 업데이트 , 랜더링 속도 >
    - DOM(Document Object Model) - HTML, XML 문서를 계층으로 표현해 생성, 변형, 삭제 돕는 인터페이스 (W3C 표준)
    -Virtual DOM은 DOM 조작이 비효율적인 이유로 속도 감소때문에 고안 방법
    - DOM은 동기식, Virtual DOM은 비동기식 방법으로 랜더링

+ < 컴포넌트 기반 구조 >
    - 모든페이지 컴포넌트 기반 구조   
    - 하나의 컨포넌트 = 다른 여러 컴포넌트 조합 구성 가능
    - react 유명한 사이트 - '에어비엔비' 참고

+  <재사용성 >
    - 반복적 작업 감소 = 생산성 증가
    - 유지보수 용이
    - 재사용 가능 여부는 해당 모듈 의존성 없어야 함

+ <대기업 관리>
    - 메타에서 오픈소스 프로젝트로 관리

+ 지식 공유 / 커뮤니티 발달

+ < 모바일 앱 개발가능 >
    -리엑트 네이티브(모바일 환경 UI프레임워크) 사용 시 크로스 플랫폼 모바일 앱 개발 가능

### 4. 단점
+ < 방대한 학습량 >
    - 하지만 자바스크립트 공부 시 빠르게 학습 가능
+ < 높은 상태 관리 복잡도 >
    - state(클래스형 컨포넌트), life cycle(클래스형 컨포넌트) 등 개념이 있음


#### 실습 2.4
    
## 2주차 23.03.09

### 1. github 연결
+ git config --global user.name "Your Name" / 이름 
+ git config --global user.email "Your Email" / 이메일


## 1주차 23.03.02

###