---
title: 弃用的 CLR 承载接口和 Coclass
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
ms.openlocfilehash: 814f148b39045ad5454a23dfce8e7f9441f69041
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616406"
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="ee8c0-102">弃用的 CLR 承载接口和 Coclass</span><span class="sxs-lookup"><span data-stu-id="ee8c0-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>
<span data-ttu-id="ee8c0-103">本部分介绍了非托管主机可用于将 .NET Framework 版本1.0 和1.1 中的公共语言运行时（CLR）集成到其应用程序中的接口。</span><span class="sxs-lookup"><span data-stu-id="ee8c0-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="ee8c0-104">这些接口为主机提供用于配置运行时并将其加载到进程中的方法。</span><span class="sxs-lookup"><span data-stu-id="ee8c0-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee8c0-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="ee8c0-105">In This Section</span></span>  
 <span data-ttu-id="ee8c0-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="ee8c0-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="ee8c0-107">为宿主提供用于配置的方法 <xref:System.AppDomain> 。</span><span class="sxs-lookup"><span data-stu-id="ee8c0-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="ee8c0-108">ICeeFileGen 类</span><span class="sxs-lookup"><span data-stu-id="ee8c0-108">ICeeFileGen Class</span></span>](iceefilegen-class.md)  
 <span data-ttu-id="ee8c0-109">弃用提供用于创建本机可移植可执行（PE）文件的功能。</span><span class="sxs-lookup"><span data-stu-id="ee8c0-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="ee8c0-110">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="ee8c0-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)  
 <span data-ttu-id="ee8c0-111">为宿主提供用于配置 CLR 设置的方法。</span><span class="sxs-lookup"><span data-stu-id="ee8c0-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ee8c0-112">相关章节</span><span class="sxs-lookup"><span data-stu-id="ee8c0-112">Related Sections</span></span>  
 [<span data-ttu-id="ee8c0-113">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="ee8c0-113">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="ee8c0-114">包含描述随 .NET Framework 版本2.0 及更高版本一起提供的宿主接口的主题。</span><span class="sxs-lookup"><span data-stu-id="ee8c0-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
