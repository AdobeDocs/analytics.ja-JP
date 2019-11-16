---
description: .JS ファイルまたは HTML コードを変更した場合に、テストをおこなう責任はお客様にあります。テストは、変更を実稼動 Web サイトに公開する前に実行する必要があります。
keywords: Analytics Implementation
solution: Analytics
title: コードの変更
topic: Developer and implementation
uuid: efac045e-15f5-45f6-a21a-de6c4b0a8185
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# コードの変更

.JS ファイルまたは HTML コードを変更した場合に、テストをおこなう責任はお客様にあります。テストは、変更を実稼動 Web サイトに公開する前に実行する必要があります。

HTML 内に配置されたコードから、または [!DNL .JS] ファイル内から、ラインフィード文字やリターン文字を削除したり変更したりしないでください。すべてのページとページテンプレートで、JavaScript がエラーなしに実行されることを確認してください（Internet Explorer の「インターネットオプション」で、「詳細設定」タブを選択し、「スクリプトエラーごとに通知を表示する」をクリックします）。

エラーについてテストする際には、コードをデフォルトの HTML ページに貼り付けて、他のページの要素やオブジェクトが原因でエラーが発生しないかを確認します。

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

