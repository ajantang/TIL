# Unreal(4.23.1 기준)

## Unreal tip

### Main Editor 단축키

* Alt + P - 플레이
* F(Actor 선택 상태) - Actor 로 카메라 이동

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

## VR Setting

### Oculus

#### DOC

* https://developer.oculus.com/documentation/unreal/unreal-engine/
* https://docs.unrealengine.com/en-US/Platforms/VR/OculusVR/index.html

#### READY TO DEVELOP

* Oculus reuntime 설치
* 편집기에서 VR Preview 버튼 클릭

### VIVE

#### DOC

* https://docs.unrealengine.com/en-US/Platforms/VR/SteamVR/index.html

#### READY TO DEVELOP

* SteamVR 설치
* Room Setup 실행
* 편집기에서 VR Preview 버튼 클릭

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
* Break Rot - 회전값을 3가지 float으로 분해
* Make Rot - float 값을 회전값으로 변환
* Add Control Yaw Input - 컨트롤러의 방향이 Yaw 방향 회전
* Add Control Pitch Input - 컨트롤러의 방향이 Pitch 방향 회전



![](C:\Users\ajant\Pictures\회전.jpg)

#### Material 입력값

* Basic Color - Diffuse Color 용도로 사용하기 위한 material 표면 색상 정보
* Roughness - 표면의 거친 정도
* Metalic - 금속 재질 수치
* Specular - 반사값(Roughness, Metalic과 함께 사용 X 권장)
* Emissive - 자체 발광 색상(랜턴, 발광 물체 등을 표현)
* 



### Blueprint

#### Class Default

* Default - 생성한 변수와 그 값
* Rendering - 해당 Actor의 게임 내 rendering 방식 관련 정보
* Replication - 네트워크 우선권, 타 client와의 연관성 등
* Input - 해당 actor의 입력 반응 방식
* Actor - 해당 actor 관련 정보

#### Component

class blueprint에만 있는 기능. blueprint의 구성 요소 추가/편집하여 actor를 완성

'(inherited)'이 붙어 있는 것은  c++ code로 작성되었다는 표시 

Pawn, Character class 가 플레이어 제어할 수 있는 기본적인 actor의 class

[***] Collison - 충돌 처리범위

##### Character Movement

* Walkable Floor Z - 놀라갈 수 있는 기울기 설정 값?

* Groud Friction - 제동력

* Orient Rotation to Movement - true : 캐릭터의 방향에 따라 카메라 방향 이동

* Use Controller Desired Rotation - true : 캐릭터의 방향을 컨트롤러의 방향으로 맞춤

* Can Walk Off Ledges - true : 경사가 가파른 언덕에서 낙하

* Can Walk Off Ledges When Crouching - 웅크릴때? 위의 옵션이 켜짐

  ##### 

##### Camera

* Use Controller View Rotation - true : camera의 반향을 Controller class의 방향에 따라 움직임

##### SpringArm

* Enable Camera Lag - 캐릭터가 이동할 때 카메라 지연
* Enable Camera Lag - 캐릭터가 방향을 바꿀 때의 카메라 지연

##### Motion Controller

* Hand - Right/Left 설정

#### Event Graph

event 처리

##### Node

* Timeline - 시간에 따른 value 변화 설정 가능(간단한 움직임 처리에 적합)
* Spawn Emitter at Location - Emitter는 특정 위치에  particle effect를 만듬
* Event Begin Play - 게임이 시작되면 곧바로 호출
* Add to Viewport - viewport에 추가
* Get Owning Actor - 애니메이션 블루프린트를 사용하고 있는 mesh의 부모 actor 참조
* Actor Has Tag - 타겟이 해당 tag를 가지고 있는지 출력
* Line Trace by Channel - 시작과 종료 위치에 공선을 날려 접촉 판덩 결과를 출력
* Break Hit Result - hit 정보 구조체 내부 정보
* Get Anim Instance - 애니메이션 블루프린트 호출(컴포넌트에서 배치)

##### Node - AI

* MoveToActor - 타겟/정지 조건등을 상세 설정하여 이동(리턴값? 바이트인거 같은데??)
* MoveToLocation - MoveToActor와 동일한 기능 + dest(vector) + 노드 사용 전 좌표 설정? 이 존재(dest의 정확한 역할은 찾아봐야할듯)
* SimpleMoveToActor - 타겟만 설정
* SimpleMoveToLocation - 위치만 설정
* StopMovement - 위의 노드들을 이용해 움직일때 멈춤
* GetPathConst - 경로를 탐색하고 그 비용을 출력(맵 좌표에 따라 비용을 다르게 설정 가능 - 참고 : Component -> Nav Modifier)
* GetPathLenth - 경로 길이
* GetRandomPoint - 범위 내의 navi mesh에서 랜덤한 위치 (ai 젠 좌표 설정에 사용)

#### Construction Graph

class  생성시 처리되는 로직

#### Class Setting

부모 class 설정 가능

### User Infterface

#### Widget Blueprint

