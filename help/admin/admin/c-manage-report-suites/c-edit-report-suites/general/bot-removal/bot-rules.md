---
description: ボットルールを使用すると、既知のスパイダーやボットによって生成されるトラフィックを、レポートスイートから削除できます。ボットトラフィックを削除すると、web サイト上のユーザーアクティビティをより正確に測定できます。
title: ボットルールの理解と設定
feature: Bot Removal
role: Admin
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '1668'
ht-degree: 69%

---

# ボットルールの理解と設定

ボットルールを使用すると、既知のスパイダーやボットによって生成されるトラフィックをレポートスイートから削除できます。ボットトラフィックを削除すると、web サイト上のユーザーアクティビティをより正確に測定できます。

ボットルールを定義すると、すべての受信トラフィックを定義済みのルールを比較します。これらのルールのいずれかと一致するトラフィックは、レポートスイートで収集されず、トラフィック指標には含まれません。

通常、ボットトラフィックを削除すると、トラフィックの量が減り、コンバージョン指標が下がります。多くのお客様は、ボットトラフィックを削除すると、コンバージョン率が向上し、他のユーザビリティ指標が増加することに気がつきます。

ボットトラフィックデータは、ボットレポートとボットページレポートに表示するために、個別のリポジトリに保存されます。

>[!NOTE]
>
>Adobe Experience Platform Edge Network は、 [ボット検出サービス](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html?lang=ja) ボットからのヒットとして識別されるヒットのラベルを示すもの。 Adobe Analyticsで使用されるボット検出プロセスは別々で、Edge ネットワークを通じて到着したデータに含まれるボットスコアを参照しません。 ただし、2 つのシステムは同じ IAB ボットリストを使用します。

## ボットルールの更新またはアップロード

>[!IMPORTANT]
>
>ボットトラフィックを削除する前に、関係者に連絡して、この削除を行った場合に、主要業績評価指標に必要な調整を加えることができるかどうかを確認します。調整が可能な場合は、最初に小規模なレポートスイートからボットトラフィックを削除して、発生する可能性がある影響を予測することをお勧めします。

次のビデオでは、ボットルールの設定方法を説明します。

