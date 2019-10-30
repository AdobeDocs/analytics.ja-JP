---
description: Adobe Analytics が収集するデータの概要とプライバシーに関する他の考慮事項
keywords: プライバシー
seo-description: Adobe Analytics が収集するデータの概要とプライバシーに関する他の考慮事項です。
seo-title: プライバシーの概要
solution: Analytics
title: プライバシーの概要
uuid: f19a8b35-3e10-47ae-93c1-6a9924b11313
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# プライバシーの概要

Adobe Analytics が収集するデータの概要とプライバシーに関する他の考慮事項です。

## 収集されるデータの詳細 {#section_F59D958D7AE44747846993E643CD4BF2}

Adobe Analytics は次のデータを収集します。

| データの種類 | Adobe Analytics によるデータ収集の有無 |
|---|---|
| 顧客サイト内の Web ページの URL | ○ |
| Web ページの名前 | ○ |
| ページでの滞在時間 | ○ |
| 時刻 | ○ |
| 非提携サイトの Web ページの URL | **×** |
| Cookie ID（ランダム生成） | ○ |
| 顧客ページにアクセスする前にユーザーが利用していたページの URL | ○ |
| 消費者が顧客ページへのリンクをクリックしたときの検索クエリ | ○ |
| ブラウザーのタイプ | ○ |
| デバイスタイプ | ○ |
| オペレーティングシステム | ○ |
| ISP／接続速度 | ○ |
| 表示設定（画面サイズと解像度） | ○ |
| IP アドレス（場所の推定に使用） | ○* |
| 顧客サイト上に用意されているフォームに消費者が入力した情報 | ○ |
| ソーシャルサイト上に用意されているフォームに消費者が入力した情報 | **×** |
| 消費者が広告をクリックしたかどうか | ○ |
| 消費者がサイト上のリンク、画像またはテキストをクリックしたかどうか | ○ |
| 消費者がファイルや画像などをダウンロードしたかどうか | ○ |
| 消費者が購入したアイテム | ○ |
| 買い物かごに残っているアイテム | ○ |
| ソーシャルネットワーク情報（写真、ユーザー ID、年齢、性別、場所など） | **×** |
| ユーザーがサービス以外から指定した個人情報 | ○ |
| 広告キャンペーンの成功率 | ○ |
| 製品情報（カラー、価格、スタイル、写真など） | ○ |

* アドビの顧客が IP の削除を選択していない場合に限ります。

## プライバシーに関する他の考慮事項 {#section_60AF6AD6FBD046EEAF9F083A9726EF8A}

