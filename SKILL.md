---
name: handdrawn-ppt
description: 내 캐릭터(IP) 이미지 한 장으로 손그림 발표자료를 통째로 만든다. 주제를 리서치해서 검증된 1차 출처를 확보하고, 차트·그래프·표·흐름도·빅넘버 같은 PPT 요소를 거친 펜선 미니 낙서 스타일로 그린 뒤, 헤드라인·설명·출처를 얹어 조립한다. 순백 배경, 콩눈, 뚝뚝 끊기는 외곽선, 깔끔한 플랫 컬러. 한국어·영어 둘 다 지원. Makes a full hand-drawn slide deck from one character image — researches the topic with verified sources, then draws charts, tables, flow diagrams and big-number slides in a rough pen-doodle style. Works in Korean and English. Trigger — /handdrawn-ppt, "내 캐릭터로 발표자료 만들어줘", "손그림 PPT 만들어줘", "손그림 삽화 만들어줘", "펜 낙서 스타일로 그려줘", "아티클 삽화 뽑아줘", "hand-drawn ppt", "doodle slide deck".
---

# handdrawn-ppt — 내 캐릭터로 만드는 손그림 발표자료

캐릭터 이미지 한 장 → 자료조사 → 손그림 PPT 요소 → 완성된 발표자료/캐러셀.
**한국어·영어 둘 다 됨** (프롬프트는 원래 영어로 나가고, 주석·헤드라인 언어만 바뀐다).

