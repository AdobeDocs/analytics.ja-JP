---
description: ライブトラッキングとレポートをチェックして、統合がデータを正常にキャプチャしていることを検証します。
seo-description: ライブトラッキングとレポートをチェックして、統合がデータを正常にキャプチャしていることを検証します。
seo-title: 統合の確認
title: 統合の確認
uuid: a9a0746a-4845-41ae-919e- e85d95c305be
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Verifying the Integration{#verifying-the-integration}

ライブトラッキングとレポートをチェックして、統合がデータを正常にキャプチャしていることを検証します。

## Live Tracking {#section-9c20e8ff6b404ae09387ee07d675c9e2}

DigitalPulse Debuggerツールを使用して、DemandbaseディメンションデータがAdobe Analyticsに送信されていることを確認します。cookieを削除した後、統合コードが導入されたWebサイト上でページをリロードします。現在のIPがDemandbaseによって認識される組織にマッピングされていると仮定すると、次のような結果が得られます。

**Reports&amp; Analytics（旧称SiteCatalyst）には、次の2つのDemandbaseコンテキストデータ変数が含まれています。**

![](assets/debugger1.png)

**ターゲットmboxには、Demandbase Profileパラメーターが含まれています。**

これは、ページにTargetが実装されている場合にのみ表示され、この統合がAdobe Target用に設定されている場合は、Adobe統合ウィザードの手順4を参照してください。

![](assets/debugger2.png)

## レポート {#section-1792fe75dc3249d0ad063dfd87a89162}

Adobe統合ウィザード（手順7）を使用して自動的に作成されたダッシュボードを使用して、Adobe Analytics内のDemandbaseレポートを確認します。

または、Adobe Analyticsメニュー構造内のDemandbaseレポートに移動できます。以下のスクリーンショットを参照してください。

>[!NOTE]
>
>このデータは、導入が成功した24~48時間以内に表示されます。

![](assets/reporting1.png)

![](assets/reporting2.png)

## よくある質問 {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**「[n/a]」という意味は何ですか。**

Demandbase Data Connectorは、このデフォルト値を設定して属性が「利用不可」の日時を示します。デフォルトの設定には、次の2つのシナリオがあります。

* Demandbaseは、訪問者が会社に属していないIPアドレスから訪問していることを検出します。
* アカウント監視属性（"watch_ list"から始まる）は使用されますが、会社はアカウントウォッチリストにありません。

**Why does “[n/a]” appear more often for certain attributes? **

Demandbaseは、すべてのIPアドレスを分類し、訪問者が会社のIPから来ていない場合でもオーディエンスとオーディエンス_セグメントの属性を提供します。オーディエンスが「住居」、「ワイヤレス」、「接客サービス」などの値を返す場合、残りの属性は使用できない可能性があります。

At times, a visitor’s audience will be “SMB”, but other attributes will show “[n/a]”. つまり、Demandbaseは訪問者をスモールビジネスとして分類できますが、完全な会社プロファイルは利用できません。これは、複数のスモールビジネスが同じサービスプロバイダーまたはIPアドレスのブロックを使用している場合、最小の会社で発生します。

## Developer Considerations {#section-d33fff55bc4b4db99f82dee418ef1bc2}

実装でデフォルト値を調整する必要がある場合は、次の行を更新します。

```
_db._nonOrgMatchLabel = "[n/a]";
```