<table id="table_247B425E774F403288233824870D070E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 地域/国 </th> 
   <th colname="col2" class="entry"> 考慮事項 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> グローバル </td> 
   <td colname="col2"> 個人の身元を特定できる情報（PII）をアドビに渡さないようにすることを強くお勧めします。特に、Analytics が PII を必要としていない状況では避けてください。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> グローバル </td> 
   <td colname="col2"> プロファイリングの際は、ユーザーに通知と選択肢を提示する必要があります。これは、カナダ、オーストラリア、欧州連合（一部の国ではオプトイン）、ラテンアメリカとアジア太平洋の多くの国では法律で義務付けられています。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> グローバル </td> 
   <td colname="col2"> ファーストパーティ cookie を使用する場合、Analytics オプトアウトは顧客固有となります。オプトアウトを Adobe.com に依存することはできません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> グローバル </td> 
   <td colname="col2"> ファーストパーティ分析は、オンライン行動広告に関する自主規制プログラム(「AdChoices」)の対象外です。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> グローバル </td> 
   <td colname="col2"> 顧客から提供される ID（ユーザー名のハッシュなど）に関連付けられていないデバイス間データを結合してはなりません。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> グローバル </td> 
   <td colname="col2"> 一般に、顧客にはアドインプレッションの結合から PII までの制限が課せられます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ヨーロッパ </td> 
   <td colname="col2"> 欧州連合には、分析 cookie を厳密に必要としていない国が多くあります。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ヨーロッパ </td> 
   <td colname="col2"> アドビは、EMEA でレポートスイートを設定しているすべての顧客に対して、デフォルトで「IP の不明化（IP Obfuscation）」を「有効 - IP 削除（x.x.x.x）」に設定しています。この設定を使用すると、IP アドレスは、地域ルックアップ後の値（x.x.x.x）に完全に置き換えられ、以後、データポイントとして使用できません。 <p>この基本的な置き換え方法は、一意の特定の IP アドレスにリバースエンジニアリングできません。IP アドレスは不可逆的に不明化されており、顧客もアドビもアクセスできません。IP の不明化の他の設定について詳しくは、 </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/reference/index.html#General_Account_Settings" format="https" scope="external"> https://marketing.adobe.com/resources/help/ja_JP/reference/index.html#General_Account_Settings </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> グローバル </td> 
   <td colname="col2"> 顧客は、JavaScript測定コードのcookieの有効期間変数を「なし」、「セッション」または秒単位の別の指定値に設定できます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ヨーロッパ </td> 
   <td colname="col2"> アドビは、Adobe clientCare for Adobe Analytics（旧称SiteCatalyst）リリースバージョン14.9および15.4で有効にできる新しい「プライバシーバイデザイン」設定を開発しました。この新しい設定を有効にすると、IPアドレスがアドビによって収集されると、IPアドレスの最後のオクテット（最後の部分）が即座に値0に置き換えられます。 この不明化は、IP アドレスの地域ルックアップ（オプション）や ISP ルックアップなど、IP アドレスに対する一切の処理が行われる前に行われます。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ドイツ </td> 
   <td colname="col2"> <p>Adobe Analytics に関するデータ処理協定（DPA）をアドビとまだ交わしていない顧客は、Adobe アカウントマネージャーまたはカスタマーサクセスマネージャーに連絡してください。これらのマネージャーがアドビ法務部門と DPA を交わします。 </p> <p>アドビは、Bavarian Data Protection Authority(Bayerisches Landesamt Fuer Datenschutzaufht - bayLDA)によって確認および承認された、Analytics用のデータ処理契約(Vertrag fuer Auftargstadatenverarbeitung - ADV)を準備しました。 ADV はドイツ語と英語で使用できます。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## EMEA データセンターの所在地 {#section_3DD2329B983849D3B8C24AEF7CD8DFB3}

現在、Adobe Analytics データは、次の EMEA データセンターでホストされています。

<table id="table_65794B3790FD4B519EE89CF4F4B88314"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> アドビ名 </th> 
   <th colname="col2" class="entry"> 住所 </th> 
   <th colname="col3" class="entry"> 施設タイプ（オペレーター） </th> 
   <th colname="col4" class="entry"> サポートされているソリューションコンポーネント </th> 
   <th colname="col5" class="entry"> 認定 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AMS1 </td> 
   <td colname="col2"> <p>Luttenbergweg 4 </p> <p>Amsterdam 1101 EC </p> <p>The Netherlands </p> </td> 
   <td colname="col3"> <p>コロケーション施設 </p> <p>（Equinix） </p> </td> 
   <td colname="col4"> <p>マルチチャネル分析 </p> <p>デジタル分析 </p> </td> 
   <td colname="col5"> <p>ISO9001:2008 </p> <p>ISO14001:2004 </p> <p>OHSAS18001:2007 </p> <p>ISO27001:2005 </p> <p>ISO50001:2011 </p> <p>PCI-DSS </p> <p> <a href="https://www.equinix.com/solutions/by-services/colocation/standards-and-compliance/iso-certified-data-centers/#table" format="http" scope="external"> Equinix </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LON5 </td> 
   <td colname="col2"> <p>3 Centro </p> <p>Boundary Way </p> <p>Hemel Hempstead HP2 7SU </p> <p>UK </p> </td> 
   <td colname="col3"> <p>コロケーション施設 </p> <p>（Gyron） </p> </td> 
   <td colname="col4"> <p>マルチチャネル分析 </p> <p>デジタル分析 </p> </td> 
   <td colname="col5"> SSAE 16 </td> 
  </tr> 
 </tbody> 
</table>
