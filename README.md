# ZERO G LAB — 무중력 물·기름 시뮬레이터

브라우저에서 실행하는 단일 HTML 시뮬레이터입니다. 별도 설치, API 키, 외부 라이브러리가 필요하지 않습니다.

## 기능
- 물·기름·금속 구슬·큐브·고리 추가
- 물체 선택, 이동, 던지기, 삭제
- 같은 종류 액체의 합체 및 선택한 액체 분리
- 중력, 표면장력, 점성, 시간 배속 조절
- WebGL 기반 굴절·반사 표현 및 Canvas 호환 모드
- 모바일 WebGL 셰이더의 배열 인덱싱 제한 대응

## 실행
배포 파일은 `index.html` 하나입니다. 브라우저에서 열거나 아래처럼 정적 서버로 실행합니다.

```sh
python -m http.server 8000
```

이후 `http://localhost:8000`에 접속합니다.

## GitHub Pages 배포

1. 저장소의 Settings → Pages를 엽니다.
2. Build and deployment → Source에서 Deploy from a branch를 선택합니다.
3. Branch를 main, 폴더를 /(root)로 선택하고 Save를 누릅니다.
4. 배포가 끝나면 Pages 설정에 표시되는 Visit site로 접속합니다.

설정 후 main의 index.html을 수정하면 재배포됩니다. 별도 빌드 작업은 없습니다.

- 설정: https://github.com/waterfirst/zero-g-water/settings/pages
- 공식 안내: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- 기존 배포: https://zero-g-water-nakcho.waterfirst.chatgpt.site

이 저장소와 기존 배포는 자동 동기화되지 않습니다. GitHub Pages를 설정하면 GitHub 코드 기준으로 별도 운영됩니다.

## 모델 범위
정량 CFD가 아닌 시각화용 근사 모델입니다. 물과 기름은 합쳐지지 않지만 계면, 유화, 밀도에 따른 층 분리는 계산하지 않습니다. 고체 충돌은 구형 경계로 근사하며 고리 구멍 통과, 젖음, 침수는 재현하지 않습니다. 진공이 아닌 밀폐 실험실을 가정합니다.

## 검증
JavaScript 문법, 셰이더 인덱싱 수정, WebGL 미지원 및 셰이더 컴파일 실패 시 호환 모드 전환을 점검했습니다. 모든 모바일 GPU에서의 WebGL 화면을 검증한 것은 아닙니다.
