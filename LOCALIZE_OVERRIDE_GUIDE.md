# Godius Localization Override Guide

This guide explains how to test Godius translation changes locally and submit feedback.

## Important

Localization override works only in a Godius build that supports the `LocalizeOverride` folder.

In older builds, `.pak` files have priority and local JSON files are not loaded. If your changes do not appear in game, please wait for a build that includes localization override support.

## Folder Layout

Place the `LocalizeOverride` folder next to the game executable.

```text
Godius/
  GcX64R.exe
  base.pak
  00000.pak
  LocalizeOverride/
    strings/
      en.json
      ja.json
      ko.json
```

Only files in `LocalizeOverride/strings/` are used for translation override.

## How To Test Changes

1. Download this repository as a ZIP file or clone it with Git.
2. Copy the `LocalizeOverride` folder into your Godius Steam install folder.
3. Open the JSON file for your language in `LocalizeOverride/strings/`.
4. Edit translated text values only.
5. Start or restart the game and check the changed text.
6. Submit your correction through GitHub Pull Request or the official feedback form.

## Language Files

| Language | File |
| --- | --- |
| Korean | `LocalizeOverride/strings/ko.json` |
| English | `LocalizeOverride/strings/en.json` |
| Japanese | `LocalizeOverride/strings/ja.json` |
| Simplified Chinese | `LocalizeOverride/strings/zh-CN.json` |
| Traditional Chinese | `LocalizeOverride/strings/zh-TW.json` |
| German | `LocalizeOverride/strings/de.json` |
| Spanish | `LocalizeOverride/strings/es.json` |
| French | `LocalizeOverride/strings/fr.json` |
| Polish | `LocalizeOverride/strings/pl.json` |
| Portuguese (Brazil) | `LocalizeOverride/strings/pt-BR.json` |
| Russian | `LocalizeOverride/strings/ru.json` |

## Editing Rules

- Edit translated text values only.
- Do not change JSON keys.
- Keep placeholders such as `%s`, `%d`, `%u`, `{0}`, and `\n`.
- Keep color tags such as `<green>`, `<orange>`, `<red>`, `<blue>`, and closing tags.
- Do not remove item names, skill names, NPC names, monster names, or map names unless you are correcting an official term.
- Keep UI text reasonably short so it can fit in game windows and buttons.

## 한국어 안내

번역을 직접 확인하려면 `LocalizeOverride` 폴더를 게임 실행 파일이 있는 Steam 설치 폴더에 넣어 주세요.

```text
Godius/
  GcX64R.exe
  LocalizeOverride/
    strings/
      en.json
      ja.json
      ko.json
```

주의: 이 기능은 `LocalizeOverride` 지원이 포함된 게임 빌드에서만 동작합니다. 이전 빌드에서는 `.pak` 파일이 우선이라 로컬 JSON 수정이 게임에 반영되지 않습니다.

수정할 때는 JSON key를 바꾸지 말고 value 문구만 수정해 주세요. `%s`, `%d`, `\n`, `<green>` 같은 placeholder와 태그는 반드시 유지해야 합니다.

## 日本語ガイド

翻訳を確認するには、`LocalizeOverride` フォルダを Steam の Godius インストールフォルダにコピーしてください。

```text
Godius/
  GcX64R.exe
  LocalizeOverride/
    strings/
      en.json
      ja.json
      ko.json
```

注意: この機能は `LocalizeOverride` に対応したゲームビルドでのみ動作します。古いビルドでは `.pak` ファイルが優先されるため、ローカル JSON の変更はゲームに反映されません。

JSON key は変更せず、翻訳テキストの value のみを修正してください。`%s`, `%d`, `\n`, `<green>` などの placeholder とタグは必ず維持してください。
