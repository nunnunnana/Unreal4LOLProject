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
>

Quiz_Oriana_PawnQuiz_Oriana_Pawn
>

- <개발>
  - quiz_actor에 큐브가 이동할 Scene Component 4개를 배치
  - Scene Component Target_list에 넣고 초기 인덱스를 0으로 설정
  - 만약 Is_Move가 True이면 Cube에 Y축을 계속 더하고 Next_Target과 Cube의 위치가 동일해지면  인덱스에 +1을 해 다음 타겟을 바꿔준다.
  - 인덱스가 Target Lengh와 같아지면 인덱스를 0으로 설정
  - Qube를 인덱스 n번째의 Scene Component에 Attach하고 인덱스에 +1을 해서 Next_Target을 바꿔준다.
  - 만약 인덱스가 Target Lengh보다 커지면 인덱스를 0으로 설정



***
## 2. 제드
- Quiz_0
  - 지정된 위치에 큐브가 도착하면 자동으로 다음 위치로 이동

![Quiz_0](https://github.com/nunnunnana/Unreal4_Project/assets/99165741/0f74f14b-7bdb-4a96-a2ee-7a7cc4fe11d2)

- 블루프린트 코드

Quiz_0_Cube_Actor
>https://blueprintue.com/blueprint/sekq4uq0/

- <개발>
  - quiz_actor에 큐브가 이동할 Scene Component 4개를 배치
  - Scene Component Target_list에 넣고 초기 인덱스를 0으로 설정
  - 만약 Is_Move가 True이면 Cube에 Y축을 계속 더하고 Next_Target과 Cube의 위치가 동일해지면  인덱스에 +1을 해 다음 타겟을 바꿔준다.
  - 인덱스가 Target Lengh와 같아지면 인덱스를 0으로 설정
  - Qube를 인덱스 n번째의 Scene Component에 Attach하고 인덱스에 +1을 해서 Next_Target을 바꿔준다.
  - 만약 인덱스가 Target Lengh보다 커지면 인덱스를 0으로 설정
