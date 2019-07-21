---
description: ページで .JS ファイルが正しく参照されていることを確認します。パスには、現在のドキュメントを基準とした相対パスを指定するか、または絶対パス名を使用できます。
keywords: Analytics の導入
seo-description: ページで .JS ファイルが正しく参照されていることを確認します。パスには、現在のドキュメントを基準とした相対パスを指定するか、または絶対パス名を使用できます。
seo-title: JavaScript JSファイル
solution: Analytics
title: JavaScript JSファイル
topic: 開発者と導入
uuid: 6e83223f-2127-41d3-9806- bd085fa2a747
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# JavaScript JSファイル

ページで .JS ファイルが正しく参照されていることを確認します。パスには、現在のドキュメントを基準とした相対パスを指定するか、または絶対パス名を使用できます。

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

If some pages of the site are loaded in a secure protocol (https:), and reference the [!DNL AppMeasurement] for JavaScript file, ensure that the reference to the file is either secure (via https:) or code the reference as shown below. この例では、現在のページのプロトコルを使用しており、「一部の要素がセキュリティで保護されていない」という警告が出ないようにしています。

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

Ensure that the [!DNL .JS] file on the web servers have permissions appropriately set so that the file may be downloaded and executed by website visitors. If a different [!DNL .JS] file is used on development servers, set the "read only" attribute for the [!DNL .JS] file on production servers to avoid an overwrite. If altered, ensure that the following settings are set appropriately at the top of the [!DNL .JS] file:

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

If " *`s_account`*" is assigned a value at the top of the [!DNL .JS] file, ensure that the report suite ID (populated in the [!UICONTROL s_account]variable) is correct. Also ensure that the code in the page is not setting the [!UICONTROL Report Suite ID] ( *`s_account`* variable).

Examine the image request and variables to ensure that the "fallback method" (the third part of the "split" code in the example above) is not creating the image request instead of the [!DNL .JS] file. このことは、「フォールバック」方式では最小限の情報のみでイメージリクエストを作成するので判別できます。
