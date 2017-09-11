---
title: "缓解：minFreeMemoryPercentageToActiveService 配置设置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f7f228890476d45517a21bc09806538139c5e389
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a><span data-ttu-id="2c3ee-102">缓解：minFreeMemoryPercentageToActiveService 配置设置</span><span class="sxs-lookup"><span data-stu-id="2c3ee-102">Mitigation: minFreeMemoryPercentageToActiveService Configuration Setting</span></span>
<span data-ttu-id="2c3ee-103">在 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 中，如果 Web 服务器上的可用内存小于 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 配置设置指定的百分比，则会导致异常抛出。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-103">In the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], an exception is thrown if the available memory on the web server is less than the percentage specified by the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) configuration setting.</span></span> <span data-ttu-id="2c3ee-104">在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，已忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-104">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], this setting was ignored.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="2c3ee-105">影响</span><span class="sxs-lookup"><span data-stu-id="2c3ee-105">Impact</span></span>  
 <span data-ttu-id="2c3ee-106">在大多数情况下，遵循 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 设置的影响令人满意：它可防止在具有受约束内存的系统上启动 Windows Communication Foundation (WCF) 服务时可能发生的 <xref:System.OutOfMemoryException> 异常，从而提高系统稳定性。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-106">In most cases, the impact of observing the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting is desirable: It improves system stability by preventing the <xref:System.OutOfMemoryException> exceptions that can occur when a Windows Communication Foundation (WCF) service is started on a system that has constrained memory.</span></span>  
  
 <span data-ttu-id="2c3ee-107">但是在某些情况下，以前成功启动的服务可能会无法启动。</span><span class="sxs-lookup"><span data-stu-id="2c3ee-107">However, in some cases, a service that previously started successfully may be unable to start.</span></span> <span data-ttu-id="2c3ee-108">在这种情况下，会显示详细错误消息：</span><span class="sxs-lookup"><span data-stu-id="2c3ee-108">In that case, a detailed error message appears:</span></span>  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a><span data-ttu-id="2c3ee-109">缓解操作</span><span class="sxs-lookup"><span data-stu-id="2c3ee-109">Mitigation</span></span>  
 <span data-ttu-id="2c3ee-110">若要还原为忽略 [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 设置的旧行为，请按如下所示修改 web.config 文件：</span><span class="sxs-lookup"><span data-stu-id="2c3ee-110">To revert to the previous behavior where the [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) setting was ignored, modify the web.config file as follows:</span></span>  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c3ee-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c3ee-111">See Also</span></span>  
 [<span data-ttu-id="2c3ee-112">运行时更改</span><span class="sxs-lookup"><span data-stu-id="2c3ee-112">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

