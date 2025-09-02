# draw.io-ko-en-translator (KO ↔ EN)

이 프로젝트는 draw.io(diagrams.net) XML 파일을 업로드하면
라벨 텍스트를 번역(한국어 ↔ 영어)하고,
다시 `.drawio` 파일로 다운로드할 수 있게 해주는 웹앱입니다.

- 배포: **GitHub Pages**
- 번역 엔진: DeepL, Google Cloud Translation, Azure Translator (선택 가능)
- API 키: 사용자가 직접 입력 (세션 저장소에만 저장, 서버 보관 없음)
- 프록시: Cloudflare Worker (`/worker.js`)를 통해 CORS 해결

---

## 🚀 사용 방법
1. [Cloudflare Worker](https://dash.cloudflare.com/)를 생성하고  
   `worker.js` 코드를 붙여넣어 배포합니다.
2. 생성된 워커 URL을 `index.html`의 `proxyURL` 변수에 넣습니다.
3. 이 리포지토리 루트에 `index.html` 파일을 추가하고 푸시합니다.
4. GitHub Pages 설정에서 브랜치를 선택해 배포합니다.
5. 배포된 페이지에 접속 → `.drawio` 파일 업로드 → 번역 실행 → 다운로드.

---

## 📂 파일 구성
- `index.html` → 메인 웹앱
- `worker.js` → Cloudflare Worker 프록시
- `README.md` → 이 문서

---

## ⚠️ 주의
- 번역 API 요금 정책/사용 제한을 반드시 확인하세요.
- API 키는 세션에만 저장되고, 새로고침 시 사라집니다.
- URL, 변수(`{{var}}`), `$VAR` 등은 번역 제외 패턴으로 보호할 수 있습니다.

