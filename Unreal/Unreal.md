# Unreal(4.23.1 기준)

## Unreal tip

### Material Editor 단축키

* 노드의 핀을 Alt + 마우스 좌클릭 - 연결 해제

### Blueprint 단축키

* Home - 줌레벨 선택에 맞춤
* PageUp - 부모 Graph로 이동
* PageDown - 자식 Graph로 이동
* Ctrl + B - Content Browser 찾기
* Ctrl + Y - 다시하기
* Ctrl + Shift + F - 모든 blueprint에서 찾기
* F7 - blueprint compile
* 연결된 노드의 핀에 Ctrl + 마우스 좌클릭 + 드래그 - 해당 핀에 wire을 전부 이동
* 노드 포커싱 상태 + F9 - breakpoint 설정
* Ctrl + Shift + F9 - 모든 breakpoint 삭제
* Ctrl + W - 선택 복제
* C - 선택 주변에 Comment 추가
* B + 좌클릭 - branch node 생성
* D + 좌클릭 - Delay node 생성
* S + 좌클릭 - Squence node 생성
* G + 좌클릭 - Gate node 생성
* F + 좌클릭 - For-Each Loop node 생성
* M + 좌클릭 - Multi-gate node 생성
* N + 좌클릭 - Do N Times node 생성
* O + 좌클릭 - Do Once node 생성
* P + 좌클릭 - BeginPlay node 생성

## Unreal 용어 정리

### mode

#### Visual Effects

* ##### Atmospheric Fog

  대기를 표현

* ##### Exponential Height Fog

  습기가 많은 지역 안개 표현

#### Volume

* ##### Lightmass Importance Volume 

  Global Illumination 효과 적용(Global Illumination - 직접광, 반사광 등 여러 광원을 계산하여 사실적인 빛 표현/계산방식) 



### Material Editor

#### Node

* Abs - 절대값, DotProduct(내적)와 주로 사용
* AppendVector - vector 생성
* Ceil - 변수 소수점 값 올림
* Floor - 변수 소수점 값 버림
* Frac - 변수 정수값 버림

#### Material 입력값

* Basic Color - Diffuse Color 용도로 사용하기 위한 material 표면 색상 정보
* Roughness - 표면의 거친 정도
* Metalic - 금속 재질 수치
* Specular - 반사값(Roughness, Metalic과 함께 사용 X 권장)
* Emissive - 자체 발광 색상(랜턴, 발광 물체 등을 표현)
* Normal - 



### Blueprint

#### Class Default

* Default - 생성한 변수와 그 값
* Rendering - 해당 Actor의 게임 내 rendering 방식 관련 정보
* Replication - 네트워크 우선권, 타 client와의 연관성 등
* Input - 해당 actor의 입력 반응 방식
* Actor - 해당 actor 관련 정보

#### Component

class blueprint에만 있는 기능. blueprint의 구성 요소 추가/편집하여 actor를 완성

#### Event Graph

event 처리

#### Construction Graph

class  생성시 처리되는 로직

## Unreal 질문

* geometry에서 subtract으로 sphere brush를 쓸때 예제 책에선 material을 설정하는 부분이 있던데, 이게 무슨 의미인지? detail 창에 material 설정 자체가 없던데, 이게 버전 차이인지? -> 잘못 알았구만. 선택 가능하네. material 설정으로 깎여진 표면 설정을 하는구만
*  Visual Effects에 Atmospheric Fog는  설정을 했는데도 화면에 표시가 안되는데 이건 어떻게 설정하고 어떨때 사용하나?
* Volumes에 Lightmass Importance Volume 영역 설정의 의미는? 그 영역만 빛 처리 영역으로 지정해서 하겠다는건가?
* node 중에 frac은 어디다 쓰지?

