---
description: ディメンション間のフローを利用して、さまざまなディメンションをまたいでユーザーパスを調査する方法を説明します。
title: ディメンション間のフロー
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
TQID: https://experienceleague.adobe.com/9OjAFYHo5uhcfbQQOB46jfG1R2wIQCBHXEr842EcZQ0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 95%

---

# ディメンション間のフロー

ディメンション間のフローを使用すると、様々なディメンションにわたるユーザーパスを調べることができます。

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Inter-dimensional flows](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

この記事では、モバイルアプリのインタラクションおよびイベントと、キャンペーンで web 訪問を推進する方法という 2 つのユースケースに対して、このフローを使用する方法について説明します。

## モバイルアプリのインタラクションとイベント

このフロー例では、[!UICONTROL 画面名]ディメンションを使用して、ユーザーがアプリ内の様々な画面（シーン）をどのように使用するかを確認します。 返される上部の画面は **[!UICONTROL luma: content: ios: en: home]** で、これはアプリのホームページです。

![追加された項目を示すフロー。](assets/flowapp.png)

このアプリの画面とイベントタイプ（買い物かごへの追加、購入など）間のインタラクションを調べるには、**[!UICONTROL イベントタイプ]**&#x200B;ディメンションをドラッグ＆ドロップします。

* フロー内の使用可能なステップに加えて、そのディメンションを置き換えるには：

  ![複数の領域にドラッグされたページディメンションを示すフロー。](assets/flowapp-replace.png)

* 現在のフロービジュアライゼーションの外部で、ディメンションを追加するには：

  ![末尾の空白にドラッグされたページディメンションを示すフロー。](assets/flowapp-add.png)

以下のフロービジュアライゼーションは、**[!UICONTROL イベントタイプ]**&#x200B;ディメンションを追加した結果を示しています。 このビジュアライゼーションでは、モバイルアプリのユーザーが、商品を買い物かごに追加する前にどのように画面を移動し、アプリケーションを閉じ、オファーを提示されているかといったインサイトが得られます。

![ページディメンションの結果がリストの上部に表示されているフロー。](assets/flowapp-result.png)

## キャンペーンがどのように web 訪問を促しているか

Web サイトへの訪問を推進するキャンペーンを分析します。 **[!UICONTROL キャンペーン名]**&#x200B;をディメンションとするフロービジュアライゼーションを作成します

![フロー web キャンペーン名ディメンション](assets/flowweb.png)

最後の&#x200B;**[!UICONTROL キャンペーン名ディメンション]**&#x200B;を&#x200B;**[!UICONTROL 書式設定されたページ名]**&#x200B;ディメンションに置き換え、フロービジュアライゼーションの最後に別の&#x200B;**[!UICONTROL 書式設定されたページ名]**&#x200B;ディメンションを追加します。

![フロー web キャンペーン名および web ページディメンション](assets/flowweb-replace.png)

いずれかのフローにポインタを合わせると、詳細が表示されます。 例えば、どのキャンペーンが買い物かごのチェックアウトにつながったかが表示されます。

![フロー web キャンペーン名と web ページディメンションのホバー](assets/flowweb-hover.png)
