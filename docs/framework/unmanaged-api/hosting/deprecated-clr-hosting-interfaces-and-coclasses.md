---
title: 弃用的 CLR 承载接口和 Coclass
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f6c20a69894c95086dbd813601ac8811ab4f337
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985694"
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="75156-102">弃用的 CLR 承载接口和 Coclass</span><span class="sxs-lookup"><span data-stu-id="75156-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>
<span data-ttu-id="75156-103">本部分中描述的接口以及非托管主机可以使用公共语言运行时 (CLR) 集成在.NET framework 1.0 和 1.1 版中在其应用程序。</span><span class="sxs-lookup"><span data-stu-id="75156-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="75156-104">这些接口提供的主机，若要配置和运行时加载到进程的方法。</span><span class="sxs-lookup"><span data-stu-id="75156-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="75156-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="75156-105">In This Section</span></span>  
 <span data-ttu-id="75156-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="75156-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="75156-107">提供主机后，若要配置的方法<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="75156-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="75156-108">ICeeFileGen 类</span><span class="sxs-lookup"><span data-stu-id="75156-108">ICeeFileGen Class</span></span>](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)  
 <span data-ttu-id="75156-109">（已弃用）提供用于创建本机可移植可执行 (PE) 文件的功能。</span><span class="sxs-lookup"><span data-stu-id="75156-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="75156-110">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="75156-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 <span data-ttu-id="75156-111">提供主机后，若要配置 CLR 设置的方法。</span><span class="sxs-lookup"><span data-stu-id="75156-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="75156-112">相关章节</span><span class="sxs-lookup"><span data-stu-id="75156-112">Related Sections</span></span>  
 [<span data-ttu-id="75156-113">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="75156-113">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="75156-114">包含描述.NET Framework 2.0 版和更高版本提供的托管接口的主题。</span><span class="sxs-lookup"><span data-stu-id="75156-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
