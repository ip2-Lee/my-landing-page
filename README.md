# Sound360 Promotion - Device Detection Landing Page

이 프로젝트는 단일 URL(`GitHub Pages`)로 접속하는 모든 사용자의 기기를 자동으로 감지하여, 최적화된 **Mobile View** 환경을 제공하는 지능형 랜딩 페이지 솔루션입니다.

Wix와 같은 반응형 웹사이트가 PC 브라우저 내의 Iframe 환경이나 태블릿 등에서 모바일 뷰를 제대로 송출하지 못하는 문제를 해결하기 위해 설계되었습니다.

---

## 🚀 주요 기능 (Features)

### 1. 초고속 모바일 리다이렉트 (Zero-Latency Redirect)
- 사용자가 접속하는 순간(HTML Body 로딩 전), `<head>` 단계에서 스크립트가 즉시 실행됩니다.
- **모바일 기기(Android/iOS)**로 감지되면, 원본 사이트(`sound360promotion.com`)로 즉시 이동시킵니다.
- `window.location.replace()` 방식을 사용하여, 사용자가 '뒤로가기'를 눌렀을 때 랜딩 페이지에 다시 갇히는(Loop) 현상을 방지했습니다.

### 2. PC 사용자용 가상 모바일 뷰 (Virtual Mobile Container)
- **PC 환경**으로 감지되면 리다이렉트하지 않고, 화면 중앙에 **iPhone 스타일의 프레임**을 띄웁니다.
- Wix 서버에 `showMobileView=true` 파라미터를 포함한 요청을 보내, Iframe 내부에서도 강제로 모바일 레이아웃이 렌더링되도록 유도합니다.
- 다크 모드 배경(#1a1a1a)과 그림자 효과를 적용하여 고급스러운 사용자 경험을 제공합니다.

### 3. 크로스 브라우징 및 예외 처리
- **기기 감지 로직**: User-Agent 문자열뿐만 아니라 `maxTouchPoints`(터치 지원 여부)와 화면 너비를 복합적으로 검사하여, 아이패드나 갤럭시 탭 같은 태블릿 환경도 정밀하게 분류합니다.

---

## 🛠 사용 기술 (Tech Stack)

- **HTML5 / CSS3**: 반응형 레이아웃 및 Iframe 스타일링
- **Vanilla JavaScript**: 외부 라이브러리 없는 순수 JS로 초경량/고속 실행 보장
- **GitHub Pages**: 별도의 서버 구축 비용 없이 정적 호스팅

---

## 📂 파일 구조 (File Structure)

```text
📦 my-landing-page
 ┣ 📜 index.html   # 핵심 로직 (기기 감지 + 리다이렉트 + Iframe 뷰어)
 ┗ 📜 README.md    # 프로젝트 설명 문서
