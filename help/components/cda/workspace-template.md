---
title: CDA Workspace テンプレート
description: Analysis Workspace 内の CDA テンプレートの各フィールドについて説明します。
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/Zui1m27pi3eQnm-dac2akfGRF01IbPaQ0SwLD01iDAE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: e38cbddc-1633-4cd5-bed5-9f289f2a6029id: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 391
ht-degree: 92%

---

# CDA Workspace テンプレート

{{available-existing-customers}}

アドビのオファーは、重要なクロスデバイスパフォーマンスデータを確認するためのテンプレートを提供します。

1. [experiencecloud.adobe.com](https://experiencecloud.adobe.com) に移動し、Adobe ID の資格情報を使用してログインします。
1. 上部の 9 グリッドアイコンをクリックし、「Analytics」をクリックします。
1. 上部の「[!UICONTROL Workspace]」をクリックし、「[!UICONTROL 新しいプロジェクトを作成]」をクリックします。
1. 「デバイス間の分析」テンプレートを見つけ、「[!UICONTROL 作成]」をクリックします。
1. プロンプトが表示されたら、CDA をサポートするレポートスイートに変更します。

複数のパネルを含む Analysis Workspace プロジェクトが作成されます。 上部に目次と紹介が表示され、レポートにコンテキストを表示したり、個々のレポートに移動したりできます。 目次内のリンクをクリックするか、パネルのアコーディオンを展開して、これらのレポートを表示します。

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **ユーザーの ID**：クロスデバイス分析に基づくメソッドを使用して、サイトへの訪問者を識別する頻度を示します。
* **オーディエンスサイズの測定**：「一意のデバイス」と「人」の比較を表示します。 この 2 つの数値の比率は「クロスデバイス圧縮」と呼ばれ、このパネルに表示される計算指標です。 この圧縮指標は、次の様々な要因によって異なります。
   * ログイン率：サイトにログインするユーザーが増えるほど、アドビはデバイスをまたいで訪問者を識別し、関連付けられるようになります。 サイトのログイン率が低い場合は、圧縮率も低くなります。
   * Experience Cloud ID の有効範囲：ECID を持つ訪問者のみを結び付けることができます。 ECID を使用してサイトに来訪した訪問者の割合が低くなると、圧縮率も低くなります。
   * 複数のデバイスの使用：サイトの訪問者が複数のデバイスを使用していない場合は、圧縮率が低くなります。
   * レポート精度：通常、日別の圧縮は、月別または年別の圧縮よりも小さくなります。 1 人のユーザーが 1 日で複数のデバイスを使用する機会は、1 ヶ月のうち 1 日だけ使用する場合よりも少なくなります。 セグメント化、フィルタリングまたは分類ディメンションを使用した場合も、圧縮率が低くなります。
* **人物ベースのセグメント**: デバイス固有のデータを表示できるセグメントドロップダウンリストが含まれています。 このパネルでは、セグメントを使用し、デバイスタイプを含める場合と除外する場合とで、レポートにどのように影響するかを確認することを推奨します。
* **クロスデバイスジャーニーの分析**：デバイスタイプに基づいたフローレポートとフォールアウトレポートを提供します。
* **クロスデバイス アトリビューション**：クロスデバイス分析とアトリビューションの機能を組み合わせます。
* **その他のヒント**：CDA をさらに活用できる、CDA に関する便利なトピック。
