# 🌅 인생 파노라마 스튜디오 (Life Panorama Studio)

> **어릴 적 사진 한 장으로 10대부터 70대까지의 미래 모습을 그려보세요.**
> Google Gemini 2.5 Flash Image(나노 바나나)를 활용해 한 장의 사진에서 6개 세대(10·20·30·40·50·70대)의 모습을 동시에 생성하는 웹앱입니다.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Try%20Now-black?logo=vercel)](https://life-panorama.vercel.app/)
[![Gemini](https://img.shields.io/badge/Gemini-2.5%20Flash%20Image-blue)](https://ai.google.dev/gemini-api/docs/image-generation)
[![BYOK](https://img.shields.io/badge/Bring%20Your%20Own-API%20Key-orange)](https://aistudio.google.com/apikey)

---

## 🤔 기획 동기

> "내가 나이가 들면 어떤 모습일까?"

누구나 한 번쯤 궁금해하는 주제입니다. 어릴 적 사진 한 장만으로 **10대부터 70대까지의 미래 모습을 한 번에 시각화**하여, 인생의 여정을 한 화면에서 미리 들여다볼 수 있도록 했습니다.

---

## ✨ 주요 기능

| 기능 | 설명 |
|------|------|
| 📤 **간편한 사진 업로드** | 어린 시절 사진(JPG/PNG) 한 장으로 시작 |
| 🌅 **6개 세대 동시 생성** | 10대 · 20대 · 30대 · 40대 · 50대 · 70대 |
| 🖼️ **결과 확대 보기** | 그리드 + 모달 뷰 |
| 💾 **개별/전체 다운로드** | 한 장씩 저장 또는 ZIP 일괄 다운로드 |
| 🔐 **BYOK 방식** | 사용자 본인의 Gemini API 키 사용 (브라우저 내에서만 사용, 외부 저장 없음) |
| 🧬 **얼굴 정체성 보존** | 인종·성별·핵심 이목구비는 유지하고 나이만 자연스럽게 변화 |

---

## 🚀 바로 사용하기

👉 **[https://life-panorama.vercel.app/](https://life-panorama.vercel.app/)**

### 사용 단계
1. **사진 업로드** - 어린 시절(아동/청소년기) 정면 사진 권장
2. **API 키 입력** - [Google AI Studio](https://aistudio.google.com/apikey)에서 무료 발급
3. **"미래 보기"** 클릭 → 6개 세대 순차 생성 (수십 초 소요)
4. **결과 저장** - 개별 다운로드 또는 ZIP 일괄 다운로드

> ⚠️ AI는 얼굴 특징을 항상 완벽히 반영하진 못합니다. 마음에 드는 결과를 위해 여러 번 시도해 보세요.

---

## 🛠️ 기술 스택

| 분류 | 기술 |
|------|------|
| **프론트엔드** | Vanilla JavaScript (단일 `index.html` 파일) |
| **스타일링** | Tailwind CSS (CDN) |
| **AI 모델** | Google **Gemini 2.5 Flash Image** (`gemini-2.5-flash-image`) |
| **압축 다운로드** | [JSZip](https://stuk.github.io/jszip/) |
| **호스팅** | Vercel (정적 웹사이트, GitHub 연동 자동 배포) |

> 💡 백엔드 서버 없이 모든 요청이 사용자 브라우저에서 Google Gemini API로 직접 전송됩니다.

---

## 📦 로컬 실행

```bash
# 저장소 복제
git clone https://github.com/tigerjk9/life-panorama-studio.git
cd life-panorama-studio

# 정적 서버 실행 (Python 3 기준)
python -m http.server 8000

# 브라우저에서 http://localhost:8000 접속
```

> 💡 별도 빌드 과정 없음. `index.html`을 브라우저에서 직접 열어도 동작합니다.

---

## 💡 핵심 노하우: 프롬프트 엔지니어링

원본 이미지의 **인종·성별·얼굴 구조는 유지**하면서 나이만 자연스럽게 변화시키기 위해, 각 세대별로 구체적인 환경·복장·표정 키워드를 포함한 영문 프롬프트를 사용합니다.

### 세대별 프롬프트 핵심 키워드

| 세대 | 분위기 키워드 |
|------|--------------|
| **10대** | high school graduation portrait, hopeful expression |
| **20대** | young professional/traveler, confident, contemporary fashion |
| **30대** | warm family / professional environment, mature confidence |
| **40대** | hobby/social gathering, comfortable and content |
| **50대** | dignified portrait, accomplished, nice home or office |
| **70대** | warm and heartwarming, laugh lines, gentle happy expression |

모든 프롬프트의 공통 조건:
- *"core facial features, ethnicity, and gender must be preserved"*
- *"highly realistic photograph"*
- *"The image must not contain any text or letters"* (Negative prompt)

---

## 🔑 API 키 발급 가이드

1. [Google AI Studio](https://aistudio.google.com/apikey) 접속
2. Google 계정 로그인
3. **"Create API Key"** 클릭 → 키 복사
4. 본 앱 입력란에 붙여넣기

> 🔒 **보안:** API 키는 사용자 브라우저 내에서만 사용되며, 외부 서버로 전송·저장되지 않습니다.
> 단, 입력 필드에 잠시 보관되므로 **공용 PC 사용 후에는 새로고침** 권장.

---

## 📁 저장소 구성

```
life-panorama-studio/
├── README.md       # 본 문서
└── index.html      # 단일 파일 웹앱 (HTML + CSS + JS 통합)
```

---

## 📝 변경 이력

| 날짜 | 내용 |
|------|------|
| 2026-04-19 | Vercel(`life-panorama.vercel.app`) 배포 + Netlify 호스팅 종료 + README 현행화 |
| 2026-04-19 | Gemini 모델명 GA 전환: `gemini-2.5-flash-image-preview` → `gemini-2.5-flash-image` (404 오류 해결) |

---

## 🐛 알려진 제약

- 얼굴 인식이 어려운 사진(측면, 가림, 저해상도)은 결과 품질 저하
- 모델 응답 시간: 6개 세대 동시 생성 시 수십 초 소요
- API 무료 할당량 초과 시 429 오류 (자동 재시도 3회)

---

## 🔗 관련 프로젝트 (Nano Banana 시리즈)

| 프로젝트 | 설명 | 라이브 |
|---------|------|--------|
| **Life Panorama Studio** *(본 프로젝트)* | 한 사진으로 6개 세대 미래 모습 | [link](https://life-panorama.vercel.app/) |
| **Nostalgia Photo Studio** | 한국 근현대사 8개 시대로 시간 여행 | [link](https://nostalgia-photo-studio.vercel.app/) |
| **AI ID Photo Studio** | AI 증명사진 6장 동시 생성 | [link](https://ai-id-photo-studio.vercel.app/) |
| **AI Style Transfer Studio** | 6가지 그림체 캐릭터 변신 | [link](https://ai-style-transfer-1310-studio.vercel.app/) |

---

## 🙏 크레딧

- **Google Gemini 2.5 Flash Image (Nano Banana)** - 멀티모달 이미지 생성 모델
- **Tailwind CSS** - 유틸리티 우선 CSS 프레임워크
- **JSZip** - 클라이언트 사이드 ZIP 생성
- **나노 바나나 프롬프트 참고** - [tigerjk9.github.io/ai/nano-banana](https://tigerjk9.github.io/ai/nano-banana/)

---

## 📝 라이선스

MIT License - 자유롭게 사용·수정·재배포 가능합니다.

---

## 👤 제작자

**김진관 (닷커넥터)**
- GitHub: [@tigerjk9](https://github.com/tigerjk9)
- Project Link: [life-panorama-studio](https://github.com/tigerjk9/life-panorama-studio)

---

> 🌅 **지금 바로 [인생 파노라마 스튜디오](https://life-panorama.vercel.app/)에서 당신의 미래를 미리 만나보세요!**
