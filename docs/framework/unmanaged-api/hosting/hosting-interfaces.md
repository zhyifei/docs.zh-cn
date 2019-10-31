---
title: 承载接口
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
ms.openlocfilehash: 43b401885bb4de69a06496874f11cec6cdf04b22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126977"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="5ef1c-102">承载接口</span><span class="sxs-lookup"><span data-stu-id="5ef1c-102">Hosting Interfaces</span></span>
<span data-ttu-id="5ef1c-103">本节介绍非托管主机可用于将公共语言运行时（CLR）集成到其应用程序中的接口。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="5ef1c-104">.NET Framework 版本2.0 宿主接口取代了 .NET Framework 版本1.0 和1.1 接口。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="5ef1c-105">两组接口之间存在重大差异。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="5ef1c-106">混合它们可能会导致意外的行为，因此不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="5ef1c-107">.NET Framework 版本3.0 和3.5 使用 .NET Framework 版本2.0 承载接口，不会引入任何承载功能。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="5ef1c-108">.NET Framework 4 宿主接口取代了 .NET Framework 2.0 接口。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5ef1c-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="5ef1c-109">In This Section</span></span>  
 [<span data-ttu-id="5ef1c-110">弃用的 CLR 承接接口和组件类</span><span class="sxs-lookup"><span data-stu-id="5ef1c-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="5ef1c-111">介绍 .NET Framework 版本1.0 和1.1 中引入的托管接口。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="5ef1c-112">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="5ef1c-112">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="5ef1c-113">介绍 .NET Framework 版本2.0 中引入的托管接口。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="5ef1c-114">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="5ef1c-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="5ef1c-115">介绍 .NET Framework 4 中引入的托管接口。</span><span class="sxs-lookup"><span data-stu-id="5ef1c-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5ef1c-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="5ef1c-116">Related Sections</span></span>  
 [<span data-ttu-id="5ef1c-117">承载组件类</span><span class="sxs-lookup"><span data-stu-id="5ef1c-117">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="5ef1c-118">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="5ef1c-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="5ef1c-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="5ef1c-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
  
 [<span data-ttu-id="5ef1c-120">承载结构</span><span class="sxs-lookup"><span data-stu-id="5ef1c-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
  
 [<span data-ttu-id="5ef1c-121">承载</span><span class="sxs-lookup"><span data-stu-id="5ef1c-121">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
  
 <span data-ttu-id="5ef1c-122">[运行时主机](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5ef1c-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
