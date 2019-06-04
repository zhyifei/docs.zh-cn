---
title: 承载接口
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46ff6032f2cdbd4a5f294198fe3bf71862c67528
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490257"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="c56f1-102">承载接口</span><span class="sxs-lookup"><span data-stu-id="c56f1-102">Hosting Interfaces</span></span>
<span data-ttu-id="c56f1-103">本部分中描述的接口以及非托管主机可用于将公共语言运行时 (CLR) 集成到其应用程序。</span><span class="sxs-lookup"><span data-stu-id="c56f1-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="c56f1-104">.NET Framework 2.0 版承载接口取代了.NET Framework 版本 1.0 和 1.1 接口。</span><span class="sxs-lookup"><span data-stu-id="c56f1-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="c56f1-105">有两个集的接口之间的重大差别。</span><span class="sxs-lookup"><span data-stu-id="c56f1-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="c56f1-106">混合使用这些接口可能会导致意外的行为，不建议使用。</span><span class="sxs-lookup"><span data-stu-id="c56f1-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="c56f1-107">.NET Framework 版本 3.0 和 3.5 使用.NET Framework 2.0 版托管接口，并且并未引入任何托管功能。</span><span class="sxs-lookup"><span data-stu-id="c56f1-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="c56f1-108">.NET Framework 4 承载接口取代了.NET Framework 2.0 接口。</span><span class="sxs-lookup"><span data-stu-id="c56f1-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c56f1-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="c56f1-109">In This Section</span></span>  
 [<span data-ttu-id="c56f1-110">弃用的 CLR 承接接口和组件类</span><span class="sxs-lookup"><span data-stu-id="c56f1-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="c56f1-111">描述.NET framework 1.0 和 1.1 版中引入的托管接口。</span><span class="sxs-lookup"><span data-stu-id="c56f1-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="c56f1-112">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="c56f1-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="c56f1-113">描述.NET Framework 2.0 版中引入的托管接口。</span><span class="sxs-lookup"><span data-stu-id="c56f1-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="c56f1-114">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="c56f1-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="c56f1-115">描述.NET Framework 4 中引入的托管接口。</span><span class="sxs-lookup"><span data-stu-id="c56f1-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c56f1-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="c56f1-116">Related Sections</span></span>  
 [<span data-ttu-id="c56f1-117">承载组件类</span><span class="sxs-lookup"><span data-stu-id="c56f1-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="c56f1-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="c56f1-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="c56f1-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="c56f1-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="c56f1-120">承载结构</span><span class="sxs-lookup"><span data-stu-id="c56f1-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="c56f1-121">承载</span><span class="sxs-lookup"><span data-stu-id="c56f1-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="c56f1-122">[运行时主机](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c56f1-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
