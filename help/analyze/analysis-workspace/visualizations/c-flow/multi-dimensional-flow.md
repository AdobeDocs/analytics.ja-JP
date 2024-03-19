---
description: ディメンション間のフローを使用すると、様々なディメンションにわたるユーザーパスを検証できます。
title: ディメンション間のフロー
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
source-git-commit: 5af6ef23a9cc48909950127552a530bc2395f7e8
workflow-type: ht
source-wordcount: '318'
ht-degree: 100%

---

# ディメンション間のフロー

ディメンション間のフローを使用すると、様々なディメンションにわたるユーザーパスを調べることができます。以下は、Analysis Workspace でのテキストの折り返しと多次元フローに関するビデオです。

>[!VIDEO](https://video.tv.adobe.com/v/24041/?quality=12)

各フロー列の先頭のディメンションラベルにより、フローのビジュアライゼーションで複数のディメンションをより直感的に使用できます。

![](assets/flow.png)

アプリの使用例と Web の使用例の 2 つについて見ていきます。

## 使用例 1：アプリケーション {#app}

返される上位の項目が [!UICONTROL ItemAdded] で、[!UICONTROL アクション名]ディメンションがフローに追加されました。

![](assets/multi-dimensional-flow.png)

画面／ページ間のインタラクションおよびこのアプリのアクションを調査するには、調査対象に応じて複数の場所にページディメンションをドラッグできます。

* ドロップゾーンのどちらかの端（表示される黒い縁の長方形のゾーンの内側）にドラッグして、その端の上位の結果を&#x200B;**置き換えます**。

  ![](assets/multi-dimensional-flow2.png) ![](assets/multi-dimensional-flow3.png)

* その端の白いスペース（黒い括弧で示される）にドラッグして、ビジュアライゼーションに&#x200B;**追加**&#x200B;します。

  ![](assets/multi-dimensional-flow4.png)

右の列の ItemScaled 項目をページディメンションで置き換える場合の結果を次に示します。上位の結果は、ページディメンションの上位の結果に変更されています。

![](assets/multi-dimensional-flow5.png)

これで、顧客がアクションおよびページをどのように移動しているかを確認できます。別のノードをクリックすることで、さらにフローを調査できます。

![](assets/multi-dimensional-flow6.png)

これは、別のアクション名ディメンションをビジュアライゼーションの端に追加する場合に発生することです。

![](assets/multi-dimensional-flow7.png)

これにより、深いインサイトが可能になり、分析するアプリに対する変更の可能性を考慮できます。

## 使用例 2：Web {#web}

この使用例は、最も多くのエントリを Web サイトに導くキャンペーンをどのようにして分析できるかを示します。

キャンペーン名ディメンションを新しいフローにドラッグします。

![](assets/multi-dimensional-flow8.png)

ここで、それらのキャンペーンがトラフィックを推進しているのはどのページかを確認したいので、ページディメンションをフロー結果の右側にドラッグして、ビジュアライゼーションに追加します。

![](assets/multi-dimensional-flow9.png)