>[!VIDEO](https://video.tv.adobe.com/v/335738/?quality=12)

ボットルールを更新またはアップロードするには：

1. に移動します。 **[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]**.

1. ボットルールを更新するレポートスイートを選択し、 **[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL ボットルール]**.

1. 次のいずれかのオプションを使用して、レポートスイートのボットルールを更新またはアップロードします。

   * 選択 [!UICONTROL **IAB ボットフィルタリングルールの有効化**] :IAB(International Advertising Bureau) の「International Spiders &amp; Bots List」でボットを削除してボットトラフィックを削除します。

     少なくとも、このオプションを選択することをお勧めします。

     詳しくは、以下の節を参照してください。 [標準 IAB ボットルール](#standard-iab-bot-rules).

   * 選択 [!UICONTROL **ルールを追加**] ：ユーザーエージェント、IP アドレス、IP 範囲に基づいてカスタムボットルールを定義し、追加する場合。

     詳しくは、以下の節を参照してください。 [カスタムボットルール](#custom-bot-rules).

   * 次の [!UICONTROL **インポートする CSV ボットファイルを選択**] 領域、選択 [!UICONTROL **ファイルを選択**]」をクリックし、ボットルールを定義する CSV ファイルを選択します。

     詳しくは、以下の節を参照してください。 [ボットルールのアップロード](#upload-bot-rules).

1. 「[!UICONTROL **保存**]」を選択します。

## 標準 IAB ボットルール

標準 IAB ボットルールは、「[!UICONTROL IAB ボットフィルタールールを有効にする]」チェックボックスをオンにすることで有効にできます。この選択により、ボットトラフィックを削除するために、IAB（International Advertising Bureau）の「International Spiders &amp; Bots List」のボットが削除されます。アドビは、IAB からこのリストを毎月更新します。

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-iab-checkbox.png)

アドビは詳細な IAB ボットリストをお客様に提供できませんが、ボットレポートを使用して、サイトにアクセスしたボットのリストを表示できます。ボットを IAB リストに送信するには、[IAB](https://www.iab.com) にアクセスします。

レポートスイートで標準 IAB ボットルールを有効にする方法について詳しくは、 [ボットルールの更新またはアップロード](#update-or-upload-bot-rules).

## カスタムボットルール

>[!NOTE]
>
>：ユーザーインターフェイスでは 500 個のルールを手動で定義することが可能です。この制限を超える場合は、「ファイルのインポート」および「ボットルールをエクスポート」オプションを使用して、ルールを一括処理する必要があります。

カスタムボットルールを使用すると、定義した条件に基づいてトラフィックをフィルタリングできます。 レポートスイートでカスタムボットルールを有効にするプロセスを開始するには、 [ボットルールの更新またはアップロード](#update-or-upload-bot-rules).

カスタムボットルールは、次の条件タイプを使用して定義されます。

* ユーザーエージェント
* IP アドレス
* IP 範囲

1 つのルールに複数の条件を定義できます。複数の条件で照合するには、「or」を使用します。例えば、ユーザーエージェントに関する値と IP アドレスを指定した場合、いずれかの条件に適合した場合にボットトラフィックと見なされます。

### ユーザーエージェント

ユーザーエージェントの条件では、そのユーザーエージェントの値を調べて、指定した文字で&#x200B;**[!UICONTROL 始まる]**&#x200B;か、その文字を&#x200B;**[!UICONTROL 含む]**&#x200B;かを判断します。「**[!UICONTROL 次を含む]**」を選択した場合、ユーザーエージェントの任意の場所に指定した文字が含まれていれば、一致と見なされます。

オプションの値を「**[!UICONTROL 次を含まない]**」リストに含めることで、照合を正常に行うためにユーザーエージェントに含めない値を定義できます。複数の値を指定するには、1 行に 1 つの値を設定します。ユーザーエージェントが照合文字列で指定した条件に一致するとき、「次を含まない」リスト内の文字列も含んでいる場合は、一致と見なされません。

「**[!UICONTROL 次を含む]**」フィールドに入力できるのは 100 文字までです。「次を含まない」リストに入力できる文字数は、255 文字から、各改行の区切り文字の数を引いた文字数です（区切り文字の数は文字列の数から 1 を引いた数になります。例えば、4 つの「*次を含まない*」文字列を指定する場合、3 つの区切り文字が必要です）。すべての文字列照合では、大文字と小文字が区別されません。

### IP アドレス（ワイルドカードの照合を含む）

1 つの IP アドレスと照合するか、ワイルドカード（&#42;）を使用して同じブロック内の複数のアドレスと照合します。照合する IP アドレスの数値を指定します。ワイルドカードを使用して照合する場合、どのような値にも一致させたい部分に &#42; を使用します。次に、IP アドレスの照合文字列の例を示します。

```
10.10.10.1
10.10.10.*
```

### IP アドレスの範囲

照合する IP アドレスの開始と終了の範囲を指定します。ワイルドカードを使用して照合する場合、どのような値にも一致させたい部分に &#42; を使用します。

### カスタムボットルールを定義する

1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**&#x200B;に移動し、1 つまたは複数のレポートスイートを選択して、**[!UICONTROL 一般]**／**[!UICONTROL ボットルール]**&#x200B;をクリックします。
1. 「**[!UICONTROL ルールの追加]**」をクリックし、1 つまたは複数の照合条件を定義します。
1. 「**[!UICONTROL 保存]**」をクリックします。変更が反映されるまで、最大 30 分かかります。

## ボットルールのアップロード

ボットルールを一括してインポートするには、ルールを定義した CSV ファイルをアップロードします。

1. レポートスイートへのボットルールのアップロードプロセスを開始するには、 [ボットルールの更新またはアップロード](#update-or-upload-bot-rules).

1. 次の列と、スプレッドシートの 1 行目の、および順番を指定して CSV ファイルを作成します。

   | 列 1、行 1 | 列 2、行 1 | 列 3、行 1 | 列 4、行 1 | 列 5、行 1 | 列 6、行 1 |
   |--- |--- |---|---|---|---|
   | ボットの名前 | IP の開始 | IP の終了値 | ルール<br>（「次を含む」または「次で始まる」）</br> | ユーザーエージェントの含む | 除外するユーザーエージェント<br>（上限 255 文字）</br> |

   次の 3 種類のボットルールを定義できます。

   * 「次を含む」または「次で始まる」ユーザーエージェント
   * 単一の IP アドレスまたはワイルドカードの一致
   * IP 範囲の一致

   インポートファイルの各行には、次のボット定義の 1 つのみを含めることができます。

   >[!NOTE]
   >
   >   （ユーザーエージェント「または」IP アドレスなどのように）OR を使用した複数のルールの組み合わせによってボットを照合するには、組み合わせるすべてのルールについて、「ボットの名前」フィールドに同じ名前を指定します。AND 一致はサポートされません。


   * **「次を含む」または「次で始まる」ユーザーエージェント**：以下を含むエージェント列に、照合する 1 つのユーザーエージェント文字列を指定します。「エージェントの一致ルール」フィールドに、「*次を含む*」または「*次で始まる*」を入力して、実行する照合のタイプを指定します。「以下を含まないエージェント」列には、必要に応じて値を指定できます。この値は、エージェントに含まれない 1 つまたは複数の文字列をパイプ記号（`|`）で区切って定義します。文字列の照合では、大文字と小文字が区別されません。「IP の開始値」列と「IP の終了値」列の両方は、空にする必要があります。

   * **単一の IP アドレスまたはワイルドカードの一致**：単一の IP アドレス（`10.10.10.1`）またはワイルドカード IP アドレス（`10.10.*.*`）を一致させるには、「IP の開始値」列と「IP の終了値」列の両方に同じ値を指定します。「一致ルール」、「以下を含むエージェント」、「以下を含まないエージェント」は空にする必要があります。

   * **IP 範囲の一致**：IP の開始値列と IP の終了値列を使用して、IP アドレスの範囲を定義します。IP 範囲の一致にワイルドカードを使用できます（例：`10.10.10.*` から `10.10.20.*`）「一致ルール」、「以下を含むエージェント」、「以下を含まないエージェント」は空にする必要があります。

1. Report Suite Manager のボットルールページで、 [!UICONTROL **インポートする CSV ボットファイルを選択**] 領域、選択 [!UICONTROL **ファイルを選択**]」をクリックし、インポートするボットルールを定義する CSV ファイルを選択します。

1. （オプション） **[!UICONTROL 既存のルールを上書き]** 」チェックボックスをオンにして、既存のルールをすべて削除し、アップロードファイルに定義されているルールで置き換えます。

1. 選択 [!UICONTROL **ファイルを読み込み**].

1. Adobe Analytics の [!UICONTROL **ルールセット**] 「 」領域で、読み込まれたルールを確認します。

1. 「[!UICONTROL **保存**]」を選択します。

## ボットルールの書き出し

UI に定義されているすべてのルールを CSV 形式で書き出すには：

1. に移動します。 **[!UICONTROL Analytics]** > **[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]**.

1. 書き出すボットルールを含むレポートスイートを選択し、「 」を選択します。 **[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL ボットルール]**.

1. 選択 **[!UICONTROL ボットルールの書き出し]**&#x200B;をクリックし、CSV ファイルをファイルシステムに保存します。

## データ収集に対するボットルールの影響 {#section_F01A3130E7A04A9993371CF26F6586F2}

ボットルールは、すべての解析データに適用されます。ボットルールによって削除されたデータは、ボットレポートとボットページレポートにのみ表示されます。

ボットルールの後に VISTA ルールが適用されます。テクニカルノートユーザーガイドの[処理順序](/help/technotes/processing-order.md)を参照してください。

**高ヒット訪問の処理**：訪問において 100 を超えるヒットが発生した場合、訪問において経過した時間（秒数）が訪問のヒット数以下かどうかを判定します。このような場合、長く集中的な訪問はデータを処理する時間がかかるので、訪問が強制的に終了され、新たな訪問として計測が継続されます。一般に、高ヒットの訪問はボット攻撃によるもので、通常の訪問者による閲覧とは考えられません。

>[!NOTE]
>
>*`bots`* としてマークされたヒットは[サーバーコール](/help/admin/admin/c-server-call-usage/overage-overview.md)として請求されます。

## ボットフィルタリングに対する IP の不明化の影響 {#section_92E60B95BE8940D983F28C79E0CD6B12}

IAB ボットリストはユーザーエージェントにのみ基づいているため、このリストを使用したフィルタリングは IP の不明化の設定に影響を受けません。非 IAB ボットフィルタリング（カスタムルール）の場合は、IP をフィルタリング条件の一部とすることができます。IP を使用してボットをフィルタリングする場合、その設定が有効であれば、最後のオクテットが削除された後、IP 全体の削除や一意 ID での IP の置換など他の IP 不明化オプションの実行前に、ボットフィルタリングが行われます。

つまり、IP の不明化を有効にすると、IP アドレスが不明化される前に IP の除外が行われるので、設定の変更などの対応は不要です。

最後のオクテットが削除されると、IP フィルタリングの前に行われます。最後のオクテットが 0 に置換されるので、末尾が 0 の IP アドレスに一致するように IP 除外ルールを更新します。「&#42; に一致」は、0 にも一致します。
