# Godius 글로벌 번역 피드백 운영 계획

이 문서는 Godius 글로벌 서비스의 번역 품질을 빠르게 개선하기 위해 왜 공개 번역 피드백을 시작하는지, 왜 GitHub에 번역 JSON을 올리는지, 유저 제보를 어떻게 받고 검수해서 실제 패치에 반영할지 정리한 운영 문서입니다.

## 1. 시작 배경

글로벌 런칭 이후 해외 유저 리뷰와 플레이 영상을 통해 Godius 같은 올드스쿨 MMORPG를 좋아하는 유저층이 해외에도 일정 수 있다는 것을 확인했다.

다만 런칭 초반 기준으로 아래 문제가 반복적으로 보이고 있다.

- 튜토리얼과 게임 내 정보가 부족해서 신규 해외 유저가 직업, 스탯, 스킬, 사냥터를 이해하기 어렵다.
- 영어 번역 품질이 낮아 게임 전체가 준비되지 않은 인상을 준다.
- 일본어권 유저는 과거 서비스에서 익숙했던 고유명사와 현재 번역이 달라 낯설게 느끼고 있다.
- 글로벌 유저는 런칭 초반의 빠른 소통, 피드백 수렴, 로드맵 제시를 기대한다.
- 번역 문제는 단순 문장 품질 문제가 아니라 게임의 신뢰도와 첫인상을 직접 떨어뜨린다.

특히 `suryeon for slime` 같은 어색한 번역은 유저 입장에서 게임이 검수되지 않은 상태로 출시된 것처럼 보이게 만든다. AI 번역 자체가 문제라기보다, 번역 후 검수와 용어 통일이 부족한 것이 문제다.

따라서 번역 품질 개선은 단순한 문구 수정 작업이 아니라 글로벌 런칭 초반의 신뢰 회복 작업으로 봐야 한다.

## 2. 목표

이번 번역 피드백 운영의 목표는 다음과 같다.

- 해외 유저가 발견한 어색한 번역과 오역을 빠르게 수집한다.
- 영어, 일본어를 우선 개선하되 11개 언어 전체를 공개 제보 대상으로 둔다.
- 과거 서비스에서 사용된 고유명사, 아이템명, 스킬명, 몬스터명, NPC명, 맵 이름을 최대한 회수한다.
- 유저가 "운영팀이 문제를 인지했고 실제로 고치고 있다"는 신호를 받게 한다.
- 번역 개선 과정을 투명하게 보여주고, 커뮤니티 참여를 유도한다.
- 내부 개발 소스는 공개하지 않고 번역 파일만 공개해 안전하게 협업한다.

## 3. 왜 GitHub에 올리는가

GitHub에 번역 JSON을 공개하는 이유는 다음과 같다.

### 3.1 변경 이력을 남길 수 있다

번역 파일은 한 번 고치고 끝나는 자료가 아니다. 누가 어떤 문구를 왜 바꿨는지 추적할 수 있어야 한다.

GitHub를 사용하면 다음이 가능하다.

- 변경 전후 비교
- Pull Request 단위 검토
- 문제 발생 시 이전 버전 확인
- 언어별 수정 이력 보존
- 커뮤니티 기여 내역 확인

### 3.2 개발 소스 없이 번역만 공개할 수 있다

현재 공개 저장소에는 클라이언트 전체 소스가 아니라 번역 JSON만 올라간다.

공개 대상:

- `strings/*.json`
- 번역 참여 안내 문서
- Google Form 운영 가이드
- 번역 운영 계획 문서

비공개 대상:

- 클라이언트 소스
- 서버 소스
- 패킷 구조
- DB 정보
- 빌드 산출물
- 내부 운영툴

이렇게 분리하면 보안 부담 없이 유저 피드백을 받을 수 있다.

### 3.3 고급 유저가 직접 수정할 수 있다

GitHub 사용이 익숙한 유저는 JSON을 직접 고쳐 Pull Request를 보낼 수 있다.

이 방식은 특히 다음에 유리하다.

- 여러 문구를 한 번에 고치는 경우
- 일본어 고유명사 전체를 정리하는 경우
- 특정 언어 담당자가 반복적으로 기여하는 경우
- 기존 번역과 제안 번역의 diff를 명확히 보고 싶은 경우

### 3.4 공개적인 개선 의지를 보여준다

