---
title: "弃用的 CLR 承载接口和组件类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a4410814669ed329e477fbad13dac60103b1ac0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="d898d-102">弃用的 CLR 承载接口和组件类</span><span class="sxs-lookup"><span data-stu-id="d898d-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>
<span data-ttu-id="d898d-103">本部分描述的接口以及非托管主机可以使用公共语言运行时 (CLR) 集成的.NET Framework 版本 1.0 和 1.1 到其应用程序。</span><span class="sxs-lookup"><span data-stu-id="d898d-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="d898d-104">这些接口提供的主机配置和运行时加载到进程的方法。</span><span class="sxs-lookup"><span data-stu-id="d898d-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d898d-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="d898d-105">In This Section</span></span>  
 <span data-ttu-id="d898d-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="d898d-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="d898d-107">提供了主机配置的方法<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="d898d-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="d898d-108">ICeeFileGen 类</span><span class="sxs-lookup"><span data-stu-id="d898d-108">ICeeFileGen Class</span></span>](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)  
 <span data-ttu-id="d898d-109">（已弃用）提供用于创建本机可移植可执行 (PE) 文件的功能。</span><span class="sxs-lookup"><span data-stu-id="d898d-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="d898d-110">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="d898d-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 <span data-ttu-id="d898d-111">提供配置 CLR 设置主机的方法。</span><span class="sxs-lookup"><span data-stu-id="d898d-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d898d-112">相关章节</span><span class="sxs-lookup"><span data-stu-id="d898d-112">Related Sections</span></span>  
 [<span data-ttu-id="d898d-113">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="d898d-113">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="d898d-114">包含描述.NET Framework 2.0 版和更高版本附带的托管接口的主题。</span><span class="sxs-lookup"><span data-stu-id="d898d-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
