---
title: Adobe Analytics のグローバルレポートスイート
description: グローバルレポートスイートを使用する利点と要件を理解します。
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 100%

---

# グローバルレポートスイートの考慮事項

グローバルレポートスイートは、組織が所有するすべてのドメインとアプリケーションからデータを収集するレポートスイートです。このデータ収集手法には準備が必要で、組織内のチーム間での調整が必要になる場合があります。

## メリット

アドビでは、ほとんどの場合、グローバルレポートスイートを実装することをお勧めします。

* **集計データ**：グローバルレポートスイートを使用すると、所有するサイト全体で KPI と成功イベントを確認できます。セグメント化と仮想レポートスイートを使用して、サイト固有のデータを表示できます。
* **クロスデバイス分析のサポート：** CDA では、Web サイトやモバイルアプリケーションなど、複数の場所からデータを収集するレポートスイートが必要です。別のデバイスを正しく実装すると、データをつなぎ合わせることができます。詳しくは、『コンポーネントユーザーガイド』の[クロスデバイス分析](../../components/cda/overview.md)を参照してください。
* **複数のレポートスイートは不要**：すべてのデータは 1 つのレポートスイートで収集できるので、開発者が誤って間違ったレポートスイートにデータを送信する可能性は低くなります。
* **ロールアップは不要**：ロールアップは、個々のレポートスイートのデータを日単位で集計する、かなり古い機能です。ロールアップでは、訪問や訪問者のデータの重複が除外されず、数値が水増しされる可能性があります。詳細については、『管理者ユーザーガイド』の[ロールアップ](../../admin/admin/c-manage-report-suites/rollup-report-suite.md)を参照してください。
* **時間を節約**：Workspace のプロジェクト、分類、セグメントおよび計算指標は、同じグローバルレポートスイートに結び付けられます。管理者は、これらのコンポーネントやデータガバナンスの管理に費やす時間を短縮できます。
* **より正確なクロスブランドアトリビューション**：あるサイトで訪問が開始し、その後、成功イベントをトリガーする前に所有する別のサイトに対するクリックをおこなうと、アトリビューションは正確に収集されます。例えば、訪問者が有料検索リンクをクリックしてサイト A に到着し、その後、サイト B へのリンクをクリックして購入したとします。グローバルレポートスイートは、購入を有料検索に正確に結び付けます。
* **シンプル化された実装**：すべてのブランド／サイトはデータを同じレポートスイートに送信するので、各サイトにわたる実装が一致します。この強制的なガバナンスにより、特定のディメンションまたは指標が同じ eVar またはイベントに保存されます。管理者、テスト担当者、タグ管理の所有者、アナリストは、このシンプル化のメリットを享受できます。

>[!NOTE]
>
> グローバルレポートスイートの実装の調整は、大規模なプロジェクトです。アドビでは、発生する複雑な問題を減らすためにコンサルタントと協力することをお勧めします。

## グローバルレポートスイートを使用した新しい実装の開始

グローバルレポートスイートを実装するプロセスを理解するには、次の一般的なガイドラインを使用します。

1. Adobe Analytics でグローバルレポートスイートを作成します。詳しくは、『管理者ユーザーガイド』の[レポートスイートの作成](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)を参照してください。
1. 各ドメインを担当する組織内のチームと連携します。多くのチームには、ビジネスの分野に固有のレポート要件があります。
1. これらの要件をすべて[ソリューションデザインドキュメント](solution-design.md)に記録して集計します。チームがディメンションに対して同様の要件を持つ場合は、同じカスタム変数を使用できます。例えば、サイト A とサイト B の両方に階層リンクディメンションが必要な場合、両方のサイトの実装は eVar1 を介してそのデータを送信できます。

   >[!IMPORTANT]
   >
   > 任意のカスタム変数がドメイン間で同様に使用されていることを確認します。サイト間で異なる目的で同じ eVar またはイベントを使用しないでください。
1. 各ドメインにデータ層があり、データ収集を簡略化できることを確認します。データ層を使用せずにデータを収集することはできますが、実装の信頼性と長期間は、特にサイトのデザインが変更されるにつれて減少します。
1. Adobe Experience Platform でタグを使用して Analytics を実装します。サイトごとに異なるデータ要素が必要になる場合があります。各ドメインに固有のルールを使用して、各データ要素が正しく入力されていることを確認し、それらのデータ要素をそれぞれの eVar およびイベントに割り当てます。[タグの概要](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja)を参照してください。
1. [Adobe Experience Cloud ID サービス](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ja)を含め、[appendVisitorIDsTo](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html?lang=ja) 関数を使用します。この関数は、ユーザーが 1 つのドメインから別のドメインにクリックした場合に訪問者データをマージします。

## グローバルレポートスイートを使用した既存の実装の変更

複数のサイトにわたる既存の実装を単一のグローバルレポートスイートに移動するプロセスでは、組織のグループ間でより多くの時間と調整が必要になります。

1. 既存のレポートスイートの 1 つを使用するか、新しいレポートスイートで新規に開始するかを決定します。実装内の既存の変数の用途を変更する場合は、新しいレポートスイートから開始することをお勧めします。
2. グローバルレポートスイートに切り替える日を指定します。カットオーバーをおこなうのに最適なタイミングは、2 つの重要なレポート期間の間、またはサイトへの主要な変更と同時期です。例としては、会計四半期や年度の開始、サイトの更新中の開始、新しいタグ管理システムへの変更などがあります。
3. 上記の手順に従います（レポートスイートを作成し、ソリューションデザインドキュメントでレポート要件を収集し、各サイトでデータ層を確立します）。Adobe Experience Platform でタグを実装する場合は、web サイトの開発バージョンを使用して実装を検証します。
4. 実装が開発に対して動作していることを確認したら、カットオーバーの日にタグの実装をプッシュします。

## 関連ページ

[複数のスイートタグ付けからグローバルレポートスイートおよび仮想レポートスイートへの移行ロールアップ](../../components/vrs/vrs-considerations.md)
[グローバルレポートスイートの比較](../../admin/admin/c-manage-report-suites/rollup-report-suite.md)
