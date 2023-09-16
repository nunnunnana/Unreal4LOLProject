# Unreal4LOLProject

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
 


>그림자 공격

- 그림자 생성 후 공격을 하면 그림자도 동일하게 공격



- 블루프린트 코드

Zed_Character
>

Zed_Shadow
>

- <개발>
  - 
