# Google Form 운영 가이드

## 계정

가능하면 개인 계정보다 회사 또는 프로젝트 공용 Google 계정으로 만드는 것을 권장합니다.

개인 계정으로 먼저 만들 수는 있지만, 아래 설정을 해두세요.

- 공동 편집자로 운영자 1명 이상 추가
- 응답 스프레드시트 공유 권한을 운영팀에 부여
- 이메일 수집 끄기
- 조직 내부 사용자로 제한 끄기
- 파일 업로드는 끄기

파일 업로드를 켜면 제보자가 Google 로그인을 해야 하는 경우가 많습니다. 글로벌 유저에게는 장벽이 되므로 스크린샷은 "이미지 링크" 입력칸으로 받는 편이 좋습니다.

## 폼 제목

Godius Translation Feedback

## 폼 설명

Help us improve Godius localization. Please report awkward translations, incorrect terms, item names, skill names, monster names, NPC names, and map names.

If you know the old official name from a previous service version, please include it.

## 질문 구성

1. Language
   - 형식: 드롭다운
   - 필수: 예
   - 선택지: English, Japanese, Korean, Simplified Chinese, Traditional Chinese, German, Spanish, French, Polish, Portuguese (Brazil), Russian, Other

2. Category
   - 형식: 객관식
   - 필수: 예
   - 선택지: UI, Tutorial, NPC dialogue, Item, Skill, Monster, Map, System message, Quest/Event, Other

3. Current text
   - 형식: 단답형 또는 장문형
   - 필수: 예
   - 설명: Copy the current in-game text exactly if possible.

4. Suggested text
   - 형식: 장문형
   - 필수: 예
   - 설명: Please write the corrected or more natural translation.

5. Where did you see it?
   - 형식: 장문형
   - 필수: 예
   - 설명: Menu name, NPC name, map name, quest step, or approximate location.

6. Reason
   - 형식: 체크박스
   - 필수: 예
   - 선택지: Mistranslation, Awkward wording, Wrong proper noun, Inconsistent term, Grammar issue, Too long for UI, Missing context, Other

7. Screenshot link
   - 형식: 단답형
   - 필수: 아니오
   - 설명: Paste an image link if available. Do not upload files here.

8. Nickname for credits
   - 형식: 단답형
   - 필수: 아니오
   - 설명: Optional. We may credit contributors in patch notes.

9. Contact
   - 형식: 단답형
   - 필수: 아니오
   - 설명: Optional Discord, X, email, or GitHub ID if we need to ask a question.

10. Consent
   - 형식: 체크박스
   - 필수: 예
   - 선택지: I agree that my suggested translation may be used in Godius.

## Google Sheets 검수 컬럼

응답 스프레드시트에 아래 컬럼을 오른쪽에 추가하세요.

- Status
- Reviewer
- Final text
- Internal note
- Applied version

상태값은 아래처럼 쓰면 충분합니다.

- Pending
- Accepted
- Modified
- Rejected
- Applied

## 운영 순서

1. Google Form과 GitHub 저장소를 동시에 공지합니다.
2. 유저가 직접 게임에서 번역을 확인할 수 있도록 `LOCALIZE_OVERRIDE_GUIDE.md`도 함께 안내합니다.
3. 일반 유저는 Form으로 받고, GitHub 사용자는 Pull Request로 받습니다.
4. 매일 1회 이상 Sheets에서 중복 제보를 정리합니다.
5. 언어별로 `Accepted` 또는 `Modified` 상태를 고릅니다.
6. 내부 검수자가 JSON에 반영합니다.
7. 패치노트에 "Translation improvements based on community feedback"로 공지합니다.

## 한국어 공지 초안

가디우스 글로벌 번역 품질 개선을 위해 번역 제보를 받습니다.

어색한 번역, 잘못된 고유명사, 아이템명, 스킬명, 몬스터명, NPC명, 맵 이름을 발견하셨다면 아래 폼으로 제보해 주세요.

과거 서비스에서 사용되던 공식 명칭을 알고 계신 분들의 제보를 특히 환영합니다. 접수된 내용은 내부 검수 후 순차적으로 반영하겠습니다.

Google Form: TODO  
GitHub: https://github.com/griffith06/godius
Local testing guide: https://github.com/griffith06/godius/blob/main/LOCALIZE_OVERRIDE_GUIDE.md

## English announcement draft

We are collecting translation feedback to improve Godius localization.

If you find awkward wording, mistranslations, incorrect names, item names, skill names, monster names, NPC names, or map names, please submit them through the form below.

Feedback from players who remember official names from previous service versions is especially welcome. All submissions will be reviewed before being applied.

Google Form: TODO  
GitHub: https://github.com/griffith06/godius
Local testing guide: https://github.com/griffith06/godius/blob/main/LOCALIZE_OVERRIDE_GUIDE.md

## Japanese announcement draft

Godius の翻訳品質を改善するため、翻訳フィードバックを募集します。

不自然な表現、誤訳、固有名詞、アイテム名、スキル名、モンスター名、NPC名、地名などで気になる点があれば、下記フォームからお知らせください。

過去サービスで使われていた公式名称をご存じの方からの情報を特に歓迎します。いただいた内容は確認後、順次反映します。

Google Form: TODO  
GitHub: https://github.com/griffith06/godius
Local testing guide: https://github.com/griffith06/godius/blob/main/LOCALIZE_OVERRIDE_GUIDE.md
