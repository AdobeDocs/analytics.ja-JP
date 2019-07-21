---
description: トリガー条件のアクションを設定します。
keywords: Dynamic Tag Management;ルール、ルールの作成;new rule;javascript/サードパーティタグ;条件のアクションを設定します。新しいスクリプトの追加;non- sequential javascript;sequential javascript;non- sequential html
seo-description: トリガー条件のアクションを設定します。
seo-title: トリガー条件のアクションの設定
solution: Marketing Cloud、Analytics、Target、Dynamic Tag Management
title: トリガー条件のアクションの設定
uuid: 2e892f0b-7261-41ee- b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# トリガー条件のアクションの設定

トリガー条件のアクションを設定します。

条件を設定したら、トリガーの条件にするアクションを設定する必要があります。このアクションには、[!DNL Analytics] イベント、サードパーティタグおよびカスタムスクリプトを含めることができます。この例では、スクリプトまたはサードパーティタグを設定する方法を説明します。

[!DNL Adobe Analytics] や Google Analytics などの統合ツールだけでなく、Dynamic Tag Management は、あらゆる種類の JavaScript をトリガーしたり、サイト、選択したページまたは特定のシナリオに HTML を挿入したりできます。

各ルールは、スクリプトや HTML 挿入をいくつでもトリガーできます。

>[!NOTE]
>
>Because DTM allows you to inject custom code into your page, please take care not to create cross-site scripting (XSS) vulnerabilities (see [OWASP’s guide](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) for more info). 特に、スクリプトの中でデータ要素を使用する場合は警戒が必要です。データ要素には、信頼できない提供元から得られた値が含まれている可能性が常にあることを意識してください。

**トリガー条件のアクションを設定するには**

1. **[!UICONTROL "JavaScript/サードパーティタグ]** 」をクリックして、ルールに新しいスクリプトを追加します。

   ![](assets/scripts-actions.png)

1. Click **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. スクリプトに名前を付けます。
1. Specify how you want the script to trigger, and paste the desired content into the text area. ![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

