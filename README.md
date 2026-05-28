# Pocket Wisdom

Goorm Honam 바이브코딩 **2일차** 프로젝트 — 유명인 명언을 보여주는 **Pocket Wisdom** 명언수첩 웹앱입니다.

**저장소**: [github.com/jjsnoel/goorm-honam-pocket-wisdom](https://github.com/jjsnoel/goorm-honam-pocket-wisdom)

## 주요 기능

### 명언칸
- **519개** 명언 (`quotes.json`) + 11개 카테고리 필터 (전체, 인생, 사랑, 지혜, 용기, 평화, 성장, 행복, 시간, 희망, 노벨 수상자)
- 5초 간격 자동 슬라이드 + `<` `>` 수동 이동
- 명언마다 다른 **3가지 비주얼 테마** (종이+형광펜 / 황혼 그라데이션 / 새벽 하늘)
- **노벨 수상 분야** 배지 (평화상, 문학상, 화학상, 물리학상, 경제학상 등) + **인물 직업** 표기
- **다크 / 라이트 모드** 전환 (설정 저장)
- **SNS 공유** (Web Share API 또는 클립보드 복사)
- **PNG 저장** (현재 명언 카드 캡처, html2canvas)

### 타이머칸
- **원 드래그**로 시간 설정 (마우스·터치)
- **분 모드**: 1~60분 (1분 단위)
- **시간 모드**: 1~12시간 (1시간 단위)
- 시작 시 원이 **가득 찬 상태에서 줄어드는** 카운트다운
- 파스텔 톤 UI (피치·세이지 그라데이션)

### 공통
- 하단 탭으로 **명언칸 / 타이머칸** 전환

## 실행 방법

`fetch`로 JSON을 불러오므로 **로컬 서버**로 실행해야 합니다. `index.html`을 더블클릭만 하면 명언이 로드되지 않을 수 있습니다.

```bash
# Python
python -m http.server 5171

# 또는 Node
npx serve . -l 5171
```

브라우저에서 [http://localhost:5171](http://localhost:5171) 접속

## 파일 구성

```text
.
├── index.html              # 앱 골격
├── style.css               # 테마·캐러셀·도크·타이머 스타일
├── app.js                  # 명언·타이머·공유·PNG 로직
├── quotes.json             # 519개 명언 + 카테고리 (메인 데이터)
├── poket-wisdom-quotes.md  # 노벨 수상자 20명 원본 (생성 스크립트용)
├── scripts/
│   └── generate-quotes.mjs # quotes.json 재생성
├── 147aeb0281f640370e699d7b007ce9ca.jpg  # 디자인 레퍼런스
├── 567c7dce27ccd37eac32d41182598305.jpg
└── c74d474758b8dff38396de82b6afe586.jpg
```

## 데이터

- 앱은 **`quotes.json`** 을 불러옵니다.
- `poket-wisdom-quotes.md`는 노벨 수상자 명언 원본이며, `scripts/generate-quotes.mjs`로 JSON을 다시 만들 수 있습니다.

```bash
node scripts/generate-quotes.mjs
```

노벨 수상자 명언의 수상 분야는 각주 URL 경로로 자동 분류됩니다.

| URL 경로 | 표시 |
|----------|------|
| `/prizes/peace/` | 노벨 평화상 |
| `/prizes/literature/` | 노벨 문학상 |
| `/prizes/chemistry/` | 노벨 화학상 |
| `/prizes/economic` | 노벨 경제학상 |

## 사용 기술

- HTML5
- CSS3 (반응형, CSS 변수, 그라데이션)
- Vanilla JavaScript
- [html2canvas](https://html2canvas.hertzen.com/) (CDN, PNG 저장)

## 만든 사람

Developer: **jjs**
