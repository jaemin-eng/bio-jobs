# 단백질 설계 · 계산생물학 Job Watcher

SF Bay Area · San Diego · Boston · Washington DC(+Baltimore) 그리고 **원격** 공고를
매일 모아 웹 대시보드에 보여줍니다.

- 대시보드: `https://<GitHub아이디>.github.io/<저장소이름>/`
- 각 지역 칸에는 배우자의 **RF 사이트 공고 수**도 함께 표시됩니다
  (주소는 `docs/index.html` 의 `RF_SITE` 값에서 바꿀 수 있습니다)

## 데이터 소스

| 소스 | 커버 범위 | 비용 |
|---|---|---|
| Adzuna | 여러 채용 사이트 집계 | 무료 |
| JSearch (RapidAPI) | LinkedIn, Indeed, Glassdoor 등 | 무료 요금제 월 200회 — RF 사이트와 키를 나눠 쓰므로 **이틀에 한 번** 실행 |
| USAJOBS | NIH, NCI, FDA 등 연방 연구직 | 무료 |
| 회사 채용 페이지 | `companies.yaml` 의 70곳 | 무료 |

## 설정

저장소 Settings → Secrets and variables → Actions 에 아래를 등록합니다.
**RF 사이트와 같은 값을 그대로 넣으면 됩니다.**

`ADZUNA_APP_ID`, `ADZUNA_APP_KEY`, `RAPIDAPI_KEY`, `USAJOBS_API_KEY`, `USAJOBS_EMAIL`

Settings → Pages → Source 를 **GitHub Actions** 로 선택한 뒤,
Actions 탭에서 **Bio Job Watcher → Run workflow** 를 누르면 첫 수집이 시작됩니다.

## 커스터마이즈

- `config.yaml` : 검색어, 제목 필터, 지역/도시, 원격 포함 여부(`include_remote`)
- `companies.yaml` : 직접 연결할 회사 (group, careers 주소)
- 처음부터 다시 받고 싶으면 `data/state.json` 삭제
