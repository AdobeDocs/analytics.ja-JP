---
title: CDA Workspace テンプレート
description: Analysis Workspace 内の CDA テンプレートの各フィールドについて説明します。
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
source-git-commit: d37fa0aff0b1bbe196b943bc26e86b1e79936184
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 93%

---

# CDA Workspace テンプレート

{{available-existing-customers}}

アドビのオファーは、重要なクロスデバイスパフォーマンスデータを確認するためのテンプレートを提供します。

1. [experiencecloud.adobe.com](https://experiencecloud.adobe.com) に移動し、Adobe ID の資格情報を使用してログインします。
1. 上部の 9 グリッドアイコンをクリックし、「Analytics」をクリックします。
1. 上部の「[!UICONTROL Workspace]」をクリックし、「[!UICONTROL 新しいプロジェクトを作成]」をクリックします。
1. 「デバイス間の分析」テンプレートを見つけ、「[!UICONTROL 作成]」をクリックします。
1. プロンプトが表示されたら、CDA をサポートするレポートスイートに変更します。

複数のパネルを含む Analysis Workspace プロジェクトが作成されます。上部に目次と紹介が表示され、レポートにコンテキストを表示したり、個々のレポートに移動したりできます。目次内のリンクをクリックするか、パネルのアコーディオンを展開して、これらのレポートを表示します。

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **ユーザーの ID**：クロスデバイス分析に基づくメソッドを使用して、サイトへの訪問者を識別する頻度を示します。
* **オーディエンスサイズの測定**：「一意のデバイス」と「人」の比較を表示します。この 2 つの数値の比率は「クロスデバイス圧縮」と呼ばれ、このパネルに表示される計算指標です。この圧縮指標は、次の様々な要因によって異なります。
   * ログイン率：サイトにログインするユーザーが増えるほど、アドビはデバイスをまたいで訪問者を識別し、関連付けられるようになります。サイトのログイン率が低い場合は、圧縮率も低くなります。
   * Experience Cloud ID の有効範囲：ECID を持つ訪問者のみを結び付けることができます。ECID を使用してサイトに来訪した訪問者の割合が低くなると、圧縮率も低くなります。
   * 複数のデバイスの使用：サイトの訪問者が複数のデバイスを使用していない場合は、圧縮率が低くなります。
   * レポート精度：通常、日別の圧縮は、月別または年別の圧縮よりも小さくなります。1 人のユーザーが 1 日で複数のデバイスを使用する機会は、1 ヶ月のうち 1 日だけ使用する場合よりも少なくなります。セグメント化、フィルタリングまたは分類ディメンションを使用した場合も、圧縮率が低くなります。
* **人物ベースのセグメント**：デバイス固有のデータを表示できるセグメントドロップダウンリストが含まれます。 このパネルでは、セグメントを使用し、デバイスタイプを含める場合と除外する場合とで、レポートにどのように影響するかを確認することを推奨します。
* **クロスデバイスジャーニーの分析**：デバイスタイプに基づいたフローレポートとフォールアウトレポートを提供します。
* **クロスデバイスアトリビューション**：クロスデバイス分析の機能とアトリビューションの機能を組み合わせます。
* **その他のヒント**：CDA をさらに活用できる、CDA に関する便利なトピック。
