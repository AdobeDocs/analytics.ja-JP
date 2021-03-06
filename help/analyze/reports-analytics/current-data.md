---
description: Reports & Analytics の「現在のデータを含む」オプションを使用すると、ほとんどの場合、データが完全に処理されてファイナライズされる前に最新の Analytics データを表示できます。「現在のデータ」には、ほとんどの指標が数分以内で表示され、迅速な意思決定を可能にする実用的なデータが提供されます。
subtopic: Current Data
title: 現在のデータ
uuid: 601d3695-be13-4b7f-9df0-de01c8bd64ee
feature: Reports & Analytics の基本
role: User, Admin
exl-id: 4e90f5ad-ba12-4282-a0d9-55765d88104b
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 97%

---

# 現在のデータ

Reports &amp; Analytics の「現在のデータを含む」オプションを使用すると、ほとんどの場合、データが完全に処理されてファイナライズされる前に最新の Analytics データを表示できます。「現在のデータ」には、ほとんどの指標が数分以内で表示され、迅速な意思決定を可能にする実用的なデータが提供されます。

レポートの設定の一部としてのオプションとして表示されます。

![現在のデータのスクリーンショット](assets/current_data.png)

「現在のデータ」は、この機能をサポートするすべてのレポートで、デフォルトで有効です。データが完全に処理された後にすべての指標を表示する場合は、次のいくつかのオプションがあります。

* Analysis Workspace で、完全に処理済みのデータを使用します。
* 現在のデータレポート設定で「いいえ」をクリックすると、完全に処理済みのデータのみが使用されます。
* 管理者以外のユーザーがこのオプションを表示できないようにするには、Admin Console の製品プロファイルから「現在のデータ」権限項目を削除します。詳しくは、『管理者ユーザーガイド』の「Analyticsツールの[製品プロファイルの権限](/help/admin/admin-console/permissions/analytics-tools.md)」を参照してください。

データの可用性を優先するため、現在のデータは、セグメント、分類、内訳、パス、また一部の指標では使用できません。これらの機能のいずれかを使用すると、現在のデータがレポートで強制的に「いいえ」に設定され、現在のデータが使用できない理由を示す黄色の通知が表示されます。

![現在のデータの通知](assets/current_data_notice.png)

## 一般的な現在のデータの遅延

指標は、次の 3 つの時間枠のいずれかに表示されます。「現在のデータを含む」の横の時計アイコンをクリックすると、レポートの各指標の実際の遅延値が表示されます。

| 時間枠 | 指標 |
| --- | --- |
| 10 分以内 | トラフィック変数のインスタンスとページビュー |
| 10 ～ 35 分 | コンバージョン変数のコンバージョンイベント、インスタンス、ページビュー |
| 45 ～ 120 分 | 訪問数、ユニーク訪問者、パーティシペーションなど、その他すべてのデータ |

現在のデータ表示に表示されるデータには完全に処理されていないデータも含まれるので、現在のデータ表示とファイナライズされた表示の値に違いがある場合があります。通常、トレンドレポートでのデータの相違は 1% 以内です。

## 計算指標

計算指標は遅延が異なる指標を使用して作成できるため、現在のデータ表示の不完全なデータを使用して最新の値が計算されることがあります。

例えば、数式「`Page Views divided by Visits`」を使用して「訪問あたりのページビュー数」という計算指標を作成したとします。ページビューは通常 10 分以内に表示され、訪問は通常 2 時間以内に表示されます。この遅延期間以内の計算指標は不完全な指標を使用して計算されることになります。2 時間の時間枠で 4,000 件の異なる訪問による 4,000 ヒットがある新しいページを公開した場合、これらの指標の間の遅延の差により、不完全な計算がおこなわれます。

このデータ差は新しい値でレポートを作成するときや非常に短い時間枠を使用するときに顕著になります。レポートでより長い日付範囲を使用する場合、レポートの直近の数時間に発生した遅延の差によって計算指標に目立った影響が及ぶことはありません。

これらの違いの影響を受ける可能性のある計算指標がある場合は、現在のデータをオフにするか、予想される待ち時間が同じ指標を使用します。

## ダウンロードしたレポート

現在のデータ表示が有効なレポートをダウンロードするとき、レポートは、キューに入れられた後、生成され、ブラウザーに返されます。レポートの生成中にデータが収集されると、そのデータがレポートに表示されます。この時間帯により、ダウンロードしたレポートのデータ量が少し増える可能性があります。
