# Olympus — オリュンポス

開発・調査・デザインなどの役割を分け、必要な専門基準だけを読むための、12のAIエージェントスキル集です。

集合名は **Olympus（オリュンポス）**。個々のスキルには、担当する役割と結びつけたオリュンポス十二神の名前を付けています。神名は役割を覚えるための名称で、特定のモデルや性能を保証するものではありません。

## 12の役割

| Skill | 名前 | 主な担当 |
| --- | --- | --- |
| [zeus](skills/zeus/SKILL.md) | ゼウス | 統括・横断判断・AIチームの分業設計 |
| [hera](skills/hera/SKILL.md) | ヘラ | PM・タスク分解・担当・期限・依存関係 |
| [hephaestus](skills/hephaestus/SKILL.md) | ヘファイストス | 開発・設計・実装・デバッグ |
| [artemis](skills/artemis/SKILL.md) | アルテミス | リサーチ・比較・根拠の確認 |
| [aphrodite](skills/aphrodite/SKILL.md) | アフロディテ | デザイン・UI・UX・情報階層 |
| [dionysus](skills/dionysus/SKILL.md) | ディオニュソス | 企画・課題発見・価値提案・MVP |
| [athena](skills/athena/SKILL.md) | アテナ | QA・レビュー・受入条件・比較評価 |
| [ares](skills/ares/SKILL.md) | アレス | セキュリティ・認証・認可・脅威分析 |
| [poseidon](skills/poseidon/SKILL.md) | ポセイドン | SRE・環境運用・接続診断・復旧 |
| [apollo](skills/apollo/SKILL.md) | アポロン | 編集・報告書・文書・資料制作 |
| [hermes](skills/hermes/SKILL.md) | ヘルメス | 秘書・依頼整理・予定・リマインド |
| [demeter](skills/demeter/SKILL.md) | デメテル | ナレッジ管理・索引・保存・再利用 |

## 構成

```text
skills/
  zeus/
    SKILL.md
    agents/openai.yaml
  ...                       # 同じ構造の12スキル
professional/
  INDEX.md                  # 専門基準の索引
  engineering/STANDARD.md
  research/STANDARD.md
  ...                       # 共通の25文書
```

`SKILL.md` は担当範囲と適用手順、`professional/` は判断・品質の基準です。基準本文をスキルごとに複製せず、相対リンクで参照します。名前・説明から主担当を選び、該当する本文・節だけを読みます。

## 使い方

リポジトリ全体をcloneし、エージェントに対象スキルを指定します。

```sh
git clone https://github.com/robatodt74-byte/olympus.git
cd olympus
```

依頼例：

> `skills/hephaestus/SKILL.md` を読んで、このプロジェクトの不具合を修正してください。

> `skills/artemis/SKILL.md` を読んで、候補を一次資料で比較してください。

> `skills/athena/SKILL.md` を読んで、成果物を受入条件に沿って評価してください。

現在の参照構成では **`skills/` と `professional/` の両方を保持**してください。スキルのフォルダだけを別の場所へコピーする方式のインストーラーには、そのまま渡せません。この初版ではCodex・Claudeの設定変更や自動インストールは行いません。

`agents/openai.yaml` にはCodex向けの表示名と暗黙呼出しの設定があります。ファイルが存在することと、利用するアプリでの発見・呼出し成功は別に確認してください。

## 運用の原則

- 主成果物に対して主担当を1つ選び、具体的な不足があるときだけ補助スキルを使う。
- すべてのスキル・基準を毎回読み込まない。同じ対象・版で有効な確認結果は再利用する。
- 技術の実装・ローカル検証・外部反映・人の受入を区別する。
- スキルの利用やチーム設計は、別エージェントの自動起動・外部送信・課金等の許可を意味しない。
- 個人環境向けの既定値や過去のプロジェクト例を含む。対象環境と最新のユーザー指定を優先する。

## 初版の範囲

2026-11-23時点の導入済み12スキルと専門基準をまとめ、リポジトリ内参照を相対パスへ変更しました。元の導入済みスキルは変更していません。追加の外部スキル・MCP・CLIは同梱していません。

これは配布・履歴管理のための初版です。トークン削減率、出力品質の改善率、別環境での自動発動は、このパッケージの検査だけでは実証できません。

公開リポジトリとして管理します。ライセンスは未設定です。
