---
title: "适用于 Windows 应用商店应用的.NET 的 MEF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f427656f9b385214db5b3bd26c4addb1122b35a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="786a3-102">适用于 Windows 应用商店应用的.NET 的 MEF</span><span class="sxs-lookup"><span data-stu-id="786a3-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="786a3-103"><xref:System.Composition?displayProperty=nameWithType>及其子命名空间包含类型，用于开发可扩展和[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用 Managed Extensibility Framework (MEF)。</span><span class="sxs-lookup"><span data-stu-id="786a3-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="786a3-104">这些命名空间属于[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]子集以供[!INCLUDE[win8](../../../includes/win8-md.md)]操作系统。</span><span class="sxs-lookup"><span data-stu-id="786a3-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="786a3-105">这些命名空间不是与.NET Framework 一起分发的核心类库的一部分。</span><span class="sxs-lookup"><span data-stu-id="786a3-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="786a3-106">若要安装这些命名空间，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从**项目**菜单，然后联机搜索 Microsoft.Composition 包。</span><span class="sxs-lookup"><span data-stu-id="786a3-106">To install these namespaces, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
-   <span data-ttu-id="786a3-107"><xref:System.Composition?displayProperty=nameWithType>提供类构成核心 MEF 的[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]应用。</span><span class="sxs-lookup"><span data-stu-id="786a3-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
-   <span data-ttu-id="786a3-108"><xref:System.Composition.Convention?displayProperty=nameWithType>提供支持使用基于约定的配置模型使用 MEF 的类型。</span><span class="sxs-lookup"><span data-stu-id="786a3-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
-   <span data-ttu-id="786a3-109"><xref:System.Composition.Hosting?displayProperty=nameWithType>提供对主机应用程序的开发人员都很有用的 MEF 类型。</span><span class="sxs-lookup"><span data-stu-id="786a3-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
-   <span data-ttu-id="786a3-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType>提供由组合引擎在内部使用的 MEF 类型。</span><span class="sxs-lookup"><span data-stu-id="786a3-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="786a3-111">有关详细信息[!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]和命名空间和它所包含的类型的列表请参阅[.NET for Windows Store 应用概述](http://go.microsoft.com/fwlink/p/?LinkID=238312)Windows 开发人员中心中。</span><span class="sxs-lookup"><span data-stu-id="786a3-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](http://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786a3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="786a3-112">See Also</span></span>  
 [<span data-ttu-id="786a3-113">.NET for Windows Store 应用概述</span><span class="sxs-lookup"><span data-stu-id="786a3-113">.NET for Windows Store apps overview</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=238312)  
 [<span data-ttu-id="786a3-114">适用于 Windows 应用商店应用的 .NET - 支持的 API</span><span class="sxs-lookup"><span data-stu-id="786a3-114">.NET for Windows Store apps – supported APIs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=247912)  
 [<span data-ttu-id="786a3-115">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="786a3-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)
