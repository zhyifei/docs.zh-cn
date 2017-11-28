---
title: "如何：启用对数据服务的访问（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 98584405b0c6a86f424f4bf82e29ea33197dfbeb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="4036a-102">如何：启用对数据服务的访问（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="4036a-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="4036a-103">在 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]中，您必须显式授予对数据服务公开的资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4036a-103">In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="4036a-104">这意味着您在创建新的数据服务之后，仍必须显式提供对实体集形式的各个资源的访问。</span><span class="sxs-lookup"><span data-stu-id="4036a-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="4036a-105">本主题演示如何启用读取和写入访问权限五个实体设置完毕后创建的 Northwind 数据服务中[快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="4036a-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="4036a-106">由于 <xref:System.Data.Services.EntitySetRights> 枚举是通过使用 <xref:System.FlagsAttribute> 定义的，因此您可以使用逻辑 OR 运算符来为单个实体集指定多个权限。</span><span class="sxs-lookup"><span data-stu-id="4036a-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4036a-107">任何可以访问该 ASP.NET 应用程序的客户端也能够访问由数据服务公开的资源。</span><span class="sxs-lookup"><span data-stu-id="4036a-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="4036a-108">在生产数据服务中，为防止对资源进行未经授权的访问，还应保护应用程序本身的安全。</span><span class="sxs-lookup"><span data-stu-id="4036a-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="4036a-109">有关详细信息，请参阅[NIB: ASP.NET 安全](http://msdn.microsoft.com/en-us/04b37532-18d9-40b4-8e5f-ee09a70b311d)。</span><span class="sxs-lookup"><span data-stu-id="4036a-109">For more information, see [NIB: ASP.NET Security](http://msdn.microsoft.com/en-us/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="4036a-110">启用对数据服务的访问</span><span class="sxs-lookup"><span data-stu-id="4036a-110">To enable access to the data service</span></span>  
  
-   <span data-ttu-id="4036a-111">在数据服务的代码中，用下列代码替换 `InitializeService` 函数中的占位符代码：</span><span class="sxs-lookup"><span data-stu-id="4036a-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="4036a-112">这使得客户端能够对 `Orders` 和 `Order_Details` 实体集进行读写访问，以及对 `Customers` 实体集进行只读访问。</span><span class="sxs-lookup"><span data-stu-id="4036a-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4036a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4036a-113">See Also</span></span>  
 [<span data-ttu-id="4036a-114">如何： 开发在 IIS 上运行的 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="4036a-114">How to: Develop a WCF Data Service Running on IIS</span></span>](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [<span data-ttu-id="4036a-115">配置数据服务</span><span class="sxs-lookup"><span data-stu-id="4036a-115">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
