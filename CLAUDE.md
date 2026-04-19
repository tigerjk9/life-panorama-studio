# CLAUDE.md — 미래 모습 사진관 (Life Panorama Studio)

## 한 줄 정의
어릴 적 사진 한 장 → 10대·20대·30대·40대·50대·70대 6개 세대 미래 모습 동시 생성.

## 라이브 / 저장소
- 🌐 https://life-panorama.vercel.app/
- 🐙 https://github.com/tigerjk9/life-panorama-studio

## 기술 스택
- 단일 `index.html` (Vanilla JS)
- Tailwind CSS CDN + JSZip
- Gemini 2.5 Flash Image (`gemini-2.5-flash-image`, BYOK)

## 핵심 데이터
- 6세대 영문 프롬프트 (10·20·30·40·50·70대)
- 공통 조건: `"core facial features, ethnicity, and gender must be preserved"` + `"highly realistic photograph"` + negative `"no text or letters"`
- 각 세대별 환경/복장/표정 키워드 정밀 명시

## 핵심 결정
- 6개 세대 동시 생성 (현재) — 추후 사용자 선택 모드 검토
- 인종·성별·핵심 이목구비 보존 + 나이만 자연스럽게 변화

## 변경 핵심 이력
- 2026-04-19: Gemini 모델명 GA 전환 (`-preview` 제거) + Vercel 호스팅 (Netlify 종료) + README 현행화 + Nano Banana 시리즈 상호 링크표 추가

## 부스 등록
🍌 나노 바나나 시리즈 3번 카드 (`nanoBananaApps[2]` in 부스 index.html)
