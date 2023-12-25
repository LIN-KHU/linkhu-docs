# 📜 프로그래밍 요구사항

## Java Style Guide

자바 스타일 가이드는 [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)를 기준으로
작성되었습니다. ([한글 번역 1](https://github.com/JunHoPark93/google-java-styleguide)
, [한글 번역 2](https://newwisdom.tistory.com/m/96))

Google Java Style Guide와 다른 부분만 아래 명시합니다.

---

### 4.2 블럭 들여쓰기: +4 스페이스

새 블록 또는 블록과 유사한 구조(block-like construct)가 열릴 때마다 들여쓰기가 네 칸씩 증가합니다. 블록이 끝나면 들여쓰기는 이전 들여쓰기 단계로 돌아갑니다. 들여쓰기 단계는 블록 전체의 코드와
주석 모두에 적용됩니다.

### 4.4 열 제한: 120

Java 코드의 열 제한은 120자입니다. "문자"는 유니코드 코드 포인트를 의미합니다.

### 4.5.2 들여쓰기 지속은 최소 +8 스페이스

줄 바꿈 시 그 다음 줄은 원래 줄에서 +8 이상 들여씁니다.

### 4.6.1 수직 빈 줄

...

빈 줄은 가독성을 향상시키기 위해서라면 어디든(예를 들면 논리적으로 코드를 구분하기 위해 문장 사이) 사용 될 수 있습니다. 클래스의 첫 번째 멤버나 초기화(initializer) 또는 마지막 멤버 또는 초기화(
initializer) 뒤의 빈 줄은 권장되지도 비권장하지도 않습니다.

> 클래스의 첫 번째 멤버나 초기화(initializer) 앞에 있는 빈줄을 강제하지 않습니다.

...

## 추가 요청 사항
- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- 3항 연산자를 쓰지 않는다.
- 함수(또는 메소드)의 길이가 15라인을 넘어가지 않도록 구현한다.
  - 함수(또는 메소드)가 한 가지 일만 잘 하도록 구현한다.

# ✍️ 과제 진행 요구 사항
- 기능을 구현하기 전 docs/README.md에 구현할 기능 목록을 정리해 추가한다.
- git의 commit 단위는 앞 단계에서 README.md 파일에 정리한 기능 목록 단위로 추가한다.
  - [AngularJS Commit Message Conventions](https://gist.github.com/stephenparish/9941e89d80e2bc58a153) 참고해 commit log를 남긴다.