글로벌 런칭 초반에는 실제 개선뿐 아니라 "개선하겠다는 태도"도 중요하다.

공개 저장소는 유저에게 다음 메시지를 준다.

- 번역 문제를 인지하고 있다.
- 제보를 받을 공식 창구가 있다.
- 변경 사항이 공개적으로 추적된다.
- 유저 의견이 실제 파일에 반영될 수 있다.

## 4. 왜 Google Form도 같이 쓰는가

GitHub만 쓰면 참여 장벽이 높다. 모든 유저가 GitHub 계정을 가지고 있거나 Pull Request를 보낼 수 있는 것은 아니다.

따라서 운영 구조는 아래처럼 나누는 것이 좋다.

| 참여자 유형 | 권장 채널 |
| --- | --- |
| 일반 유저 | Google Form |
| GitHub 사용 가능 유저 | Pull Request |
| 짧은 오타 제보 | Google Form |
| 고유명사 대량 정리 | Pull Request |
| 스크린샷 기반 제보 | Google Form |
| 반복 기여자 | Pull Request 또는 언어별 리뷰어 |

Google Form은 공식 번역 제보함이고, GitHub는 실제 번역 파일 작업장이다.

## 5. 현재 저장소 구조

공개 GitHub 저장소:

https://github.com/griffith06/godius

현재 번역 파일은 클라이언트의 아래 폴더에서 가져온다.

```text
nclient/Bin/Localize/strings/
```

GitHub 저장소에는 아래 구조로 반영한다.

```text
godius/
  README.md
  read.md
  FORM_GUIDE_ko.md
  LOCALIZATION_OPERATION_ko.md
  strings/
    de.json
    en.json
    es.json
    fr.json
    ja.json
    ko.json
    pl.json
    pt-BR.json
    ru.json
    zh-CN.json
    zh-TW.json
```

초기에는 일반 문자열과 UI 문자열이 `파일명.json`, `ui_파일명.json`처럼 나뉘어 있었으나, 유저 입장에서 더 직관적인 구조가 필요해 언어별 단일 JSON으로 합쳤다.

현재 GitHub에 올라간 파일은 합쳐진 11개 언어 JSON이다.

| 언어 | 파일 |
| --- | --- |
| 한국어 | `ko.json` |
| 영어 | `en.json` |
| 일본어 | `ja.json` |
| 중국어 간체 | `zh-CN.json` |
| 중국어 번체 | `zh-TW.json` |
| 독일어 | `de.json` |
| 스페인어 | `es.json` |
| 프랑스어 | `fr.json` |
| 폴란드어 | `pl.json` |
| 포르투갈어 브라질 | `pt-BR.json` |
| 러시아어 | `ru.json` |

## 6. 유저에게 안내할 핵심 메시지

유저 공지에서 전달해야 할 핵심은 아래 네 가지다.

1. 번역 품질 문제가 있다는 것을 인지했다.
2. 커뮤니티 제보를 받아 빠르게 개선하겠다.
3. 제보는 Google Form과 GitHub Pull Request로 받는다.
4. 접수된 내용은 내부 검수 후 순차적으로 패치에 반영한다.

중요한 점은 "무조건 유저가 고쳐달라"가 아니라 "운영팀이 책임지고 검수하되, 커뮤니티의 도움을 공식적으로 받겠다"는 톤이어야 한다.

## 7. Google Form 세팅 방식

Google Form은 가능하면 개인 계정보다 회사 또는 프로젝트 공용 Google 계정으로 만드는 것이 좋다.

개인 계정으로 먼저 만들 경우에도 아래 설정을 권장한다.

- 공동 편집자로 운영자 1명 이상 추가
- 응답 스프레드시트를 운영팀에 공유
- 이메일 수집 끄기
- 조직 내부 사용자 제한 끄기
- 파일 업로드 끄기
- 스크린샷은 파일 업로드 대신 이미지 링크로 받기

파일 업로드를 켜면 제보자에게 Google 로그인이 필요할 수 있다. 글로벌 유저에게는 참여 장벽이 되므로 피하는 편이 좋다.

### 7.1 폼 제목

```text
Godius Translation Feedback
```

### 7.2 폼 설명

```text
Help us improve Godius localization. Please report awkward translations, incorrect terms, item names, skill names, monster names, NPC names, and map names.

If you know the old official name from a previous service version, please include it.
```

### 7.3 질문 구성

