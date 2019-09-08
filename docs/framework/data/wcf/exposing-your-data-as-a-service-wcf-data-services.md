---
title: 将数据公开为服务（WCF 数据服务）
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
ms.openlocfilehash: 1dc1f0ec12c50c4c97b141a34b468e3367ead75e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780299"
---
# <a name="expose-your-data-as-a-service-wcf-data-services"></a><span data-ttu-id="5ec4a-102">将数据公开为服务（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="5ec4a-102">Expose Your Data as a Service (WCF Data Services)</span></span>

<span data-ttu-id="5ec4a-103">WCF 数据服务与 Visual Studio 集成，使你能够更轻松地定义服务，以将你[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]的数据公开为源。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-103">WCF Data Services integrates with Visual Studio to enable you to more easily define services to expose your data as [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feeds.</span></span> <span data-ttu-id="5ec4a-104">创建公开 OData 源的数据服务涉及以下基本步骤：</span><span class="sxs-lookup"><span data-stu-id="5ec4a-104">Creating a data service that exposes an OData feed involves the following basic steps:</span></span>

1. <span data-ttu-id="5ec4a-105">**定义数据模型。**</span><span class="sxs-lookup"><span data-stu-id="5ec4a-105">**Define the data model.**</span></span> <span data-ttu-id="5ec4a-106">WCF 数据服务本身支持基于[ADO.NET 实体框架](../adonet/ef/index.md)的数据模型。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-106">WCF Data Services natively supports data models that are based on the [ADO.NET Entity Framework](../adonet/ef/index.md).</span></span> <span data-ttu-id="5ec4a-107">有关详细信息，请参阅[如何：使用 ADO.NET 实体框架数据源](create-a-data-service-using-an-adonet-ef-data-wcf.md)创建数据服务。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-107">For more information, see [How to: Create a Data Service Using an ADO.NET Entity Framework Data Source](create-a-data-service-using-an-adonet-ef-data-wcf.md).</span></span>

     <span data-ttu-id="5ec4a-108">WCF 数据服务还支持基于公共语言运行时（CLR）对象的数据模型，这些对象返回<xref:System.Linq.IQueryable%601>接口的实例。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-108">WCF Data Services also supports data models that are based on common language runtime (CLR) objects that return an instance of the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="5ec4a-109">通过此功能，您可以在 .NET Framework 中部署基于列表、数组和集合的数据服务。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-109">This enables you to deploy data services that are based on lists, arrays, and collections in the .NET Framework.</span></span> <span data-ttu-id="5ec4a-110">若要启用针对这些数据结构的创建、更新和删除操作，还必须实现 <xref:System.Data.Services.IUpdatable> 接口。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-110">To enable create, update, and delete operations over these data structures, you must also implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="5ec4a-111">有关详细信息，请参阅[如何：使用反射提供程序](create-a-data-service-using-rp-wcf-data-services.md)创建数据服务。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-111">For more information, see [How to: Create a Data Service Using the Reflection Provider](create-a-data-service-using-rp-wcf-data-services.md).</span></span>

     <span data-ttu-id="5ec4a-112">对于更高级的方案，WCF 数据服务包括一组提供程序，使你能够基于后期绑定数据类型定义数据模型。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-112">For more advanced scenarios, WCF Data Services includes a set of providers that enable you to define a data model based on late-bound data types.</span></span> <span data-ttu-id="5ec4a-113">有关详细信息，请参阅[自定义数据服务提供程序](custom-data-service-providers-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-113">For more information, see [Custom Data Service Providers](custom-data-service-providers-wcf-data-services.md).</span></span>

2. <span data-ttu-id="5ec4a-114">**创建数据服务。**</span><span class="sxs-lookup"><span data-stu-id="5ec4a-114">**Create the data service.**</span></span> <span data-ttu-id="5ec4a-115">大多数基本数据服务公开一个从 <xref:System.Data.Services.DataService%601> 类继承的类和一个作为实体容器的命名空间限定名称的 `T` 类型。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-115">The most basic data service exposes a class that inherits from the <xref:System.Data.Services.DataService%601> class, with a type `T` that is the namespace-qualified name of the entity container.</span></span> <span data-ttu-id="5ec4a-116">有关详细信息，请参阅 [Defining WCF Data Services](defining-wcf-data-services.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-116">For more information, see [Defining WCF Data Services](defining-wcf-data-services.md).</span></span>

3. <span data-ttu-id="5ec4a-117">**配置数据服务。**</span><span class="sxs-lookup"><span data-stu-id="5ec4a-117">**Configure the data service.**</span></span> <span data-ttu-id="5ec4a-118">默认情况下，WCF 数据服务禁用对由实体容器公开的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-118">By default, WCF Data Services disables access to resources that are exposed by an entity container.</span></span> <span data-ttu-id="5ec4a-119">使用<xref:System.Data.Services.DataServiceConfiguration>接口可以配置对资源和服务操作的访问，指定受支持的 OData 版本，还可以定义其他服务范围的行为，例如批处理行为或可返回的最大实体数在单个响应中。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-119">The <xref:System.Data.Services.DataServiceConfiguration> interface enables you to configure access to resources and service operations, specify the supported version of OData, and to define other service-wide behaviors, such as batching behaviors or the maximum number of entities that can be returned in a single response.</span></span> <span data-ttu-id="5ec4a-120">有关详细信息，请参阅[配置数据服务](configuring-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-120">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>

<span data-ttu-id="5ec4a-121">有关如何创建基于 Northwind 示例数据库的简单数据服务的示例，请参阅[快速入门](quickstart-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="5ec4a-121">For an example of how to create a simple data service that is based on the Northwind sample database, see [Quickstart](quickstart-wcf-data-services.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ec4a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ec4a-122">See also</span></span>

- [<span data-ttu-id="5ec4a-123">入门</span><span class="sxs-lookup"><span data-stu-id="5ec4a-123">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
- [<span data-ttu-id="5ec4a-124">概述</span><span class="sxs-lookup"><span data-stu-id="5ec4a-124">Overview</span></span>](wcf-data-services-overview.md)
