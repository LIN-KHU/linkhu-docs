## 미션 진행 및 제출 방법 

### 미션 사전 세팅 

#### 1. LINKHU 미션 레포지토리에서 자신의 계정으로 fork 합니다.
   <img width="1247" alt="image" src="https://github.com/LIN-KHU/linkhu-docs/assets/78679830/7df60dec-ca99-4bcb-abba-9622106105ac">

   
</br>
</hr>
</br>

#### 2. fork가 완료되었다면 아래와 같이 본인의 레포지토리에 미션 저장소가 생성됩니다.
<img width="1341" alt="image" src="https://github.com/LIN-KHU/linkhu-docs/assets/78679830/a5fef08b-f7f1-4fe3-8368-3fab267930ed">



</br>
</hr>
</br>


#### 3. fork한 저장소를 자신의 컴퓨터로 clone 합니다.



  <img width="1280" alt="image" src="https://github.com/LIN-KHU/linkhu-docs/assets/78679830/f63d7594-5365-42e4-aa83-bf9e8b571a6e">


  </br>
  
  3-1. `https://github.com/{본인 계정}/{레포지토리 이름}.git` 형태로 클립보드에 복사됩니다.
  3-2. 명령어를 통해 자신의 컴퓨터로 레포지토리를 클론합니다.
  ```bash
  git clone https://github.com/{본인 계정}/java-racing-car.git
  ```
  3-3. 클론된 디렉토리로 이동합니다.
  ```bash
  cd {디렉토리 명}
  ```

  3-4. 브랜치를 만들고 해당 브랜치로 checkout 합니다.
  ```bash
  git checkout -b {깃허브 아이디}
  ```

---

### 미션 진행중

#### 1. 기능 구현 시에 커밋 및 푸시

  1-1. 기능 구현을 완료하면 구현한 내용을 stage에 올립니다.
  ```bash
  git add {파일 명}
  // 수정된 전체 파일을 올리고 싶은 경우에는 git add .
  ```

  1-2. 커밋 메시지를 남깁니다.
  ```bash
  git commit -m "{커밋 메시지}"
  ```

  1-3. 푸시합니다.
  ```bash
  git push
  ```

  터미널을 통해 Git을 사용하는 것도 좋으나, 편의성 측면에서 IntelliJ나 VsCode에 내장된 Git 관련 툴을 사용하시는 것을 추천드립니다 😀
  - [VsCode에서 Git 커밋 및 푸쉬하기](https://devgoat.tistory.com/12)
  - [IntelliJ에서 Git 커밋 및 푸쉬하기](https://velog.io/@dev-mage/connect-intellij-and-github)

---

### 미션 진행 후

#### 1. PR 생성하기

  1-1. pull request 버튼을 클릭합니다.
  <img width="1189" alt="image" src="https://github.com/LIN-KHU/linkhu-docs/assets/78679830/eb37e88d-71d2-49c1-bdab-16c79674aa45">


  1-2. new pull request 버튼을 클릭합니다.
  <img width="1339" alt="image" src="https://github.com/LIN-KHU/linkhu-docs/assets/78679830/ad875fc1-b259-4c2f-b3bf-b2dda2d06303">


  1-3. 본인이 작업한 브랜치에서 원격 Repository의 본인 아이디 브랜치로 pull request를 요청할 수 있도록 pull request 방향 설정을 합니다.
  <img width="1257" alt="image" src="https://github.com/LIN-KHU/linkhu-docs/assets/78679830/bdb2bb08-7793-4352-ae3a-3e0c8af61a02">


  1-4. create pull request 버튼을 클릭합니다.
  <img width="1243" alt="image" src="https://github.com/LIN-KHU/linkhu-docs/assets/78679830/ba828ddf-ad32-4df4-91ad-1c955a7d92c8">


  1-5. pull request 제목과 메시지를 작성한 후에 create pull request 버튼을 클릭합니다.
  <img width="1251" alt="image" src="https://github.com/LIN-KHU/linkhu-docs/assets/78679830/62224e0e-9b76-43ad-81f3-81c74c061401">

  </br>

### 다음 단계로
- [문서](missionguide2.md)를 참고하여 리뷰를 진행한다.
