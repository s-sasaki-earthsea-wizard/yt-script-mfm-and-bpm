# YouTube Script: MFM and Bit Patterned Media

## プロジェクト概要

MFM（磁気力顕微鏡）の測定原理と、ビットパターンドメディア（BPM）について解説するYouTube動画の脚本を制作するプロジェクトです。磁気記録技術の次世代を担うBPMの仕組みと、それを観察・評価するMFMの原理を、学部生にもわかりやすく解説します。

### テーマ

「MFMとビットパターンドメディア - ナノスケールで磁石を"見る"技術と次世代磁気記録」

### 主要トピック

- **MFMの測定原理**: AFM（原子間力顕微鏡）をベースとした磁気力の検出メカニズム、磁化探針の役割
- **MFMの動作モード**: リフトモード、位相検出、周波数変調など
- **ビットパターンドメディア（BPM）**: 従来の連続薄膜メディアとの違い、1Tb/in²超の記録密度への挑戦
- **BPMの製造技術**: ナノインプリントリソグラフィ（NIL）、電子ビームリソグラフィ（EBL）
- **MFMによるBPMの評価**: 個別ビット島の磁化反転観察、スイッチングフィールド分布（SFD）の測定

### 参考資料

- **BPM論文**: Chen, Y.J. et al. (2010) "Individual bit island reversal and switching field distribution in perpendicular magnetic bit patterned media." Journal of Magnetism and Magnetic Materials.
  - DOI: 10.1016/j.jmmm.2010.11.094
  - 場所: `docs/BPM_JMMM_online101214.pdf`
- **NILレビュー論文**: Oh, D.K. et al. (2021) "Nanoimprint lithography for high-throughput fabrication of metasurfaces." Frontiers of Optoelectronics, 14(2), 229-251.
  - DOI: 10.1007/s12200-021-1121-8
  - 場所: `docs/12200_2021_Article_1121.pdf`

## ディレクトリ構造

```text
yt-script-mfm-and-bpm/
├── CLAUDE.md                 # プロジェクト設定・開発ルール
├── README.md                 # プロジェクト概要
├── Makefile                  # ビルドコマンド
├── docs/                     # 参考文献（バージョニング対象外）
│   └── *.pdf                 # MFM・BPM関連の学術論文
├── instructions/             # 制作ガイドライン
│   ├── video_concept.md      # 動画コンセプト（10-20分、1動画1テーマ）
│   └── youtube_script_guidelines.md  # YouTube脚本ガイドライン（TTS変換含む）
├── slides-jp/                # スライド・動画関連（Reveal.js）
│   ├── index.html            # メインスライド
│   ├── script-outline.md     # 動画脚本のアウトライン
│   ├── yt_script.md          # YouTube動画脚本（予定）
│   ├── css/                  # スタイルシート
│   ├── assets/               # 画像等のアセット
│   └── dist/                 # Reveal.jsビルド成果物
├── descriptions/             # 動画の概要欄
│   └── youtube_description.md  # YouTube概要欄（日本語）
├── captions/                 # 字幕（予定）
│   └── mfm-and-bpm-jp.srt   # 日本語字幕（予定）
└── .github/                  # GitHubテンプレート
```

## 動画フォーマット

- **尺**: 10〜20分程度
- **構成**: 1動画1テーマ
- **スタイル**: 短く、濃く、わかりやすく
- **ターゲット**: 理工系の学部生、大学院生、研究者、社会人
- **コンセプト**: 学部1-2回生程度の前提知識で物理や技術をわかりやすく平易に伝える

詳細は `instructions/video_concept.md` を参照。

## 言語設定

このプロジェクトでは**日本語**での応答を行ってください。コード内のコメント、ログメッセージ、エラーメッセージ、ドキュメンテーション文字列なども日本語で記述してください。

## 開発ルール

### コーディング規約

- Python: PEP 8準拠
- 関数名: snake_case
- クラス名: PascalCase
- 定数: UPPER_SNAKE_CASE
- Docstring: Google Style

### Manimアニメーション

- アニメーション内のテキスト・ラベルは**日英併記**とする
  - 国際的な視聴者にも理解できるよう、日本語と英語を併記する
- テロップは**簡潔に核心を伝える**ものとする
  - 冗長な説明は避け、要点を端的に表現する
  - ナレーションの補助として機能させる

## Git運用

- ブランチ戦略: feature/*, fix/*, refactor/*
- コミットメッセージ: 英文を使用、動詞から始める
- PRはmainブランチへ

## 開発ガイドライン

### ドキュメント更新プロセス

機能追加やPhase完了時には、以下のドキュメントを同期更新する：

1. **CLAUDE.md**: プロジェクト全体状況、Phase完了記録、技術仕様
2. **README.md**: ユーザー向け機能概要、実装状況、使用方法
3. **Makefile**: コマンドヘルプテキスト（## コメント）の更新
4. **makefiles/**: コマンドヘルプテキスト（## コメント）の更新

### コミットメッセージ規約

#### コミット粒度

- **1コミット = 1つの主要な変更**: 複数の独立した機能や修正を1つのコミットにまとめない
- **論理的な単位でコミット**: 関連する変更は1つのコミットにまとめる
- **段階的コミット**: 大きな変更は段階的に分割してコミット

#### プレフィックスと絵文字

- ✨ feat: 新機能
- 🐞 fix: バグ修正
- 📚 docs: ドキュメント
- 🎨 style: コードスタイル修正
- 🛠️ refactor: リファクタリング
- ⚡ perf: パフォーマンス改善
- ✅ test: テスト追加・修正
- 🏗️ chore: ビルド・補助ツール
- 🚀 deploy: デプロイ
- 🔒 security: セキュリティ修正
- 📝 update: 更新・改善
- 🗑️ remove: 削除

**重要**: Claude Codeを使用してコミットする場合は、必ず以下の署名を含める：

```text
🤖 Generated with [Claude Code](https://claude.ai/code)

Co-Authored-By: Claude <noreply@anthropic.com>
```

## 脚本制作ガイドライン

脚本作成時は `instructions/youtube_script_guidelines.md` を参照。

### 主なポイント

- 話し言葉として書く（「読む」ではなく「聴く」ための最適化）
- 一文は20〜30文字程度
- 句読点による自然な間
- Audio Tags（ElevenLabs v3用）の活用
- 専門用語には補足説明を付ける
