# PDF手書き — Windows配布版

PDFに手書き・文字・図形・画像/PDFスタンプ等の注釈を追加し、保存・印刷するWindowsアプリです。

[最新の配布版をダウンロード](https://github.com/fnkuroko-design/PDF_Handwriting-Releases/releases/latest)

## 使用方法

1. Releasesから`PDF_Handwriting_0.6.6_x64_portable_github.zip`または7zを取得します。
2. 書き込み可能なフォルダーへすべて展開します。
3. `PDF手書き-portable/PDF手書き.exe`を起動します。

Windows 10/11 x64とMicrosoft Edge WebView2 Runtimeが必要です。文字注釈・日付スタンプにはWindowsのMSゴシック・MS P明朝を利用します。フォントファイルは同梱しません。

EXE、`bin`、`licenses`、利用案内・対応ソースを含むフォルダー一式を保持してください。詳しい使い方と確認範囲は配布セットの`README.txt`と[0.6.6 Release案内](RELEASE_0.6.6.md)に記載しています。EXEはAuthenticode未署名です。

## DataClasys

導入先にあるUserClientの`CLSUClient.exe`を呼び出します。DataClasys本体・UserClientは同梱していません。通常PDFにはUserClientは不要です。暗号化PDFを扱う場合はUserClientの導入・復号権限が必要で、呼出先はアプリ設定または`PDF_TEGAKI_CLSUCLIENT_PATH`で指定できます。

## 利用条件

自作部分は[MITライセンス](LICENSE)で利用・改変・再配布できます。第三者成分にはそれぞれの条件を適用します。第三者の許諾・著作権・NOTICEと必要な対応ソースは、配布アーカイブへ同梱しています。再配布時もこれらを保持してください。

## このリポジトリの内容

ここには配布物・利用案内・配布記録を保存します。アプリの開発リポジトリはPrivateで維持しています。GitHubが自動生成するSource code ZIP/tar.gzには、この配布用リポジトリの案内・記録を収録します。MPL対象等の第三者対応ソースは、配布アーカイブ内の`third-party-sources.zip`から無償取得できます。
