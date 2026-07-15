# tokutei-rireki — 特定技能外国人の履歴書システム

多言語対応（日本語／ベトナム語／インドネシア語／クメール語／タガログ語／英語）の
特定技能外国人向けWeb履歴書ツールです。入力内容を日本語の履歴書PDFに変換して保存でき、
外国人管理システムへ取り込むための機械可読データ（JSON）をPDFに埋め込みます。

## 公開URL（GitHub Pages）

`https://akina12231988-star.github.io/tokutei-rireki/`

- 単一の `index.html`（外部依存はGoogle FontsのCDNのみ）で動作する静的サイトです。
- リポジトリ設定 → **Pages** → Source を **Deploy from a branch**、Branch を **main / (root)** に設定してください。
- `.nojekyll` を置いているため Jekyll のビルドは行われず、ファイルがそのまま配信されます。

## 主な機能

- 6言語UI・入力補助
- ⑨ 職歴（会社名・在留資格・期間）を行数制限なしで追加
- 当時の在留資格はプルダウン（7区分）／PDFでは必ず日本語表記
- 「日本語に翻訳してPDF保存」でA4履歴書PDFを生成
- PDFに `@@RIREKI_JSON_V1@@…@@END@@` 形式のJSON（Base64）を不可視テキストで埋め込み

## 自動翻訳バックエンド（任意）

自由記述欄（会社名・住所など）の自動日本語翻訳を有効にする場合は、
`index.html` 冒頭の `TRANSLATE_ENDPOINT` にデプロイ済み外国人管理システムの
`/api/translate` のURLを設定してください。未設定でもPDF生成フローは完了します
（選択式項目は内蔵辞書で日本語化され、自由記述は入力言語のまま出力されます）。

## 関連

- 外国人管理システム（PDF取り込み側）: immigration-app リポジトリ
- 埋め込みデータ仕様・翻訳辞書・在留資格辞書: immigration-app `docs/` 配下を参照
