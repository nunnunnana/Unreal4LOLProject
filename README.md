# Unreal4_LOLProject

### 언리얼 엔진을 사용해 간단한 롤 캐릭터를 제작한 프로젝트 입니다.
***
## 1. 오리아나

### 주요 기능

>기본

- 구체는 플레이어 주위로 계속 회전
- W, A, S, D로 움직이고 마우스로 회전

![오리아나 이동](https://github.com/nunnunnana/Unreal4LOLProject/assets/99165741/bc2c879b-5e1d-4a13-bcb5-06852c1f01c1)

>오리아나 구체이동

- 마우스 왼쪽 클릭을 하면 플레이어가 바라보는 방향으로 구체 이동
- 마우스 오른쪽 클릭을 하면 구체 돌아오기
- 구체는 플레이어와 멀어졌을 때 플레이어를 가리키는 화살표나 표시됨
 
![오리아나 구체 이동](https://github.com/nunnunnana/Unreal4LOLProject/assets/99165741/fe0e1aab-e81d-4322-ada3-d08cf03cc9a8)

>플레이어와 구체 상호작용

- 플레이어와 구체가 멀어지면 구체가 빨갛게 변하고 플레이어로 돌아오기
- 플레이어와 구체가 가까워지면 구체 위치에서 부터 플레이어 주위로 회전

![오리아나 구체 상호작용](https://github.com/nunnunnana/Unreal4LOLProject/assets/99165741/bfa75fde-8b21-4c92-a776-73f910495d96)

>오리아나 궁극기

- 스페이스바를 누르면 구체 주위에 있는 액터들이 구체로 모임
- 스페이스바를 한번 더 누르면 모였던 액터가 구체 주위로 펴짐
- 구체가 주위 액터들을 모은 상태에서 구체가 이동하면 자동으로 모았던 액터를 펼침

![오리아나 궁극기](https://github.com/nunnunnana/Unreal4LOLProject/assets/99165741/5b7ce62a-9adb-4aa7-9c5e-b49d6a9d7a88)

- 블루프린트 코드

Quiz_Oriana_Sphere_Actor
>https://blueprintue.com/blueprint/8a-3cdog/

Quiz_Oriana_PawnQuiz_Oriana_Pawn
>https://blueprintue.com/blueprint/3vo2he_j/

- <개발>
  - Pawn에 Scene 컴포넌트를 생성하고 Sphere_Actor를 Scene 컴포넌트에 Attach 후 Scene을 계속 회전시킴
  - 마우스 왼쪽 클릭을 누르면 Sphere_Actor를 Detach 하고 Pawn 액터의 정방향 벡터를 구해 500 만큼의 거리로 이동
  - Pawn과 Sphere의 거리가 800 이상이면 Sphere Color를 Red로 바꾸고 거리가 1000 이상이면 Pawn에 Attach
  - 마우스 오른쪽 클릭을 하면 Sphere_Actor의 위치에서 Pawn에 Scene 컴포넌트 위치까지 부드럽게 이동 후 Scene에 Attach
  - Sphere_Actor에 Coliision을 생성 후 Pawn이 Overlap되면 World location을 유지하면서 Pawn에 Attach
  - 스페이스바를 누르면 Sphere_Actor에서 Get Overlapping Actors 노드로 Collision에 Overlap 된
  Color_Sphere_Actor_2의 Physics를 끄고 위치를 Sphere_Actor의 위치로 변경
  - 액터가 모인 상태에서 스페이스바를 누르거나 공의 위치가 변경되면 Overlap 된 Color_Sphere_Actor_2의 Physics를 켬



***
## 2. 제드

### 주요 기능

>기본 이동 및 공격

- W, A, S, D로 움직이고 마우스로 회전
- 마우스 왼쪽 클릭으로 표창 던지기
- 키보드 E를 누르면 회전하면서 주변 사물 베기

![Zed 이동 및 공격](https://github.com/nunnunnana/Unreal4LOLProject/assets/99165741/024241cc-495c-47d7-bfc3-6a1237cdd6d3)

>그림자 생성

- 키보드 Q를 누르면 그림자 생성
- Q를 한 번 더 누르면 그림자와 위치 변경
- 그림자는 5초 뒤 사라짐
 
![제드 그림자 생성](https://github.com/nunnunnana/Unreal4LOLProject/assets/99165741/454f2c9c-500f-477b-9040-73061d0561a5)

>그림자 공격

- 그림자 생성 후 공격을 하면 그림자도 동일하게 공격



- 블루프린트 코드

Zed_Character
>https://blueprintue.com/blueprint/21z_hnkf/

Zed_Shadow
>https://blueprintue.com/blueprint/5jplke-t/

- 애니메이션 생성
  - 애니메이션 키 값을 설정해 공격, 그림자 생성에 맞는 애니메이션 생성
<img src="https://github.com/nunnunnana/Unreal4LOLProject/assets/99165741/7b4042cc-dacc-471e-9518-c549cf15941a.png" width="350" height="350"/>



- <개발>
  - CurrentState 변수를 생성하고 애니메이션 블루프린트를 생성해 CurrentState 변수 값에 따라 선택한 애니메이션이 재생되도록 추가
  - 마우스 왼쪽 클릭을 누르면 제드 앞에 표창을 생성하고 500만큼 표창을 날림
  - 키보드 E를 누르면 제드에 Cube를 생성해서 제드 중심으로 Cube 회전
  - Q를 누르면 제드 캐릭터의 정방향 벡터를 구한 뒤 그림자 액터를 생성한 후 Distance만큼 Lerp하게 그림자가 이동
  - Q를 한번 더 누르면 Is_Shadow_On 변수를 체크해서 True이면 Shadow_Actor의 위치를 변수에 저장하고 Shadow_Actor의 위치와 Zed_Actor의 위치를 변경
  - 마우스 왼쪽 클릭을 눌렀을 때 Is_Shadow_On가 True면 FindLookAtRotation 노드를 이용해 Zed_Actor가 바라보는 방향에서 Distance 만큼의 거리를 그림자 액터가
  바라보도록 회전한 후 표창을 생성해 Distance만큼 표창을 날림
 






