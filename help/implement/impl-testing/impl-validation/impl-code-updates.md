---
description: .JS ファイルまたは HTML コードを変更した場合に、テストをおこなう責任はお客様にあります。テストは、変更を実稼動 Web サイトに公開する前に実行する必要があります。
keywords: Analytics の導入
seo-description: .JS ファイルまたは HTML コードを変更した場合に、テストをおこなう責任はお客様にあります。テストは、変更を実稼動 Web サイトに公開する前に実行する必要があります。
seo-title: コードの変更
solution: Analytics
title: コードの変更
topic: 開発者と導入
uuid: eac045e-15f5-45f6- a21a- de6c4b0a8185
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# コードの変更

.JS ファイルまたは HTML コードを変更した場合に、テストをおこなう責任はお客様にあります。テストは、変更を実稼動 Web サイトに公開する前に実行する必要があります。

Ensure that the linefeeds/return characters are not stripped or altered from the code that is placed within the HTML, or from within the [!DNL .JS] file. すべてのページとページテンプレートで、JavaScript がエラーなしに実行されることを確認してください（Internet Explorer の「インターネットオプション」で、「詳細設定」タブを選択し、「スクリプトエラーごとに通知を表示する」をクリックします）。

エラーについてテストする際には、コードをデフォルトの HTML ページに貼り付けて、他のページの要素やオブジェクトが原因でエラーが発生しないかを確認します。

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

