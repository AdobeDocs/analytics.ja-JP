---
title: データレイヤーの作成
description: Analytics の実装におけるデータレイヤーと、それらを Adobe Analytics で変数のマッピングに使用する方法について説明します。
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '479'
ht-degree: 100%

---

# データレイヤーの作成

データレイヤーは、サイト上の JavaScript オブジェクトのフレームワークで、実装で使用されるすべての変数値が含まれます。データレイヤーを使用すると、実装をより詳細に制御することができ、メンテナンスが容易になります。

## 前提条件

[ソリューションデザインドキュメントの作成](solution-design.md) - 組織がトラッキング要件に合わせて調整をおこなうことが重要です。組織の開発チームに連絡する前に、ソリューションデザインドキュメントの準備が整っていることを確認します。

## ワークフロー

データレイヤーを使用して Adobe Analytics を実装する場合は、通常次の手順に従います。

1. **サイト開発チームと協力して、データレイヤーを実装します**：サイト開発チームは、主にデータレイヤーオブジェクトに正しい値が入力されることを確認する必要があります。このページをサイト開発チームと共に確認し、チーム間で期待値が一致することを確認します。

   >[!NOTE]
   >
   > アドビ推奨のデータレイヤー仕様に従うことはオプションです。データレイヤーが既に存在する場合、またはアドビの仕様に従わない場合は、どの仕様に従うかを組織で決定してください。
1. **ブラウザーコンソールを使用して、データレイヤーを検証します**：データレイヤーが作成されたら、任意のブラウザーの開発者コンソールを使用して、データレイヤーが機能していることを検証できます。デベロッパーコンソールは、`F12` キーを使用してほとんどのブラウザーで開くことができます。変数値の例は `digitalData.page.pageInfo.pageID` です。
1. **Adobe Experience Platform Launch を使用して、データレイヤーオブジェクトを Launch データ要素にマッピングします**：Launch でデータ要素を作成し、データレイヤーで概要を説明している JavaScript 属性にマップします。
1. **Launch の Adobe Analytics 拡張機能を使用して、データ要素を Analytics 変数にマップします**：ソリューションデザインドキュメントに従って、各データ要素を適切な Analytics 変数に割り当てます。

## 仕様

アドビでは、[Customer Experience デジタルデータコミュニティグループ](https://www.w3.org/community/custexpdata/)によってアウトラインされている [Customer Experience デジタルデータレイヤー](https://www.w3.org/2013/12/ceddl-201312.pdf)に従うことをお勧めします。以下の節では、データレイヤー要素と Adobe Analytics との関わり方について説明します。

包括的なデータレイヤーオブジェクトとして `digitalData` を使用することが推奨されます。次の例は、いくぶん包括的なデータレイヤーの JSON オブジェクトと例の値を示しています。

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product: [{
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            quantity: 1,
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    }],
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event: [{
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    component: [{
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    user: [{
        segment: "Premium membership",
        profile: [{
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }]
    }],
    privacy: {
        accessCategories: [{
            categoryName: "Default",
            domains: "adobedtm.com"
        }]
    },
    version: "1.0"
}
```

各オブジェクトとサブオブジェクトの詳細については、[顧客体験デジタルデータレイヤー](https://www.w3.org/2013/12/ceddl-201312.pdf)レポートを使用します。サイトはすべてのオブジェクトを使用するわけではありません。例えば、ニュースサイトをホストする場合、`digitalData.product` オブジェクト配列を使用する可能性は低くなります。

データレイヤーは拡張可能です。組織に固有の要件がある場合は、そのニーズに合わせてオブジェクトをデータレイヤーに含めることができます。

## データレイヤー値の設定

通常、データレイヤーはサーバーサイドを生成し、サイトコンテンツの構築に使用したのと同じオブジェクトを参照します。組織の[ソリューションデザインドキュメント](solution-design.md)で設定されたトラッキング要件に基づいて、サイトのデータレイヤーを設定します。

## 次の手順

[データ要素へのデータレイヤーオブジェクトのマッピング](../launch/layer-to-elements.md)：Adobe Experience Platform Launch で、サイトのデータレイヤーを使用します。
