# PDF手書き 0.6.6（配布用再ビルド）

Windows 10/11 x64向けのポータブル版です。`PDF_Handwriting_0.6.6_x64_portable_github.zip`または同名の7zをダウンロードし、すべて展開して`PDF手書き.exe`を実行してください。Microsoft Edge WebView2 Runtimeが必要です。EXEだけを取り出さず、`bin`、`licenses`、利用案内と対応ソースを含むフォルダー一式を保持してください。

## 主な機能

- 手書き、文字、図形、矢印、画像・PDFスタンプ等の注釈追加・編集・保存
- パスワード付きPDFの閲覧、保護設定・変更・解除
- しおりの追加・編集・倍率設定、注釈一覧の検索・フィルタ
- 文字選択・コピー、複数PDFのタブ表示、ページ回転・並べ替え
- 連続注釈・資料番号、ページサイズ変更、注釈焼き付け保存
- 印刷プレビュー、複数ページ配置、対応する文字・ベクターを保持するネイティブ印刷

## 今回の再ビルド

従前の0.6.6を基に、ビルド時の個人ローカルパスを対処し、MIT許諾・第三者表記・日本語の利用案内を配布セットへ整えました。`0.6.6-dev.46`で比較・限定検証を行った後、改めて正式版番号を`0.6.6`へ戻しています。

描画・注釈・保存・印刷・DataClasysの製品処理と採用する依存版は変更していません。releaseでは、開発者のソースフォルダーにあるPDFium DLLを探さなくなりました。同梱DLLは従前と同じです。EXEはAuthenticode未署名です。

## DataClasysとフォント

DataClasys連携は、配布先に導入済みのUserClientの`CLSUClient.exe`を呼び出します。本体・UserClientは同梱していません。導入先が異なる場合は、アプリ設定または`PDF_TEGAKI_CLSUCLIENT_PATH`で指定してください。通常PDFにはUserClientは不要です。

文字注釈にはWindowsのMSゴシック、日付スタンプにはMS P明朝が必要です。フォントファイルは同梱していません。利用者PDF、登録スタンプ、ログ、ブラウザープロファイルも含めていません。

## 利用条件と第三者ソース

自作部分は同梱`LICENSE`のMITライセンスで利用・改変・再配布できます。第三者成分にはそれぞれの条件を適用します。著作権・許諾・NOTICE等は`licenses`と`THIRD_PARTY_NOTICES.txt`にあり、MPL対象のRust成分・PDF.js SVGの対応ソースは同梱`third-party-sources.zip`で無償取得できます。

本ソフトウェアは、Independent JPEG GroupおよびFreeType Teamの成果を一部利用しています。再配布時は、同梱の許諾本文に加えて次の謝辞も配布文書に保持してください。

- This software is based in part on the work of the Independent JPEG Group.
- This software is based in part on the work of the FreeType Team.

依存一覧にはビルド・開発候補も含みます。fontkit 1.1.1の実際の配布JSの表記を保持し、内包成分について参照資料を補足しました。内包版を確定したSBOMとしては扱いません。詳細は`THIRD_PARTY_INVENTORY.json`を参照してください。

## 添付ファイル

| ファイル | サイズ（概数） | SHA-256 |
|---|---|---|
| `PDF_Handwriting_0.6.6_x64_portable_github.zip` | 12.8 MB | `06B3C54D52E5C676DC7C1EA9B5A333366EFF9A62839D989E51BBC532DF06B066` |
| `PDF_Handwriting_0.6.6_x64_portable_github.7z` | 8.6 MB | `0FFC6E46E9742D8237800F4CBD232A9162F941BE3ED8339B77FC69759CE3B2E5` |
| `SHA256SUMS.txt` | — | ZIP/7zの照合用 |
| `PACKAGING_RECORD.json` | — | 全769ファイルのハッシュと元ビルド・包装記録 |
| `0.6.6-provenance.json` | — | 配布物・検証範囲の要約 |

ZIPと7zは同じ769ファイルのセットです。どちらか一方を取得してください。GitHubの自動生成Source code ZIP/tar.gzは、配布用リポジトリの案内・記録をまとめたものです。アプリの開発ソースはPrivateで保持しています。

## ビルド・確認記録

今回のEXEのビルド元は`30f48a424ae09fbc9ef8402c4d9174e454f89162`、包装元は`abafa0eb184af9da424cbd30375e49c93042d1fc`です。従前EXEの元記録`2e97295`とは区別しています。

- 従前snapshotとの製品ソース・依存比較、および生成フロントエンド全17ファイルのバイト一致
- EXEとPDFium DLLのローカルパス文字列検査で検出0件
- qpdf保護処理8テスト成功
- ZIP/7zの破損検査と全769ファイルのSHA-256一致
- 7z展開後、ソースツリー外から起動し、応答するウィンドウと版タイトルを確認

旧EXEとのバイナリ一致や全機能のGUI同等性を証明する確認ではありません。全機能のGUI再操作、実機プリンター全般、DataClasys実資料の再操作は行っていません。印刷時の文字保持にはフォント・PDF内容による制約があります。
