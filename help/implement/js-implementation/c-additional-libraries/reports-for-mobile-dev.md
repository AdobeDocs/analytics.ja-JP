---
description: モバイルデバイスは他の訪問者と同じようにビーコンによって追跡されるので、ほとんどのレポートが利用でき、精度の高い情報が表示されます。
keywords: Analytics Implementation;reports;mobile protocols;search engines;search keywords;referring domains;referrers;geosegmentation;domains;connection type;time zone;cookies;java;javascript;monitor colors;monitor resolution;browser width;height;netscape plug-in
title: モバイルプロトコルを使用するデバイスに関するレポート
topic: Developer and implementation
uuid: 4aab125d-c131-4402-9bc8-1c7fd1bb2bee
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# モバイルプロトコルを使用するデバイスに関するレポート

モバイルデバイスは他の訪問者と同じようにビーコンによって追跡されるので、ほとんどのレポートが利用でき、精度の高い情報が表示されます。

[!DNL VISTA] は、モバイルおよび標準の方法で収集したデータを編集するために使用できます。[!UICONTROL カスタム][!UICONTROL インサイト]（[!UICONTROL prop] と [!UICONTROL eVar]）、[!UICONTROL イベント]、[!UICONTROL サイトトラフィック]および[!UICONTROL パス]レポートはすべてサポートされています。

## 検索エンジン、検索キーワード、参照ドメインおよびリファラー {#section_184D2EF9D906443FBDED04A09CDC50E9}

これらのレポートには、モバイル用ページから送信されるイメージリクエストにリファラーが入力された場合にのみ、データが含まれます。リファラーは、ホワイトペーパー『JavaScript を使用しない導入方法』で説明されているように、「r」クエリ文字列パラメーターによって入力されます。また、リファラー情報を手動でイメージリクエストに渡す必要があります。

'r'クエリ文字列パラメータには、リファラーのプロトコルを含める必要があります。 リファラーのプロトコルが含まれていない場合、リファラーレポートは入力されません。例えば、「`r=https://msn.com`not`r=msn.com`」を使用します。

## 地理特性およびドメイン {#section_2B4E9443AAFE4ECA961F9E993592E628}

地理特性レポートは、要求を送信するデバイスの IP アドレスに基づいています。モバイルデバイスではゲートウェイを使用して Adobe サーバーからイメージを要求するので、ユーザーの位置情報を判断するにはゲートウェイの IP アドレスが使用されます。ゲートウェイとその IP アドレスは大規模なネットワークに登録されるので、多くの場合、関連する位置情報は正確性に欠けます。

ドメインもゲートウェイの IP アドレスに基づいています。つまり、多くの場合、ゲートウェイを所有する通信業者の名前がドメインレポートに含まれます。仮想移動体通信事業者（MVNO）が原因で、この名前が正確でない場合があります。

## 接続タイプ {#section_0E7FA18178B848AEBB839B1694B4D691}

アドビは、携帯電話会社に属する既知の IP アドレス範囲を保持しています。既知の携帯電話会社に属する IP 範囲からヒットが受信された場合、そのヒットは、接続タイプレポートに「携帯電話会社」として表示されます。判定できない場合、モバイルトラフィックは「LAN / Wi-Fi」としてカウントされます。

## タイムゾーン、cookie、Java、JavaScript、画面の色と解像度、ブラウザーの幅と高さおよび Netscape プラグイン {#section_158C848273AE4691B4413767E849E846}

これらのレポートはすべて、JavaScript を使用してブラウザーの特定の設定を検出することによって収集されます。モバイルデバイスのイメージビーコンの作成に JavaScript は使用されないので、これらのレポートにはモバイルユーザーから収集したデータが含まれません。
