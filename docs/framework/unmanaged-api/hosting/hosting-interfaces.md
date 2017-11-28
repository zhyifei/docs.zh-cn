---
title: "承载接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a3cad92c204fa10f72d7a9a61460f1234206cb39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-interfaces"></a><span data-ttu-id="0f900-102">承载接口</span><span class="sxs-lookup"><span data-stu-id="0f900-102">Hosting Interfaces</span></span>
<span data-ttu-id="0f900-103">本部分描述的接口以及非托管主机可用于将公共语言运行时 (CLR) 集成到其应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f900-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="0f900-104">.NET Framework 2.0 版承载接口取代了.NET Framework 版本 1.0 和 1.1 接口。</span><span class="sxs-lookup"><span data-stu-id="0f900-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="0f900-105">有两个集的接口之间的重要差异。</span><span class="sxs-lookup"><span data-stu-id="0f900-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="0f900-106">混合使用这些接口可能会导致意外的行为，不建议使用。</span><span class="sxs-lookup"><span data-stu-id="0f900-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="0f900-107">.NET Framework 版本 3.0 和 3.5 使用.NET Framework 2.0 版承载接口，并且并未引入任何宿主功能。</span><span class="sxs-lookup"><span data-stu-id="0f900-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="0f900-108">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]承载接口取代.NET Framework 2.0 接口。</span><span class="sxs-lookup"><span data-stu-id="0f900-108">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0f900-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="0f900-109">In This Section</span></span>  
 [<span data-ttu-id="0f900-110">弃用的 CLR 承载接口和组件类</span><span class="sxs-lookup"><span data-stu-id="0f900-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="0f900-111">描述.NET framework 1.0 和 1.1 版中引入的托管接口。</span><span class="sxs-lookup"><span data-stu-id="0f900-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="0f900-112">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="0f900-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="0f900-113">描述.NET Framework 2.0 版中引入的托管接口。</span><span class="sxs-lookup"><span data-stu-id="0f900-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="0f900-114">CLR 承载接口添加在.NET Framework 4 和 4.5</span><span class="sxs-lookup"><span data-stu-id="0f900-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="0f900-115">描述中引入的托管接口[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0f900-115">Describes the hosting interfaces introduced in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0f900-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="0f900-116">Related Sections</span></span>  
 [<span data-ttu-id="0f900-117">承载组件类</span><span class="sxs-lookup"><span data-stu-id="0f900-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="0f900-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="0f900-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="0f900-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="0f900-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="0f900-120">承载结构</span><span class="sxs-lookup"><span data-stu-id="0f900-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="0f900-121">承载</span><span class="sxs-lookup"><span data-stu-id="0f900-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 [<span data-ttu-id="0f900-122">运行时主机</span><span class="sxs-lookup"><span data-stu-id="0f900-122">Runtime Hosts</span></span>](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)
