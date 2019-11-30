---
title: 如何：使用反射提供程序自定义源（WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: d3e2d587978a4c82784c8cfc8a7acc17cf601c3a
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569150"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="4cb00-102">如何：使用反射提供程序自定义源（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="4cb00-102">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>
<span data-ttu-id="4cb00-103">WCF 数据服务使你能够在数据服务响应中自定义 Atom 序列化，以便可以将实体的属性映射到在 AtomPub 协议中定义的未使用的元素。</span><span class="sxs-lookup"><span data-stu-id="4cb00-103">WCF Data Services enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="4cb00-104">本主题演示如何为使用反射提供程序定义的数据模型中的实体类型定义映射特性。</span><span class="sxs-lookup"><span data-stu-id="4cb00-104">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="4cb00-105">有关详细信息，请参阅[源自定义](feed-customization-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="4cb00-105">For more information, see [Feed Customization](feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="4cb00-106">主题[如何：使用反射提供程序创建数据服务](create-a-data-service-using-rp-wcf-data-services.md)中定义了此示例的数据模型</span><span class="sxs-lookup"><span data-stu-id="4cb00-106">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cb00-107">示例</span><span class="sxs-lookup"><span data-stu-id="4cb00-107">Example</span></span>  
 <span data-ttu-id="4cb00-108">在以下示例中，`Order` 类型的两个属性均映射到现有的 Atom 元素。</span><span class="sxs-lookup"><span data-stu-id="4cb00-108">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="4cb00-109">`Product` 类型的 `Item` 属性映射到单独的命名空间中的自定义源特性。</span><span class="sxs-lookup"><span data-stu-id="4cb00-109">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="4cb00-110">示例</span><span class="sxs-lookup"><span data-stu-id="4cb00-110">Example</span></span>  
 <span data-ttu-id="4cb00-111">上面的示例为 URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` 返回以下结果。</span><span class="sxs-lookup"><span data-stu-id="4cb00-111">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="4cb00-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cb00-112">See also</span></span>

- [<span data-ttu-id="4cb00-113">反射提供程序</span><span class="sxs-lookup"><span data-stu-id="4cb00-113">Reflection Provider</span></span>](reflection-provider-wcf-data-services.md)
