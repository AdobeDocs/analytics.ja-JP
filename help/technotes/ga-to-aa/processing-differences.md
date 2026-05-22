---
title: 分析プラットフォーム間の処理方法とアーキテクチャの違い
description: Adobe Analytics や Google Analytics などの複数のプラットフォーム間で、一部のデータの収集方法と表示方法が異なる場合について説明します。
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
TQID: 'https://experienceleague.adobe.com/pL36oKany2sKuJrEn4-oIja3O91PZ47YQGoNvhdt6y8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: a60fda7a-bb0b-4eb6-b9fe-77558cbee1fa
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 96%

---

# 分析プラットフォーム間の処理方法とアーキテクチャの違い

Adobe Analytics と Google Analytics はどちらも分析ツールですが、データの収集方法と処理方法が大きく異なります。 このページでは、特定のディメンションと指標の収集方法に関する主な違いと、同様のレポートで異なる数値が表示される理由について説明します。

## [!UICONTROL バウンス率]

[!UICONTROL バウンス率]は、多くの分析ツールでランディングページの効果と関連性を測定するために使用される一般的な KPI です。 これは一般に、web サイトを訪問したユーザーがランディングページで何も操作せずにそのままサイトから離脱した数を指します。

* Adobe Analytics では、[!UICONTROL バウンス率]は「**バウンス数 ÷ エントリー回数**」の式を使用して算出されます。
* Google Analytics では、[!UICONTROL バウンス率]は「**単一ページのセッション数 ÷ セッション数**」の式を使用して算出されます。

どちらのプラットフォームでも、1 回の訪問またはセッションで複数のヒットが送信された場合はバウンスとはみなされません。 Adobe Analytics ではカスタムリンクを使用できます。カスタムリンクをクリックしたことによる訪問は、バウンスとはみなされません。 Google Analytics は通常、1 つのページで複数のデータリクエストを送信しません。

レポートツール間のパリティを高めるには、[!UICONTROL バウンス]ではなく Adobe Analytics の[!UICONTROL 単一ページ訪問]指標を計算指標の一部として使用します。 [!UICONTROL 単一ページ訪問]指標には、単一ページビューのみを含む訪問数、または Web サイトにアクセスしたが別のページへのクリックを含まない訪問の総数が含まれます。

詳しくは、コンポーネントユーザーガイドの「[バウンス率](/help/components/metrics/bounce-rate.md)」を参照してください。

## [!UICONTROL 訪問回数とセッション数]

[!UICONTROL 訪問回数]（Google Analytics ではセッション数）は、同じユーザーが短時間におこなったページビューのグループです。 どちらのプラットフォームでも、訪問回数は通常、[!UICONTROL 無操]作状態が 30 分間続くと期限が切れます。 どちらのプラットフォームでも、[!UICONTROL 訪問回数]の期限が切れる時間をカスタマイズできます。 プラットフォーム間で違いが発生する原因となるシナリオは、複数考えられます。

* **日の終わり：** Google Analyticsのすべてのセッションは、特定の日の午後11:59後に期限切れになります。 午前 12:00 以降もユーザーが Web サイトでアクティブな状態のままの場合は、新しいセッションが作成されます。 Adobe Analytics では、翌日も続く訪問はすべて同じ訪問として扱います。
* **異なるキャンペーン：** Google Analytics の新しいセッションは、ユーザーのキャンペーンソースが変更されると開始されます。 Adobe Analytics に新しい[!UICONTROL トラッキングコード]値が表示される場合、それは同じ訪問の一部とみなされます。
* **手動によるセッションの上書き：** Google Analytics では、`sessionControl` を使用してセッションを手動で開始または終了すると、新しいセッションが開始されます。 [!UICONTROL Adobe Analytics では、訪問を手動で終了することはできません。]
* **Adobe Analytics における外れ値の訪問の検出：Adobe Analytics では、ユーザーが 12 時間連続して操作をおこなった場合、2500 ヒットまたは 100 秒以内に 100 ヒットに達した場合に、**&#x200B;新しい[!UICONTROL 訪問]が自動的に開始されます。 これらの各検出条件は通常、ボットアクティビティによってトリガーされます。

詳しくは、コンポーネントユーザーガイドの「[訪問回数指標](/help/components/metrics/visits.md)」を参照してください。
