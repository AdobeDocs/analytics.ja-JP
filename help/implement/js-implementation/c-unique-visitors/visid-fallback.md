---
description: 訪問者 ID による他の方法が失敗した場合、アドビでは、フォールバック cookie を設定するか、IP アドレスとユーザーエージェントの組み合わせを使用して訪問者を識別します。
keywords: Analytics Implementation
title: フォールバック ID による方法
topic: Developer and implementation
uuid: f242d481-81f0-4287-be4f-52fd03eb01fc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# フォールバック ID による方法

訪問者 ID による他の方法が失敗した場合、アドビでは、フォールバック cookie を設定するか、IP アドレスとユーザーエージェントの組み合わせを使用して訪問者を識別します。

## フォールバック訪問者の識別方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x and JavaScript H.25.3 (released January 2013) contain a new fallback visitor identification method for visitors whose browser blocks the cookie set by Adobe's data collection servers (called `s_vi`). 以前は、cookie を設定できない場合、データ収集時に IP アドレスとユーザーエージェント文字列の組み合わせを使用して訪問者を識別していました。

この更新により、標準的な `s_vi` cookie を使用できない場合は、ランダムに生成された一意の ID を使用して、Web サイトでフォールバック cookie が作成されます。この cookie は `s_fid` と呼ばれ、2 年間の有効期限付きで設定され、今後のフォールバック識別方法として使用されます。この変更により、プライマリ cookie（`AMCV_` または `s_vi`）を設定できない状況での、訪問回数と訪問者数の精度が向上します。

訪問総数には、`s_vi` cookie またはフォールバック方法を使用して識別されたすべての訪問者が含まれます。

## IP アドレス、ユーザーエージェント、ゲートウェイ IP アドレス {#section_104819D74C594ECE879144FCC5DEF4BF}

 の呼び出しの後におこなわれる場合です。`AMCV_` または `s_vi`、`s_fid` のいずれの cookie も設定できない場合、訪問者は IP アドレスとユーザーエージェントの組み合わせによって識別されます。