##### Palette

###### Panel

* Horizontal Box - 
* Vertical Box - 

##### Detail

* Anchors - 스크린의 크기/비율 변화에 따라 위치 자동 조절

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

* Server - 이 함수가 서버에서 실행되기 위해 복제됨. 함수 선언은 함수 이름 대신 '함수 이름_Implementation'으로 작성해야 합니다

* NetMulticast - 이 함수가 actor의 NwrOener에 관계없이 서버와 모든 client에 복제되고 실행됨

* Reliable - 복제된 함수를 호출하는 것이 확실하게 진행되어야 함을 나타냅니다. 'Client'나 'Server' 지정자와 함께 사용할 때만 유효합니다

* Unreliable - 복제된 함수를 호출하는 것이 불확실하게 진행되어야 함을 나타냅니다. 'Client'나 'Server' 지정자와 함께 사용할 때만 유효합니다

* BlueprintCallable - 이 함수는 blueprint에서 호출 가능하고 표시 됨

* Category = '그룹 이름' - blueprint editor의 표시될 함수 그룹을 지정

  cf> ObjectBase.h 에 macro 지정자가 선언되어 있음

### c++ 디버깅 코드

* AddOnScreenDebugMessage(float, float, FColor, "Text"); - GEngine 클래스 함수로 화면에 "Text" 출력 

### 자료형

* FVector - 3차원 벡터
* FQuat - 쿼터니언
* FVector2D - 2차원 벡터
* FRotator - 3차원 공간상의 회전 정보
* FTransform - 4*4 배열(회전, 위치, 스케일 정보)
* FString - TChar 동적 배열
* FName - Global string table?로 구성된 변경불가/대소문자 구분 없는 레퍼런스?
* FText - 현지화를 고려한 문자열?

### AI 설정

* Behavior Tree - 
* AIController - 
* Blackboard - 

## Unreal 질문

* geometry에서 subtract으로 sphere brush를 쓸때 예제 책에선 material을 설정하는 부분이 있던데, 이게 무슨 의미인지? detail 창에 material 설정 자체가 없던데, 이게 버전 차이인지? -> 잘못 알았구만. 선택 가능하네. material 설정으로 깎여진 표면 설정을 하는구만
*  Visual Effects에 Atmospheric Fog는  설정을 했는데도 화면에 표시가 안되는데 이건 어떻게 설정하고 어떨때 사용하나?
* Volumes에 Lightmass Importance Volume 영역 설정의 의미는? 그 영역만 빛 처리 영역으로 지정해서 하겠다는건가?
* node 중에 frac은 어디다 쓰지?
* class 중 playerState는 플레이어별로 서버에서 생성되어(오프라인 게임도) 모든 클라이언트에 복제 된다 <- 라는 구문을 봤는데, 오프라인에 서버 개념이 들어가질 않는데 무슨 소리인지 모르겠네?
* generated_body()의 기능을 정확히 알고 싶다
* node 중에 Add to Viewport 기능이 정확히? viewport에 추가하겠다는 기능 같은데, target으로 받는 인자의 종류가 위젯만 받는건가?
* VR 프로젝트 생성시 c++ 선택이 안되던데, 이게 프로젝트 내부에서 c++ 사용에 다른 제약이 있는건지? 
* SpringArm과 Camera component를 같이 사용하라고 하는데, 둘의 개념이 정확히 어떻게 나눠진 것인지?
* ~~음....뭐지 예제 7.3 다시 확인 바람 - camera rotation 관련 블루프린트 설정 법 확인 필요~~ - 해결
* 메타데이터? c++ 관련 메타데이터 설정법에 대한 부분이 불명확함. 에디터 빌드할때 c++ 코드에 접속할 수 있지만 정식 출시에는 쓰지 않는다는게 개발 단계에서만 쓰고 정식 버전에서 사용할때는 쓰지 않는다는 뜻?
* 변수 중 byte 의 주요 사용처는? 
* VR 기기 종류도 많고 그에 따른 컨트롤러의 입력값도 많이 다른거 같은데, 혹시 입력값에 대한 일정 패턴을 파악할 수 있는 함수가 있는지?
* FSting, FName, FText에 대한 자세한 설명이 필요
* 엔진을 수정해서 사용하는 샘플은?
* IKINEMA RunTime? vr 관련 내용이 있던데, 기본적으로 사용되는 라이브러리 인지?
* 음...vr controller 적용하는 블루프린트 구성을 보면서 약간은 기본적인 질문 사항이 생겼는데, 대충 자료형에 따라 소켓? 색이 다른건 알겠는데, 연보라?색은 벡터 표시가 아닌가요? 그리고 하늘색이 일부 자료형을 제외하고 통틀어서 표시하는거 같은데  VR HMD Scene은 음...정확히 어떤것인데 parent로 받아서 처리하는 부분이 있는지 잘 모르겠네요



관련 강의 수강중 - https://www.udemy.com/course/unreal-engine-the-ultimate-game-developer-course/

