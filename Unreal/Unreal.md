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

#### Class Setting

부모 class 설정 가능

### Class

![](C:\Users\ajant\Downloads\built_in_class.png)

#### Object

최상위 class. unreal 엔진에서 사용되는 구조체 등이 선언

#### Actor

주로 world나 blueprint에서 호출되느 class를 만들때 상속. world에서의 위치 정보, rendering event 등이 선언

#### Pawn

player나 AI의 동작 제어

#### Character

mesh, collision, physics 속성 정의. CharacterMovementComponent로 Character의 이동

#### Controller

Pawn을 제어

#### AIController

AI로 Pawn을 제어. AI를 만들 수 있음

#### PlayerController

 Player가 Pawn을 제어

#### HUD

2D 이미지(GUI 등)를 그리기 위한 함수

#### PlayerCamera

#### Info

기본 정보 class. 주로 네트워크로 공유하는 정보 보관

#### GameMode

게임 규칙, 점수, 인원 등을 정의

#### GameState

게임 진행 시간, 게임 상태 등을 정의

#### PlayerState

Player의 이름, 점수 등이 정의

#### WorldSetting

level에 이용되는 중력 가속도 증의 정보 정의

#### ActorComponenet

blueprint editor의 component 모드에서 actor에 추가하는 component의 기본 class

### Macro

#### UCLASS()

class 선언 앞에 삽입

* classGroup='그룹 이름' - 이 class가 editor에서 표시될 actor 그룹 지정
* DependsOn='class 이름' - 지정한 class가 컴파일 전에 이 class가 코드를 생성할 수 없음
* BlueprintType - blueprint에서 변수로 사용 가능  
* Blueprintable - 부모 class로 선택 가능
* NoBlueprintable - 부모 class로 선택 불가(default)
* customConstructor - 생성자 선언의 자동 생성을 막음
* placeable - editor에서 이 class를 level에 배치 가능(계승 o)
* notplaceable - level에 배치 불가
* Const - 이 class의 함수와 변수가 모두 상수(계승 o)
* Abstract - 추사 class
* config - 객체를 만들 때 설정을 읽어 옴
* perObjectConfig - class 단위가 아닌 object 별로 설정을 지정

#### GENERATED_BODY()

class 선언의 시작 부분에 삽입된 언리얼 엔진 class에서 필요한 선언

#### UPROPERTY()

변수 선언 앞에 변수 속성 설정

* GlobalConfig - Config와 동일하지만, 모든 자식 class에 반영
* Localized - 속성값이 지역화 문자열 파일에서 읽어옴
* Replicated - 속성값이 서버 및 클라이언트에 복제됨
* ReplicatedUsing = '함수 이름' - Replicated와 함께 사용. 속성값이 복제될때 통지할 함수 지정
* RepRetry - Replicated와 함께 사용. 복제가 실패했을 때 재시도 횟수 지정
*  Category = '그룹 이름' - editor에서 보여질 속성 그룹 설정
* EditAnywhere - editor에서 이 속성값 편집 가능
* EditInstanceOnly - Details 탭에서만 속성값 편집 가능
* EditDefaultsOnly - class default에서만 이 값을 편집 가능
* VisibleAnywhere - editor에서 값을 볼 수 있지만 편집 안됨
* VisibleInstanceOnly - Details 탭에서만 값이 표시. 편집 X
* VisibleDefaultsOnly - class default에서만 값 표시. 편집 X
* BlueprintReadOnly - 이 속성값을 blueprint에서 읽을 수 있으나 편집 X
* BlueprintReadWrite - 이 속성값을 blueprint에서 읽고 편집 가능

#### UFUNCTION()

함수 선언 앞에 설정

* BlueprintImplementableEvent - ?
* SealedEvent - 
* Exec -  이 함수를 명령행에서 실행 가능
* Server - 

## Unreal 질문

* geometry에서 subtract으로 sphere brush를 쓸때 예제 책에선 material을 설정하는 부분이 있던데, 이게 무슨 의미인지? detail 창에 material 설정 자체가 없던데, 이게 버전 차이인지? -> 잘못 알았구만. 선택 가능하네. material 설정으로 깎여진 표면 설정을 하는구만
*  Visual Effects에 Atmospheric Fog는  설정을 했는데도 화면에 표시가 안되는데 이건 어떻게 설정하고 어떨때 사용하나?
* Volumes에 Lightmass Importance Volume 영역 설정의 의미는? 그 영역만 빛 처리 영역으로 지정해서 하겠다는건가?
* node 중에 frac은 어디다 쓰지?
* class 중 playerState는 플레이어별로 서버에서 생성되어(오프라인 게임도) 모든 클라이언트에 복제 된다 <- 라는 구문을 봤는데, 오프라인에 서버 개념이 들어가질 않는데 무슨 소리인지 모르겠네?
* generated_body()의 기능을 정확히 알고 싶다