화풍 원본: [EverettFish/ip_illustration_for_yourself](https://github.com/EverettFish/ip_illustration_for_yourself)
개조·확장(한국어 운용, 자료조사 단계, 표정·드리프트·팔레트 규칙): MOONGI Studio.


---

## 1. 이 스킬은 뭐가 다른가 (v1 소흑 스킬과 비교)

같은 계열의 **두 번째 버전**이다. 헷갈리지 말고 목적에 따라 골라 쓸 것.

| | v1 `ian-xiaohei-illustrations` | **v2 이 스킬** |
|---|---|---|
| 비율 | 16:9 가로 | **쓰일 자리에 맞춤** (§3-1) |
| 주인공 | 소흑(小黑) 고정 — 검정 실루엣 | **내 캐릭터** (참조 이미지로 생성) |
| 색 | 흑백 선화 + 빨강/주황/파랑 주석 | **깔끔한 플랫 컬러 채색** |
| 텍스트 | 한국어 짧은 레이블 적극 사용 | **기본 무텍스트** (예외는 §7) |
| 선 | 규정 없음 | **거친 외곽선이 합격/불합격 기준** |
| 용도 | 구조·흐름 설명도 | 의미·감정·장면 삽화 |
| 장수 | 4~8장 | **기본 5장** |

**한 줄 요약:** v1은 "설명하는 그림", v2는 "내 캐릭터가 그 얘기를 겪는 그림".

---

## 2. 스킬 시작 방법

```
/handdrawn-ppt
```
슬래시로 안 켜지면 직접 읽기:
```
~/.claude/skills/handdrawn-ppt/SKILL.md 읽고 실행해줘
```
그다음 분석할 글·링크·노션 페이지·스레드·주제를 붙여넣으면 된다.

### 내 캐릭터로 시작 (권장)
프롬프트 글자만으로는 캐릭터가 안 잡힌다. **캐릭터 이미지를 첨부**해야 한다.

```
/handdrawn-ppt
[내 캐릭터 이미지 첨부]
이 캐릭터로 그려줘. [분석할 글 또는 주제]
```

캐릭터 이미지가 없으면 §9 워크플로 A로 **캐릭터 앵커부터** 만들고 시작한다.
한 번 마음에 드는 컷이 나오면 그 컷을 락 이미지로 저장해두고 계속 재사용할 것 — 매번 새로 만들지 말 것.

---

## 3. 목표 화풍 (북극성)

**치졸하게, 작게, 여백 많이, 콩눈으로 귀엽게, 펜선은 거칠고 뚝뚝 끊기게, 색은 깔끔한 플랫으로, 글 내용과 강하게 붙게.**

핵심 프롬프트 문장 (항상 포함):

> EXTREMELY cute mini pen-doodle illustration, tiny chibi subject on a large pure-white page, naive dot-eye face, rough black ink contour, visibly hand-drawn line jitter, uneven stroke character, micro-hesitations, frequent tiny contour breaks and incomplete closures, imperfect pen control, simple clean flat color fills, very light fill misregistration, messy-cute and childlike, sparse article-relevant micro-scene.

이 문장은 **영어 원문 그대로** 넣는다. 한국어로 번역해서 넣으면 화풍이 무너진다.
프롬프트는 영어, 결과물의 맥락·레이블·기획만 한국어 — 이게 이 스킬의 한국어 운용 원칙이다.

**위 문장은 `rough` 모드용이다.** `clean` 모드면 굵은 부분
(`rough black ink contour ... imperfect pen control`)을 §4-2의 clean 문구로 갈아끼운다.
나머지(미니 구도·순백 배경·콩눈·플랫 채색)는 두 모드가 똑같다.

### 3-1. 비율은 원본 기본값(1:1) 말고 **쓰일 자리**에 맞춘다 ★

원문은 `1:1 square`가 기본이지만 그건 원작자가 블로그 본문에 쓰던 자리 기준이다.
**최종적으로 들어갈 슬롯 비율을 먼저 확인하고 거기에 맞춰 생성한다.** 잘라 쓰지 말 것 —
이 화풍은 여백이 곧 디자인이라, 크롭하면 캐릭터가 화면을 꽉 채운 것처럼 보이면서 §5 구도 규칙이 깨진다.

| 쓰일 자리 | 생성 비율 |
|---|---|
| IG 캐러셀(4:5 슬라이드)의 **가로 이미지 밴드** | **16:9** ← 가장 많이 쓰는 값 |
| 캐러셀 슬라이드 **전면(풀블리드)** | **4:5** |
| 커버처럼 살짝 낮은 밴드 | `3:2` 또는 `16:9` |
| 블로그 본문 삽화 | `1:1` (원문 기본) |
| 릴스·스토리 | `9:16` |

`nano-banana-pro` 지원값: `1:1 2:3 3:2 3:4 4:3 4:5 5:4 9:16 16:9 21:9 1:4 4:1 1:8 8:1`

프롬프트 첫 줄의 `1:1 square illustration`도 실제 비율로 같이 바꿔 쓴다
(예: `16:9 horizontal illustration`). 파라미터만 바꾸고 문장을 안 고치면 모델이 헷갈린다.

---

## 4. 선 모드 — `rough` / `clean` 둘 중 하나를 먼저 정한다 ★

원본 스킬은 "거친 선"만 정답으로 봤지만, 실제로 써보니 **쓰이는 자리에 따라 정답이 다르다.**
그래서 이 스킬은 두 모드를 지원한다. **작업 시작할 때 어느 쪽인지 먼저 확정하고, 한 덱 안에서는 절대 섞지 않는다.**

| | `rough` | `clean` |
|---|---|---|
| 느낌 | 치졸한 펜 낙서, 뚝뚝 끊긴 선 | 깔끔하고 균일한 라인, 동화책 삽화 |
| 어울리는 자리 | IG 캐러셀, 릴스, SNS 카드뉴스 | 발표자료, 강의자료, 제안서, 블로그 |
| 강점 | 피드에서 눈에 띔, 사람 손 느낌 | 가독성, 프로페셔널, 정보 밀도 높은 슬라이드 |
| 실사 인물 참조와 궁합 | 나쁨 (자꾸 clean으로 끌려감) | 좋음 |

**모드를 안 정하고 시작하면 모델이 매번 다르게 그려서 한 덱 안에서 톤이 흔들린다.**
사용자가 지정 안 하면 물어본다. 못 물어보는 상황이면 — SNS면 `rough`, 발표자료면 `clean`.

### 4-1. `rough` 모드

합격선에 있어야 하는 것:
- 눈에 보이는 손떨림 / 선 굵기·필압 불균일 / 미세한 망설임
- 곡선에서 어색하게 각지는 구간 / 짧게 끊긴 선분
- 군데군데 뚫린 윤곽 틈 / 안 닫힌 마감 몇 군데 / 겹쳐 그은 자국 약간

프롬프트에 넣을 문구:
```
rough black ink contour, visibly hand-drawn line jitter, uneven stroke character,
micro-hesitations, frequent tiny contour breaks and incomplete closures, imperfect pen control
```

**불합격:** 선이 매끄럽다 / 끊김 없이 이어진다 / 벡터 같다 → 재생성.

재생성용 수정 문구:
> The contour is too smooth. Redraw it with visibly rougher hand-controlled pen lines: more natural wobble, uneven pressure, micro-hesitations, short broken segments, tiny contour gaps, and slightly awkward curves. Do not clean up the linework. Preserve the clean flat fills and large white space. The silhouette itself must visibly read as imperfect pen doodling.

**주의:** 거칠기는 **검정 펜선**이 담당한다. 색을 지저분하게 칠해서 거칠어 보이게 만들면 안 된다.

### 4-2. `clean` 모드

선은 균일하고 부드럽게, 대신 **여전히 손으로 그린 것**이어야 한다. 벡터·클립아트로 가면 실패다.

프롬프트에 넣을 문구 (§3 북극성 문장에서 rough 관련 구절을 이걸로 교체):
```
smooth confident hand-drawn black ink contour of even weight, calm steady linework,
closed clean shapes, still clearly drawn by hand — not vector, not clip art,
no digital stroke perfection, slight organic irregularity in long curves
```

**불합격:** 선이 자로 잰 듯 완벽하다 / 베지어 곡선처럼 매끈하다 / 스톡 아이콘 같다 → 재생성.

재생성용 수정 문구:
> The linework looks vector-generated. Redraw it as a calm, confident hand-drawn ink line: even weight, closed shapes, but with slight organic irregularity so it still reads as drawn by a person. Do not add jitter or broken segments — keep it clean, just not mechanical.

**두 모드 공통:** 순백 배경 · 플랫 채색 · 콩눈 · 미니 구도 · 여백 · 캐릭터 색 독점 규칙은 그대로 적용된다.
바뀌는 건 **외곽선 처리 하나뿐**이다.

---

## 5. 채색·구도·얼굴

**채색** — 단순 플랫 채색, 깨끗한 색면, 음영 최소, 선과 색이 살짝 어긋나는 건 OK.
금지: 크레용 / 오일파스텔 / 색연필 질감 / 붓터치 / 얼룩진 채색 / 마커 줄무늬.

**캐릭터 색은 캐릭터만 쓴다.** 캐릭터 옷이 주황이면 화살표·강조 도형·배경 오브젝트에 주황을 쓰지 말 것.
안 막으면 모델이 강조색으로 주황을 계속 끌어다 쓰고, 그 순간 캐릭터가 화면에 묻힌다.
오브젝트 팔레트는 캐릭터 색을 뺀 나머지로 고정한다 — 예: 회청색(중립 오브젝트) · 빨강(핵심·나쁜 소식) · 파랑(대비·부연) · 웜그레이(소품).

**구도** — 캐릭터 + 소품이 화면의 **20~40%**만. 더 작아도 좋다. 순백 배경, 여백 크게, 보조 오브젝트 1~4개.
> "커다란 흰 종이 위에 아주 작은 귀여운 펜 낙서 하나가 툭 떨어져 있다."

금지: 화면 꽉 채운 히어로 캐릭터 / 빽빽한 인포그래픽 / 포스터 구도 / 풀프레임 배경.

**얼굴** — 콩눈·점눈, 작은 입, 필요하면 볼터치, 어색하고 귀여운 몸짓. 캐릭터 정체성상 꼭 필요한 게 아니면 애니풍 큰 눈은 쓰지 말 것.

### 5-1. 표정은 장면 감정에 맞춘다 ★ (기본 미소 금지)

생성 모델은 놔두면 **무조건 웃는 얼굴**을 그린다. 그러면 그림이 내용을 배신한다.
정리해고 얘기에 캐릭터가 방긋 웃고 있으면 그 컷은 실패다.

프롬프트에 **표정을 매번 명시**한다. "cute"만 쓰면 웃는다.

| 장면 감정 | 지정할 표정 |
|---|---|
| 불안·위기·나쁜 소식 | `flat closed mouth, eyes lowered, small worried frown, no smile` |
| 충격·당황 | `tiny open mouth, blank wide dot eyes, no smile` |
| 관찰·판단 중 | `neutral straight mouth, calm steady eyes, arms crossed, no smile` |
| 지침·체념 | `mouth a small flat line, slumped shoulders, eyes downcast` |
| 결심·전환 | `mouth firm and closed, eyes forward, chin slightly up, no smile` |
| 희망·나눔 (마지막 컷만) | `small gentle smile` |

**웃는 표정은 서사가 희망으로 넘어간 뒤에만 쓴다.** 한 캐러셀에서 미소 컷은 보통 1~2장이면 충분하다.
네거티브로 `no smile, not cheerful, not happy`를 함께 넣으면 더 잘 듣는다.

---

## 6. 참조 이미지 전략

참조 이미지는 패키지 안에 들어 있다. 별도 URL 호스팅이 필요 없다.

```
references/style_lock/
├── 01_comparison_annotated.png   비교 구도 + 손글씨 주석 밀도  ← 기본 앵커
├── 02_colorful_board.png         여러 차트가 올라간 컬러 보드
├── 03_bar_chart.png              막대차트
├── 04_table.png                  손그림 표
├── 05_flow_diagram.png           흐름도
└── 06_big_number.png             빅넘버
```

한 장으로는 화풍이 안 잡힌다. **매번 최소:**
- `01_comparison_annotated.png` — 항상 넣는다. 선 굵기·주석 밀도·팔레트가 여기서 잡힌다.
- 만들려는 **포맷과 같은 style_lock 1장** (표를 그리면 `04_table.png`)
- **내 캐릭터 참조 이미지** (정면 + 측면이면 더 안정적)
- 글에 구체적 대상이 나오면 로고 / 제품 / UI 스크린샷 / 장소 사진 추가

### 6-1. style_lock의 캐릭터는 무시시켜야 한다 ★

style_lock 이미지들에는 **제작자의 캐릭터가 들어 있다.** 그대로 두면 그 캐릭터가
사용자 캐릭터에 섞여 나온다. 프롬프트에 아래를 **반드시** 넣는다:

```
Use reference image 1 for LINE QUALITY, ANNOTATION STYLE, PALETTE and LAYOUT only.
IGNORE the character in the style references completely.
The character must come only from the character reference image(s).
```

첫 컷이 나오면 **그 컷을 새 앵커로 삼고** 이후 컷은 그것을 참조 1번에 넣는다.
그 시점부터 패키지의 style_lock은 더 안 써도 된다 (§9-1 참고).

**실측 (2026-08-09):** 위 문구를 넣고 실사 인물 레퍼런스 시트로 테스트한 결과,
style_lock의 캐릭터(단발·주황 원피스)가 전혀 섞이지 않고 참조 인물의 특징
(긴 웨이브 머리·트위드 셋업·검은 힐·흰 숄더백)만 손그림으로 옮겨졌다. 이 문구는 실제로 듣는다.

### 6-2. 실사 사진을 캐릭터 참조로 쓸 때

실사 참조를 넣으면 **선이 정갈해지고 얼굴 디테일이 늘어나는 쪽으로 끌린다.**
(속눈썹·콧대가 생기고, 외곽선이 매끄러워진다.) 그래서 실사 참조를 쓸 때는:

- §4 재생성 문구를 **처음부터** 프롬프트에 같이 넣는다
- `simplify the face to the doodle language: two small black dot eyes, tiny mouth, faint blush`
- `no photographic shading, no realistic rendering, no eyelashes, no nose shading`
- 캐릭터가 커지는 경향도 있으니 `draw her TINY`를 명시

제품·로고 참조를 넣어도 **화풍 락은 유지**한다. 번들거리는 제품 사진 한 장 때문에 그림 전체가 번들거리면 실패다.

---

## 7. 한국어 텍스트 정책 ★ 한국어판 핵심

**원문은 "기본 무텍스트"지만 한국어판은 반대다. 주석을 적극적으로 쓴다.**

이유: 이 그림들이 실제로 쓰이는 자리는 **손그림 발표자료·카드뉴스**다.
그림 안에 한국어 주석과 숫자가 들어가야 그림 한 장이 슬라이드 한 장 몫을 한다.
주석이 없으면 예쁜 삽화일 뿐이고, 정보는 전부 바깥 텍스트가 나르게 된다 — 그러면 이 스킬을 쓸 이유가 없다.
v1 소흑 스킬이 "더 귀엽다"고 느껴졌던 이유도 이 손글씨 주석 밀도였다.

**목표 밀도: 컷당 주석 3~6개.** 색은 빨강(핵심·나쁜 소식) / 파랑(대비·부연) / 검정(중립) 3색으로 제한.

### 7-1. 한글 주석 안전 규칙

생성 모델은 긴 한글을 깨뜨린다. 짧으면 잘 나온다. 그래서 제약이 있다.

- **2~6자.** 문장 금지. 조사 붙은 어절 금지.
- 좋은 예: `벌써 넘었다` `빈 골문` `공 놓침` `여기서 막힘` `조 3위 탈락`
- 나쁜 예: `이번 달에 결국 이렇게 됐다`(길다) / `클릭률이`(조사) / 줄바꿈된 문장
- **숫자·영문은 거의 안 깨진다.** `124,000명` `-13%` `+62%` `92M` `2026` — 수치는 망설이지 말고 그림 안에 넣을 것.
- 손글씨 느낌으로 오브젝트 **옆에** 작게. 제목처럼 좌상단에 박지 말 것.
- 화살표·밑줄·동그라미 같은 손그림 기호를 주석과 같이 쓰면 관계가 읽힌다.

### 7-2. 검수 (필수)

생성 후 글자를 **눈으로 읽어라.** 자모가 깨졌거나 없는 글자가 만들어졌으면
그 컷은 폐기하고 다시 뽑는다. "대충 비슷하니까" 통과 금지.
두 번 연속 같은 단어가 깨지면 그 단어를 숫자·영문으로 치환하거나 빼고 재생성한다.

### 7-2. 한국어 원문 → 영어 프롬프트 변환

글은 한국어로 읽고, 장면 묘사는 **영어로 번역해서** 프롬프트에 넣는다.
한국 고유 맥락(김밥, 배달 오토바이, 한옥, 지하철 노선도, 아파트 등)은 영어로 풀어 쓴다.
예: `한강 치킨` → `fried chicken box and picnic mat by a wide river`

한국인·한국 아이돌·실존 인물·실존 브랜드 건물 이름은 프롬프트에 **직접 쓰지 않는다.**
형태·재료·맥락으로 서술한다.

---

## 8. 생성 툴 라우팅 (한국어판 — 원문의 Mode A/B/C 대체)

원문 기본 모델은 `gpt-image-2`다. 이 워크스페이스에서는 순서가 다르다.

**Mode A — nano-banana-pro (기본)**
```bash
python "~/.claude/skills/nano-banana-pro/scripts/generate_image.py" \
  --prompt "<영어 프롬프트>" \
  -i "<내 캐릭터.png>" \
  -i "<references/style_lock/01_docs_reader_style.png>" \
  -i "<references/style_lock/02_searcher_style.png>" \
  --aspect-ratio 1:1 \
  -o "<프로젝트>/illustrations/01-주제.png"
```
참조 이미지 여러 장을 `-i`로 반복 전달 → 캐릭터 락 + 화풍 락 동시 적용.
초안은 flash, 최종은 pro.

**Mode B — Higgsfield CLI** (`hf`) — image-to-image가 필요하거나 nano banana가 화풍을 못 잡을 때.
`--output` 옵션 없음, `| tail` 금지(result_url 잘림), 동시 4잡 제한.

**Mode C — gpt-image-2 API** — 원문 기본 경로. `examples/api_fallback/` 의 curl 예시 사용.

**Mode D — 생성 능력 없는 환경** — 지어내지 말고 그대로 말한다:
> 지금 환경에선 이미지 생성을 직접 못 돌려. 최종 프롬프트 + 참조 이미지 목록 + API 호출 템플릿을 정리해줄게.

그리고 ① 최종 프롬프트 ② 참조 이미지 목록 ③ curl 템플릿 ④ 공식 문서 링크를 낸다.
**어떤 환경에서도 "못 해요"로 끝내지 않는다.**

### 유료 생성 게이트 ★
이미지를 실제로 뽑기 전에 **몇 장 × 어떤 모델 × 예상 비용**을 말하고 승인을 받는다.
승인 없이 배치로 돌리지 않는다.

---

## 9. 워크플로 A — 내 캐릭터(IP) 앵커 만들기

**입력:** 캐릭터 참조 이미지 1장 이상.

**락 걸 항목:** 헤어스타일/실루엣 · 얼굴 단서 · 모자·안경·액세서리 · 옷 · 팔레트 · 시그니처 소품 · 성격과 표정 범위 · **절대 바뀌면 안 되는 요소**.

**산출물:**
1. 캐릭터 앵커 설명 (짧게, 한국어)
2. 전신 앵커 이미지 1장
3. (선택) 정면/측면/후면 턴어라운드

### 9-1. 캐릭터 드리프트 방지 ★ (실전에서 제일 자주 터지는 문제)

시리즈로 여러 장 뽑으면 어느 한 장만 슬쩍 다른 사람이 된다. 원인은 두 가지다.

**(1) 편집 체인 누적 — 자기 출력을 다시 참조로 넣지 말 것**

`A → A를 참조로 A' → A'을 참조로 A''` 로 가면 오차가 복리로 쌓인다.
edit 모드는 기존 이미지를 보존하려는 성질이 있어서 **틀어진 얼굴도 그대로 보존**한다.

- 모든 컷은 **승인된 캐릭터 락 컷 1장**에서 각각 새로 뽑는다. 컷끼리 참조로 물리지 않는다.
- 수정이 필요하면 그 컷의 이전 버전을 참조에서 **완전히 빼고** 락 컷 기준으로 다시 그린다.
- **같은 컷을 두 번 넘게 편집했는데 여전히 어긋나면, 편집을 포기하고 처음부터 재생성한다.** 세 번째 편집은 거의 항상 실패한다.
- 참조 1번 슬롯에는 항상 락 컷을 놓는다.

**(2) 캐릭터가 정면·크게 나오는 컷은 재해석 위험이 크다**

뒷모습·옆모습·작게 나오는 컷은 잘 유지되는데, **정면 + 큰 사이즈**면 모델이 얼굴 비율을 새로 상상한다.
장면 지시(표 내용, 차트 수치 등)가 길어질수록 캐릭터 묘사가 묻혀서 더 심해진다.

정면 컷에는 **수치화된 캐릭터 락 문구**를 프롬프트에 그대로 넣는다:
```
head about one third of total height / bob stops at JAW level like a short helmet /
small round face, not long or angular / two small black dot eyes set close together /
pink round blush / almost no visible neck / short stubby arms and legs
```

**검수:** 컷을 다 뽑은 뒤 전부 나란히 놓고 얼굴만 훑어라. 한 장이라도 "다른 사람"으로 읽히면 그 컷만 재생성.

앵커 구도는 작게 · 여백 많이 · 거친 끊긴 펜선 · 깔끔한 채색 · 단순한 얼굴.
앵커 PNG는 프로젝트의 `outputs/character/`에 저장하고, 이후 모든 컷에서 **같은 파일을 참조로 재사용**한다.

---

## 9-2. 워크플로 0 — 자료조사 (데이터가 들어가는 자료면 **무조건 먼저**) ★

숫자·통계·전망이 한 장이라도 들어가면 **그리기 전에 조사부터 한다.**
그림 안 손글씨로 박힌 숫자는 나중에 못 고친다. 틀리면 그 컷을 통째로 다시 뽑아야 하고($),
발행 뒤에 틀리면 계정 신뢰가 날아간다. **검증 안 된 수치는 그림에 넣지 않는다.**

### 출처 등급 — 위에서부터 쓴다

1. **기관 1차 원문** — 보고서 PDF, 공식 보도자료, 연구소 발행 페이지, 라이브 대시보드
2. **주요 매체 보도** — 1차 자료를 인용한 기사 (인용 대상이 명시된 것만)
3. **블로그·요약 사이트** — ❌ **단독 근거 금지.** 방향 잡는 용도로만. 여기서 본 숫자는
   반드시 1차 출처로 되짚어 확인한 뒤에 쓴다.

### 반드시 확인할 것

- **보고서 연도.** 「Future of Jobs Report **2025**」(2025.1 발간, 2030 전망)를 "2026년판"으로
  쓰면 그게 첫 번째 반박 지점이 된다. 발간연도와 전망연도는 다른 것이다.
- **표본과 방법.** "노동자 460만 명 / 730개 직군", "27개국 구인공고 10억 건" —
  표본을 같이 적으면 반박이 거의 안 들어온다.
- **라이브 수치는 직접 열어서 읽는다.** 인터랙티브 대시보드는 `WebFetch`로 못 읽히는 경우가 많다.
  그럴 땐 브라우저 도구로 실제 페이지를 열어 숫자를 눈으로 확인하고, **조회 날짜를 같이 적는다.**
- **매체마다 숫자가 다르면 단정하지 않는다.** 대신 **비교 형태**로 쓴다.
  ("12만 4천 명" ❌ → "올해 누적이 작년 한 해 전체를 넘었다" ✅)
  비교는 출처가 흔들려도 안 깨진다.
- **반론이 있는 주제면 반론도 넣는다.** 한 컷을 통째로 반론에 쓰는 게 신뢰를 제일 크게 올린다.
  "아직 논쟁 중" 이라고 쓰는 쪽이 확정처럼 파는 쪽보다 강하다.

### 출처는 슬라이드에 박는다

캡션에만 적지 말고 **그림 바로 밑에** 넣는다. 형식:

```
기관명 「보고서명」 발간연월 · 저자 · 표본
예) Stanford Digital Economy Lab 「Canaries in the Coal Mine?」 2025.11
    Brynjolfsson·Chandar·Chen · ADP 급여데이터 460만 명 / 730개 직군
```

손글씨체 말고 **인쇄체(Noto Sans KR 7~8px 회색)** 로 쓴다.
손글씨=내 말 / 인쇄체=남의 자료 — 이 대비 자체가 신뢰 신호다.

### 조사 결과 넘기기

조사가 끝나면 **팩트 표**를 먼저 만들고 사용자에게 확인받은 뒤 그림에 들어간다.

| 층 | 팩트 | 출처 | 그림에 넣을 표기 |
|---|---|---|---|
| 현상 | … | … | `125,809명` |
| 원인 | … | … | `-13%` |

**모르면 지어내지 말고 "확인 못 했다"고 말한다.** 추정치를 그림에 박는 건 금지.

---

## 10. 워크플로 B — 글 삽화 뽑기

**기본 5장.** 사용자가 장수를 지정하면 그걸 따른다.

문단 순서대로 기계적으로 자르지 말고, 글에서 제일 센 시각적 개념을 뽑는다.

**5컷 역할 패턴:**
1. 전체 조망 / 상황 세팅
2. 고민 / 준비 / 긴장
3. 핵심 행동 / 전환점
4. 구조 / 은유 / 관계
5. 판단 / 결론 / 감정 착지

### 의미 결합 규칙 (하드)
모든 컷은 글의 **특정 문장·사건**에 1:1로 대응해야 한다.

좋은 예: 협회가 절차 생략 → 면접 의자가 텅 빈 채 도장만 찍히는 장면
나쁜 예: 로봇 + 노트북 + 반짝이 / 아무 글에나 붙는 장식컷

장식과 의미가 충돌하면 **의미가 이긴다.**

---

## 11. 검수 체크리스트

생성 후 아래를 순서대로 본다. 하나라도 걸리면 재생성.

- [ ] **선이 지정한 모드와 맞는가** (§4 — 제일 먼저 본다)
      · `rough`면 매끄럽지 않은가 · `clean`이면 벡터처럼 기계적이지 않은가
- [ ] 캐릭터가 화면의 20~40% 이내로 작은가
- [ ] 배경이 순백인가 (회색기·질감·그라데이션 없음)
- [ ] 채색이 플랫하고 깨끗한가 (크레용·붓터치 아님)
- [ ] 이 컷이 글의 어느 문장인지 한 줄로 말할 수 있는가
- [ ] 한글이 들어갔다면 **글자가 안 깨졌는가** (§7-1)
- [ ] 캐릭터가 앞 컷과 같은 사람인가 (헤어·옷·팔레트)
- [ ] 예시 참조 이미지 구도를 그대로 베끼지 않았는가

---

## 12. 저장 규칙

```
<프로젝트>/outputs/character/     캐릭터 앵커·턴어라운드
<프로젝트>/illustrations/         본편 삽화
  01-<주제>.png
  02-<주제>.png
```
원본 생성 파일은 남긴다. 명시적 요청 없이 기존 에셋을 덮어쓰지 않는다.
산출물은 워크트리 안이 아니라 부모 프로젝트 폴더에 저장한다.

---

## 13. 프롬프트 템플릿

```
<비율> illustration, EXTREMELY cute mini pen-doodle illustration, tiny chibi
subject on a large pure-white page, naive dot-eye face,
<선 모드 문구 — §4-1 rough 또는 §4-2 clean 중 하나를 그대로 붙인다>,
simple clean flat color fills, very light fill misregistration, messy-cute and
childlike, sparse article-relevant micro-scene.

Character: [락 걸린 캐릭터 정체성 — 영어]
Scene:     [글의 딱 한 가지 개념/사건/은유 — 영어]
Objects:   [핵심 보조 오브젝트 1~4개 — 영어]

Hard constraints:
- subject stays mini, lots of empty white space
- linework must match the chosen mode (§4); never vector or clip-art
- if it drifts to the other mode, regenerate
- clean flat fills, no crayon/oil-pastel texture
- dot-eye / simple-face language
- strong semantic connection to the article
- no text in the image
```

한글 레이블이 꼭 필요할 때만 마지막 줄을 교체:
```
- only these Korean labels, handwritten, tiny, beside the object: "실패", "여기서 막힘"
```

---

## 14. 최종 원칙

**작고, 치졸하고, 거친 펜선에, 선이 군데군데 끊겨 있고, 콩눈이고, 여백이 넓은 그림.
못 그려서 귀엽고 — 글이 하려는 말을 진짜로 해서 쓸모 있는 그림.**
