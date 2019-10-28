---
description: ページで .JS ファイルが正しく参照されていることを確認します。パスには、現在のドキュメントを基準とした相対パスを指定するか、または絶対パス名を使用できます。
keywords: Analytics の実装
seo-description: ページで .JS ファイルが正しく参照されていることを確認します。パスには、現在のドキュメントを基準とした相対パスを指定するか、または絶対パス名を使用できます。
seo-title: JavaScript JS ファイル
solution: Analytics
title: JavaScript JS ファイル
topic: 開発者と実装
uuid: 6e83223f-2127-41d3-9806-bd085fa2a747
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScript JS ファイル

ページで .JS ファイルが正しく参照されていることを確認します。パスには、現在のドキュメントを基準とした相対パスを指定するか、または絶対パス名を使用できます。

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

サイトの一部のページがセキュリティで保護されたプロトコル（https:）で読み込まれ、JavaScript 版 [!DNL AppMeasurement] ファイルを参照する場合、そのファイルへの参照がセキュリティで保護されている（https: を介している）か、または次に示すように参照がコード化されていることを確認します。この例では、現在のページのプロトコルを使用しており、「一部の要素がセキュリティで保護されていない」という警告が出ないようにしています。

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

Web サイトの訪問者がファイルをダウンロードして実行できるように、Web サーバーの [!DNL .JS] ファイルに権限が適切に設定されていることを確認します。開発サーバーで別の [!DNL .JS] ファイルが使用されている場合、上書きを防ぐために、実稼動サーバーの [!DNL .JS] ファイルに「読み取り専用」の属性を設定します。[!DNL .JS] ファイルを変更した場合は、ファイルの最上部で次の設定が正しく指定されていることを確認してください。

```js
/************************** CONFIG SECTION **************************/
/* You may add or alter any code config here.                       */
/* Link Tracking Config */
s.trackDownloadLinks=false /* true for download tracking */
s.trackExternalLinks=false /* true for exit link tracking */
s.trackInlineStats=false /* true for ClickMap support */
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls"
s.linkInternalFilters="javascript:"
s.linkLeaveQueryString=false
s.linkTrackVars="None" 
s.linkTrackEvents="None"
```

「*`s_account`*」が [!DNL .JS] ファイルの最上部にあり、値が割り当てられている場合は、レポートスイート ID（[!UICONTROL s_account ] 変数に設定される）が正しいことを確認します。また、ページ内のコードで、[!UICONTROL レポートスイート ID]（*`s_account`* 変数）に設定がないことを確認します。

イメージリクエストと変数を調べて、「フォールバック方式」（上記の例における「分割」コードの 3 番目の部分）が [!DNL .JS] ファイル以外のイメージリクエストを作成していないことを確認します。このことは、「フォールバック」方式では最小限の情報のみでイメージリクエストを作成するので判別できます。