| 질문 | 형식 | 필수 | 목적 |
| --- | --- | --- | --- |
| Language | 드롭다운 | 예 | 언어 분류 |
| Category | 객관식 | 예 | UI, 튜토리얼, NPC, 아이템 등 분류 |
| Current text | 단답형 또는 장문형 | 예 | 현재 게임 내 문구 |
| Suggested text | 장문형 | 예 | 제안 번역 |
| Where did you see it? | 장문형 | 예 | 위치 설명 |
| Reason | 체크박스 | 예 | 오역, 어색함, 고유명사 오류 등 |
| Screenshot link | 단답형 | 아니오 | 이미지 링크 |
| Nickname for credits | 단답형 | 아니오 | 패치노트 크레딧용 |
| Contact | 단답형 | 아니오 | 추가 확인용 |
| Consent | 체크박스 | 예 | 번역 사용 동의 |

### 7.4 응답 스프레드시트 검수 컬럼

Google Sheets에는 기본 응답 컬럼 오른쪽에 아래 내부 관리 컬럼을 추가한다.

```text
Status
Reviewer
Final text
Internal note
Applied version
```

상태값은 아래처럼 운용한다.

```text
Pending
Accepted
Modified
Rejected
Applied
```

## 8. GitHub Pull Request 운영 방식

GitHub에서는 유저가 `strings/` 안의 언어별 JSON을 수정해 Pull Request를 보낼 수 있다.

### 8.1 수정 규칙

- JSON key는 변경하지 않는다.
- 번역 text value만 수정한다.
- `%s`, `%d`, `%u`, `{0}` 같은 placeholder를 삭제하거나 순서를 깨지 않는다.
- `\n` 줄바꿈을 유지한다.
- `<green>`, `<orange>`, `<red>`, `<blue>` 같은 색상 태그를 유지한다.
- 아이템명, 스킬명, NPC명, 몬스터명, 맵 이름은 근거 없이 임의 변경하지 않는다.
- UI에 들어가는 짧은 문구는 너무 길어지지 않게 한다.

### 8.2 Pull Request 검수 기준

Pull Request는 바로 반영하지 않고 내부 검수를 거친다.

검수 시 확인할 것:

- JSON 파싱이 정상인지
- placeholder가 유지됐는지
- 색상 태그가 유지됐는지
- 같은 용어가 다른 문구와 충돌하지 않는지
- UI 영역에 들어가기 너무 긴 문구는 아닌지
- 고유명사가 과거 공식 명칭 또는 커뮤니티에서 통용되는 명칭과 맞는지
- 번역 제안이 지나치게 의역되어 게임 시스템 의미를 바꾸지 않는지

## 9. 내부 반영 플로우

권장 운영 플로우는 다음과 같다.

```text
1. 유저가 Google Form 또는 GitHub PR로 제보
2. 운영자가 중복 제보와 명백한 오류를 정리
3. 언어별 검수자가 Accepted, Modified, Rejected 결정
4. 확정 문구를 JSON에 반영
5. JSON 파싱과 placeholder 검증
6. 클라이언트 Bin/Localize/strings에 반영
7. 게임 내 주요 화면에서 표시 확인
8. 패치에 포함
9. 패치노트에 커뮤니티 번역 개선 반영 공지
```

## 10. 1주일 집중 운영안

런칭 초반에는 상시 접수보다 "집중 개선 기간"으로 공지하는 것이 효과적이다.

권장 이름:

```text
Godius Global Translation Feedback Week
```

운영 기간:

```text
7일
```

우선순위:

1. 영어
2. 일본어
3. 튜토리얼과 초반 UI
4. 아이템, 스킬, 몬스터, NPC, 맵 고유명사
5. 나머지 언어

집중 기간 종료 후에는 1차 번역 개선 패치를 내고, 이후 상시 제보로 전환한다.

## 11. 패치노트 작성 방향

패치노트에는 단순히 "번역 수정"이라고 쓰기보다 커뮤니티 참여를 명시하는 것이 좋다.

예시:

```text
Translation improvements based on community feedback have been applied.

Thank you to all players who reported awkward wording, incorrect names, and localization issues. We will continue reviewing submitted feedback and improving localization in future updates.
```

한국어 예시:

