---
description: 訪問者 ID による他の方法が失敗した場合、アドビでは、フォールバック cookie を設定するか、IP アドレスとユーザーエージェントの組み合わせを使用して訪問者を識別します。
keywords: Analytics の導入
seo-description: 訪問者 ID による他の方法が失敗した場合、アドビでは、フォールバック cookie を設定するか、IP アドレスとユーザーエージェントの組み合わせを使用して訪問者を識別します。
seo-title: フォールバックIDメソッド
solution: Analytics
title: フォールバックIDメソッド
topic: 開発者と導入
uuid: f242d481-81f0-4287- be4f-52fd03eb01fc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# フォールバックIDメソッド

訪問者 ID による他の方法が失敗した場合、アドビでは、フォールバック cookie を設定するか、IP アドレスとユーザーエージェントの組み合わせを使用して訪問者を識別します。

## フォールバック訪問者の識別方法 {#section_2BA15E4FA6034C3EBF43859406343EB6}

JavaScript 1.x 版 AppMeasurement と JavaScript H.25.3（2013 年 1 月リリース）以降のバージョンは、アドビのデータ収集サーバーによって設定される cookie（`s_vi`）をブロックするブラウザーを使用している訪問者を対象とした、新しいフォールバック訪問者の識別方法を備えています。以前は、cookie を設定できない場合、データ収集時に IP アドレスとユーザーエージェント文字列の組み合わせを使用して訪問者を識別していました。

この更新により、標準的な `s_vi` cookie を使用できない場合は、ランダムに生成された一意の ID を使用して、Web サイトでフォールバック cookie が作成されます。この cookie は `s_fid` と呼ばれ、2 年間の有効期限付きで設定され、今後のフォールバック識別方法として使用されます。This change should result in increased accuracy in visit and visitor counts in situations where the primary cookie ( `AMCV_` or `s_vi`) cannot be set.

訪問総数には、`s_vi` cookie またはフォールバック方法を使用して識別されたすべての訪問者が含まれます。

## IP アドレス、ユーザーエージェント、ゲートウェイ IP アドレス {#section_104819D74C594ECE879144FCC5DEF4BF}

 の呼び出しの後におこなわれる場合です。If the `AMCV_` or `s_vi` and the `s_fid` cookies cannot be set, visitors are identified using a combination of IP address and User Agent.
