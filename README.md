1. Lab 구현 내용
- Lab1 : useState를 사용하여 타이머 관리, useEffect 사용하여 숫자가 1초마다 증가하도록 구현 ,setInterval로 타이머 실행, Cleanup함수에서 cleaarInterval을 호출하여 타이머 정리
- Lab2 : start버튼을 누리면 타이머가 시작, stop버튼을 누르면 정지, reset버튼을 누르면 타이머가 정지되고 숫자가 0으로 초기화
- Lab3 : focus버튼을 누르면 입력창에 커서가 이동, clear버튼을 누르면 입력된 내용이 삭제되고 다시 입력창에 포커스가 이동
- Lab4 : start,stop,reset버튼 구현

2. Lab 비교 분석
useEffect의 Dependency Array가 필요한 이유는?
- Dependency Array는 useEffect가 언제 실행될지 결정
- 빈 배열을 사용하면 컴포넌트가 처음 화면에 나타날때 실행되고 특정값을 넣으면 해당값이 변경될때 다시 실행
Cleanup을 사용하지 않으면 어떤 문제가 발생할 수 있는가?
- 컴포넌트가 화면에서 사라진 후에도 타이머가 계속 실행될 수 있다
useState와 useRef의 가장 중요한 차이는?
- useState는 값이 변경되면 화면을 다시 렌더링하는 반면 useRef는 current값이 변경되어도 화면을 다시 렌더링하지 않음
LAB 2와 LAB 4의 Timer 관리 방식은 어떻게 다른가?
- LAB 2는 useEffect와 running 상태를 이용해 타이머의 실행과 정지를 관리하는 반면 LAB 4는 useRef에 타이머 ID를 직접 저장하고 관리

3. 프로젝트 customizing
- 디자인 변경 : 프로젝트 제목과 설정 변경, 전체 배경색 변경, LAB 메뉴의 모서리와 색상 변경 등

- 추가 기능 구현 : 타이머 실행 상태 표시, 타이머 숫자를 초 단위에서 분:초 형식으로 변경

4. 배포 및 저장소
- Vercel 배포 주소 : https://week12-starter-project-rust.vercel.app/
- GitHub URL: https://github.com/2026-2-OSS/assign12-c01-22500323.git
- GitHub URL(개인): https://github.com/22500323-cloud/week12_starter_project.git

5. 새롭게 배운 점
- useEffect를 활용하여 타이머와 같은 부수 효과를 관리하는 방법
- Cleanup이 필요한 이유와 setInterval을 정리하는 방법
- useRef를 활용하여 DOM 요소에 접근하고 타이머 ID를 저장하는 방법

6. 어려웠던 점과 해결 방법
처음에는 setInterval과 cleanup이 어떻게 연결되는지 이해하기 어려웠다. 직접 타이머를 구현하고 start, stop, reset 기능을 테스트 해보면서 동작 원리를 이해할 수 있었다. 또 타이머 숫자를 분과 초로 표시하는 과정에서 숫자가 올바르게 출력되지 않는 문제가 있었다. Math.floor(), 나머지 연산자(%), padStart()를 활용하여 해결했다.

7. AI활용내역
- AI를 활용하여 React Hook의 개념을 이해하고 코드 구현 과정에서 발생한 오류 해결, CSS디자인 개선과 추가 기능 구현에 도움을 받음

8. 이해도 확인 질문
1. `setCount(prev => prev + 1)`은 왜 유용한가?
- 이전 상태값을 기준으로 1씩 증가시키기 때문에 최신값을 안전하게 사용할 수 있다. 
2. `useEffect(fn, [])`과 `useEffect(fn)`은 어떻게 다른가?
- useEffect(fn, []) : 처음 화면에 나타날떄 실행되고, useEffect(fn) : 컴포넌트가 렌더링 될때마다 실행된다.
3. Cleanup은 언제 실행되는가? 개발 환경 StrictMode 영향은?
- Cleanup은 컴포넌트가 사라지거나 Effect가 다시 실행되기 전에 실행된고 StrictMode는 문제가 없는지 확인한다.
4. `useState`와 `useRef`의 값 변경 시 렌더링 차이는?
- useState : 값이 바뀌면 화면에 다시 렌더링 되고 useRef : 값이 바껴도 화면이 다시 렌더링 되지 않는다
5. LAB 2와 LAB 4에서 Timer를 관리하는 방식의 차이는?
- LAB 2는 running 상태와 useEffect를 이용해 타이머를 관리하고 LAB 4는 useRef에 타이머 ID를 저장해 직접 관리한다. 