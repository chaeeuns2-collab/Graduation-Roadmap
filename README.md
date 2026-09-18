# 대학원 수료 및 졸업 안내 페이지

서울과학기술대학교 일반대학원 인공지능응용학과의 수료·졸업 요건 로드맵 페이지입니다.
한국어 / English 전환을 지원하고, GitHub Pages로 무료 공개할 수 있습니다.

## 폴더 구성

| 파일 | 내용 | 고칠 일 |
|---|---|---|
| `data/content.json` | 페이지의 모든 글 (한국어·영어) | **내용을 고칠 때 이 파일만 고치면 됩니다** |
| `files/` | 첨부 파일 (우수학술대회 목록 PDF, 학위논문 제출 양식 HWP) | 새 양식으로 바꿀 때 |
| `images/technyong.png` | 테크뇽 이미지 | 거의 없음 |
| `index.html` | 페이지 디자인과 동작 | 고치지 않아도 됩니다 |
| `.nojekyll` | GitHub Pages 설정용 빈 파일 | 지우지 마세요 |

---

## 1. 처음 한 번: GitHub에 올리고 공개하기

1. **개인 이메일로 GitHub 계정을 만듭니다** (github.com → Sign up).
   퇴사 후에도 쓰려면 회사 메일이 아닌 개인 메일로 만드세요.
2. 오른쪽 위 **+ → New repository**
   - Repository name: 예) `graduation-roadmap`
   - **Public** 선택 (무료 계정은 Public 저장소만 GitHub Pages로 공개할 수 있습니다)
   - **Create repository**
3. 만들어진 저장소 화면에서 **uploading an existing file** (또는 **Add file → Upload files**) 클릭
4. 이 폴더 **안의 내용 전부**(`index.html`, `README.md`, `.nojekyll`, `data`, `files`, `images`)를 끌어다 놓고 **Commit changes**
   - `.nojekyll`처럼 점으로 시작하는 파일이 탐색기에서 안 보이면: 탐색기 **보기 → 표시 → 숨긴 항목** 체크
5. 저장소 **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / **/(root)** → **Save**
6. 1~2분 뒤 같은 화면 위쪽에 주소가 나타납니다.
   `https://<내 GitHub 아이디>.github.io/graduation-roadmap/`
   이 주소를 학생들에게 공유하면 됩니다.

---

## 2. 내용 고치기 (어디서든 브라우저만 있으면 됩니다)

1. GitHub에서 저장소 → `data` → `content.json` 열기
2. 오른쪽 위 **연필 아이콘(Edit this file)**
3. 글을 고친 뒤 **Commit changes…** → **Commit changes**
4. 1~2분 뒤 페이지에 반영됩니다 (안 보이면 새로고침).

### content.json 읽는 법

```json
"label": {
  "ko": "학위자격시험",
  "en": "Degree Qualifying Exam"
},
"body": {
  "ko": [
    "@응시자격: 3개 학기 이상 등록하고 18학점 이상 취득한 자",
    "## 석사과정 시험 면제제도",
    "- 첫 번째 항목"
  ],
  "en": [ ... ]
}
```

- `ko`는 한국어, `en`은 영어입니다.
- `facts`(핵심 수치)와 `body`(본문)는 **한 줄에 하나씩** `[ ]` 안에 적습니다.
  각 줄은 `"큰따옴표"`로 감싸고, 줄 사이에는 **쉼표(,)** 를 넣습니다. **마지막 줄 뒤에는 쉼표를 넣지 않습니다.**
- 글 안에 큰따옴표가 필요하면 `\"` 로 적습니다. (작은따옴표 `'`, `‘ ’`는 그대로 써도 됩니다.)
- **영어(`en`)를 비워 두면** (`""` 또는 `[]`) English 화면에서도 그 부분은 한국어로 보입니다.
  한국어를 고쳤는데 영어를 아직 못 고쳤다면 비워 두는 편이 옛 영어가 보이는 것보다 안전합니다.
- 고친 날짜는 `"updatedAt": "2026-09-18"` 을 직접 바꿔 주세요.

### 본문(body) 작성 규칙

| 적는 방법 | 보이는 모양 |
|---|---|
| `## 제목` | 소제목 |
| `### 제목` | 서류·세부 묶음 상자 |
| `- 내용` | 목록 (앞에 공백 2칸 이상이면 하위 목록) |
| `① 내용` | 번호 목록 |
| `@항목: 내용` | 표 형식 한 줄 |
| `※ 내용` | 노란 강조 안내 상자 |
| `* 내용` | 각주 |
| `**굵게**` | 굵은 글씨 |
| `https://…` | 자동 링크 |

핵심 수치(`facts`)는 한 줄에 `"값 | 설명"` 형식입니다.

### 단계별 설정값

| 항목 | 뜻 |
|---|---|
| `kind` | `"step"` 로드맵 단계 / `"rule"` 로드맵 아래 작은 카드 (수료 후 등록, 학과 내규) |
| `lane` | `"common"` 공통 단계(학위자격시험, 학위청구논문) / `"detour"` B 수료 트랙 전용(수료) |
| `icon` | `cert` `calendar` `rule` `talk` `thesis` `doc` `book` `star` `cap` 중 하나 |
| `link` | 바로가기 주소 (없으면 `""`) |
| `hover` | 로드맵에서 마우스를 올리면 나오는 말풍선 |
| `tip` | 테크뇽 TIP |
| `badge`, `join` | 아래 작은 카드의 윗줄 문구, 오른쪽 표시 |

순서는 `steps` 안에서 블록 순서대로입니다.

---

## 3. 첨부 파일 바꾸기

1. 저장소 → `files` 폴더 → **Add file → Upload files** 로 새 파일 올리기
2. `content.json`에서 해당 단계의 `files` 부분 수정
   ```json
   "files": [
     { "name": "새 양식.hwp", "path": "files/새 양식.hwp", "size": 82944 }
   ]
   ```
   `size`는 바이트 단위 크기이며, 모르면 `0`으로 두어도 됩니다 (크기 표시만 빠짐).
3. 옛 파일은 `files` 폴더에서 열고 휴지통 아이콘으로 지울 수 있습니다.

---

## 4. 문제가 생기면

- **페이지에 "내용 파일을 읽지 못했어요"가 뜨면**: 방금 고친 `content.json`에서 쉼표나 따옴표가 빠졌거나 남은 것입니다.
  저장소의 `content.json` → **History** 에서 직전 버전을 열어 비교하거나, 그 버전으로 되돌리면 됩니다.
- 영어 번역이나 큰 수정은 Claude 같은 AI에게 `content.json` 내용을 붙여 넣고
  "ko를 이렇게 바꾸고 en도 맞춰 번역해 줘. 줄 구조와 기호는 유지해 줘"라고 요청하면 편합니다.
  (용어: 통합정보시스템 = SUIS System, 인공지능응용학과 = Department of Applied Artificial Intelligence)

## 참고

- 이 GitHub 페이지와 claude.ai에 게시된 페이지는 **서로 자동으로 연결되지 않습니다.**
  한쪽을 고치면 다른 쪽에는 반영되지 않으니, 학생들에게 공유할 주소를 하나로 정해 그쪽을 고치세요.
- 폰트는 Google Fonts(IBM Plex Sans KR)를 사용합니다.
