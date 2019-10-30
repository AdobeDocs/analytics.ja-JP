---
description: トリガー条件のアクションを設定します。
keywords: Dynamic Tag Management, ルール, ルールの作成, 新規ルール, javascript／サードパーティタグ, 条件のアクションの設定, 新規スクリプトを追加, 非順次 javascript, 順次 javascript, 非順次 html
seo-description: トリガー条件のアクションを設定します。
seo-title: トリガー条件のアクションの設定
solution: Experience Cloud, Analytics, Target, Dynamic Tag Management
title: トリガー条件のアクションの設定
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# トリガー条件のアクションの設定

トリガー条件のアクションを設定します。

条件を設定したら、トリガーの条件にするアクションを設定する必要があります。このアクションには、[!DNL Analytics] イベント、サードパーティタグおよびカスタムスクリプトを含めることができます。この例では、スクリプトまたはサードパーティタグを設定する方法を説明します。

[!DNL Adobe Analytics] や Google Analytics などの統合ツールだけでなく、Dynamic Tag Management は、あらゆる種類の JavaScript をトリガーしたり、サイト、選択したページまたは特定のシナリオに HTML を挿入したりできます。

各ルールは、スクリプトや HTML 挿入をいくつでもトリガーできます。

> [!NOTE] DTMではページにカスタムコードを挿入できるので、クロスサイトスクリプティング(XSS)脆弱性を作成しないように注意してください(詳しくは [OWASPのガイド](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) を参照)。 特に、スクリプトの中でデータ要素を使用する場合は警戒が必要です。データ要素には、信頼できない提供元から得られた値が含まれている可能性が常にあることを意識してください。

**トリガー条件のアクションを設定するには**

1. 「**[!UICONTROL Javascript / サードパーティタグ]**」をクリックして、新しいスクリプトをルールに追加します。

   ![](assets/scripts-actions.png)

1. 「**[!UICONTROL 新規スクリプトを追加]**」をクリックします。

   ![](assets/scripts-actions2.png)

1. スクリプトに名前を付けます。
1. スクリプトのトリガー方法を指定して、目的のコンテンツをテキスト領域に貼り付けます。![](assets/scripts-actions3.png)

1. 「**[!UICONTROL コードを保存]**」をクリックすると、スクリプトがルールのキューに追加されます。![](assets/scripts-actions4.png)

