---
description: ユーザーがサイトに訪問すると、ブラウザーへの HTTP 応答に cookie を含めることで、アドビの Web サーバーによって持続的 cookie が設定されます。この cookie は、指定されたデータ収集ドメインに対して設定されます。
keywords: Analytics の導入
seo-description: ユーザーがサイトに訪問すると、ブラウザーへの HTTP 応答に cookie を含めることで、アドビの Web サーバーによって持続的 cookie が設定されます。この cookie は、指定されたデータ収集ドメインに対して設定されます。
seo-title: Analytics 訪問者 ID
solution: Analytics
title: Analytics 訪問者 ID
topic: 開発者と導入
uuid: fa7737cc-0190-4d27- af1b-87301a715df2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Analytics 訪問者 ID

ユーザーがサイトに訪問すると、ブラウザーへの HTTP 応答に cookie を含めることで、アドビの Web サーバーによって持続的 cookie が設定されます。この cookie は、指定されたデータ収集ドメインに対して設定されます。

リクエストがアドビのデータ収集サーバーに送信されると、ヘッダーで訪問者 ID cookie（`s_vi`）の有無がチェックされます。この cookie がリクエストに含まれている場合、この cookie を使用して訪問者が識別されます。この cookie がリクエストに含まれていない場合、サーバーは一意の訪問者 ID を生成し、それを HTTP 応答ヘッダー内に cookie として設定した後、リクエストとともに返送します。この cookie はブラウザーに保存され、以後にサイトを訪問したときにデータ収集サーバーに渡されます。これにより、以後の訪問時にその訪問者を識別できるようになります。

## サードパーティ cookie と CNAME レコード {#section_61BA46E131004BB2B75929C1E1C93139}

Apple Safari などのブラウザーによっては、現在の Web サイトのドメインと一致しないドメインから HTTP ヘッダーに設定される cookie については保存しないものもあります。例えば、`mysite.com` を表示しているとき、データ収集サーバーが `mysite.omtrdc.net` である場合は、`mysite.omtrdc.net` からの HTTP ヘッダーで返された Cookie はブラウザーによって拒否される可能性があります。

この問題を回避するために、多くのお客様は[ファーストパーティ cookie を導入する](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)中で、データ収集サーバーの CNAME レコードを導入しています。お客様のドメインのホスト名をデータ収集サーバーにマッピングするように CNAME レコードを設定すると（例えば、`metrics.mysite.com` を `mysite.omtrdc.net` にマッピングする）、データ収集ドメインは Web サイトのドメインと一致するので、訪問者 ID cookie が保存されます。これによって訪問者 ID cookie が保存される可能性が高まりますが、CNAME レコードを設定し、データ収集サーバーの SSL 証明書を保持する必要があるので、ある程度のオーバーヘッドが生じます。

## モバイルデバイスの cookie {#section_7D05AE259E024F73A95C48BD1E419851}

cookie を使用してモバイルデバイスをトラッキングする場合、測定の実施方法を変更するために使用できる設定がいくつかあります。cookie の有効期間はデフォルトで 5 年ですが、CL クエリパラメーター変数（`s.cookieLifetime`）を使用してデフォルト設定を変更できます。CNAME 実装での cookie の場所を設定するには、CDP クエリ文字列 `s.cookieDomainPeriods` を使用します。値を指定しない場合のデフォルト値は 2 です。デフォルトの場所は domain.com です。CNAME を使用しない実装では、訪問者 ID cookie の場所は 2o7.net ドメインになります。