```text
커뮤니티 제보를 바탕으로 번역 개선 사항을 반영했습니다.

어색한 문구, 잘못된 고유명사, 현지화 문제를 제보해 주신 모든 플레이어분들께 감사드립니다. 접수된 피드백은 계속 검수하여 이후 업데이트에도 순차 반영하겠습니다.
```

## 12. 공지 초안

### 12.1 한국어

```text
가디우스 글로벌 번역 품질 개선을 위해 번역 제보를 받습니다.

어색한 번역, 잘못된 고유명사, 아이템명, 스킬명, 몬스터명, NPC명, 맵 이름을 발견하셨다면 아래 폼으로 제보해 주세요.

과거 서비스에서 사용되던 공식 명칭을 알고 계신 분들의 제보를 특히 환영합니다. 접수된 내용은 내부 검수 후 순차적으로 반영하겠습니다.

Google Form: TODO
GitHub: https://github.com/griffith06/godius
```

### 12.2 English

```text
We are collecting translation feedback to improve Godius localization.

If you find awkward wording, mistranslations, incorrect names, item names, skill names, monster names, NPC names, or map names, please submit them through the form below.

Feedback from players who remember official names from previous service versions is especially welcome. All submissions will be reviewed before being applied.

Google Form: TODO
GitHub: https://github.com/griffith06/godius
```

### 12.3 Japanese

```text
Godius の翻訳品質を改善するため、翻訳フィードバックを募集します。

不自然な表現、誤訳、固有名詞、アイテム名、スキル名、モンスター名、NPC名、地名などで気になる点があれば、下記フォームからお知らせください。

過去サービスで使われていた公式名称をご存じの方からの情報を特に歓迎します。いただいた内容は確認後、順次反映します。

Google Form: TODO
GitHub: https://github.com/griffith06/godius
```

## 13. 운영 시 주의점

### 13.1 모든 제보를 그대로 반영하지 않는다

유저 제보는 매우 유용하지만, 모든 제안을 그대로 넣으면 용어가 흔들릴 수 있다. 최종 반영은 반드시 내부 검수자가 결정한다.

### 13.2 고유명사는 별도 용어집으로 관리한다

특히 일본어는 과거 서비스 명칭과 현재 번역이 충돌할 수 있다. 아이템, 스킬, 몬스터, NPC, 맵 이름은 별도 용어집으로 분리해 관리하는 것이 좋다.

추가 예정 파일 예시:

```text
GLOSSARY.md
glossary/ja.md
glossary/en.md
```

### 13.3 UI 길이를 확인한다

번역이 자연스러워도 버튼, 탭, 작은 패널에 들어가지 않으면 실제 게임에서는 문제가 된다. UI 문구는 의미와 길이를 함께 봐야 한다.

### 13.4 placeholder와 태그를 반드시 검증한다

`%s`, `%d`, `<green>` 같은 요소가 깨지면 게임 내 출력이 망가지거나 런타임 문제가 생길 수 있다. 자동 검증 스크립트를 두는 것이 좋다.

### 13.5 스팸과 장난 제보를 예상한다

공개 폼은 스팸이 들어올 수 있다. 다만 초반에는 참여 장벽을 낮추는 것이 더 중요하므로, 로그인 강제보다 내부 필터링으로 대응하는 편이 낫다.

## 14. 이후 개선 방향

1차 운영 후에는 아래를 추가하는 것이 좋다.

- 언어별 용어집
- 번역 상태표
- 많이 제보된 문구 목록
- 초반 튜토리얼 전용 검수표
- UI 길이 초과 문구 체크
- placeholder 자동 검증 스크립트
- Crowdin, Weblate 같은 번역 플랫폼 도입 검토

GitHub와 Google Form만으로도 초기 대응은 가능하다. 다만 제보량이 많아지고 언어별 검수자가 늘어나면 전문 번역 플랫폼을 붙이는 편이 장기적으로 낫다.

## 15. 최종 운영 방향

이번 작업의 핵심은 번역 JSON을 공개하는 것 자체가 아니다.

핵심은 글로벌 유저에게 아래 신호를 주는 것이다.

- 문제를 인지했다.
- 공식 제보 창구를 열었다.
- 커뮤니티 의견을 실제 패치에 반영하겠다.
- 번역 품질을 지속적으로 개선하겠다.

런칭 초반에는 완벽한 시스템보다 빠른 반응과 명확한 운영 흐름이 더 중요하다. GitHub 공개 저장소와 Google Form은 그 흐름을 만들기 위한 첫 단계다.
