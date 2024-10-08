# Marp로 ppt 작성하기

# 목차
1. Marp란?
2. VSCode로 Marp 시작하기
3. 활용법

## Marp란?
Marp란 마크다운을 변환할 수 있는 도구로 .md 파일을 쉽고 빠르게 프리젠테이션 문서로 변환해주는 툴입니다.

### 장점
- 짧은 시간동안 사용해본 결과, **빠르게 원하는 내용을 ppt 파일**로 전달하기 좋습니다.
- **코드나 수식**을 활용하여 만들기 좋습니다.
- **css 파일**을 만들어 원하는 템플릿, 글자 크기, 색상, 테이블이나 사진 크기 등을 저장하여 간편하게 만들 수 있습니다.

### 단점
- 위 장점은 ppt도 갖고 있습니다. 굳이 이걸 썼을 때의 장점은 코드 블럭을 활용할 수 있는 것 정도...?
- css로 커스터마이징해야 하는데 ppt에 비해 **상당히 많은 시간이 필요**합니다.

## VS Code로 Marp 시작하기

1. Marp for VS Code 익스텐션 설치해야 합니다.
2. .md 파일을 생성한 뒤 아래 코드를 입력하여 marp을 시작합니다.
```md
---
marp: true
---
```
3. 잘 나오는지 ctrl + k v를 눌러 확인합니다. (Ctrl + Shift + V의 경우, 새 창을 열어 확인)
4. `---`을 통해 페이지를 구분할 수 있습니다.
5. 이제 마크다운 문법으로 작성하면 ppt가 그에 맞게 만들어집니다.

## Marp 활용법

기본적인 스타일 활용법은 2가지입니다. 문서 작성은 마크다운으로 하면 되지만,

ppt로써의 기능을 하려면 스타일링이 가능해야 합니다.

#### MD 파일 내에서 스타일링 하기
```md
---
marp: true
title: 제목
header: 상단에 들어갈 내용
footer: 하단에 들어갈 내용
paginate: ture -> 쪽 수 매기기
theme: default, gaia(내장 테마)
style: |
h1 {
    스타일을 직접 지정할 수 있습니다.
}
---
```

이미지 첨부의 경우도 마크다운 문법으로 할 수 있는데 사진 설명란에 다음과 같이 위치와 크기를 지정해주면
그에 맞게 사진이 업로드 됩니다.
```md
 ![bg right height:300px](cute_hamster.jpg)
```

#### 외부 css 파일로 테마 만들기

내부에 style 태그를 쭉 쓰면 코드가 길어지고 읽기 어려워집니다. 따라서 외부에 css 파일을 만드는 것도 하나의 방법입니다.

외부 css 파일로 테마를 만드는 것은 상당히 복잡하여 만들진 못했지만.. 방법은 다음과 같습니다.

1. themes 폴더를 생성합니다.
2. themes 폴더 안에 css 파일을 생성합니다.
3. css 파일 상단에 `<!-- theme custom -->`을 입력하고 css 코드를 작성합니다. custom 부분에 원하는 테마명을 입력합니다.
4. .vscode 폴더를 생성합니다.
5. .vscode 폴더 안에 settings.json 파일을 만듭니다.

그리고 settings.json에 다음과 같이 작성합니다.
```
{
    "markdown.marp.themes": [
      "./themes/custom-theme.css"
    ]
}

# custom-theme.css에는 themes 폴더 안의 지정한 파일명을 작성해주면 됩니다.
```

마지막으로 css 파일 상단에 입력했던 테마명을 Md 파일에 theme에 지정해줍니다.

그러면 원하는 스타일로 만들 수 있게 됩니다. 

위 내용을 github에 올려봤습니다. 파일, 코드, ppt가 궁금하시다면 [git_Marp](https://github.com/Donggyu-Kim1/Marp)를 참고해주세요.

Marp에 대해 더 알고 싶다면, [Marp](https://marpit.marp.app/directives)를 참고하면 좋습니다.