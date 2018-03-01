---
title: "CorRuntimeHost 组件类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 23bee1a79dfb54a696495fdb61a7ba9ba4b4c143
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="12fb7-102">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="12fb7-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="12fb7-103">提供用于管理正由公共语言运行时执行的应用程序的接口。</span><span class="sxs-lookup"><span data-stu-id="12fb7-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12fb7-104">语法</span><span class="sxs-lookup"><span data-stu-id="12fb7-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="12fb7-105">接口</span><span class="sxs-lookup"><span data-stu-id="12fb7-105">Interfaces</span></span>  
  
|<span data-ttu-id="12fb7-106">接口</span><span class="sxs-lookup"><span data-stu-id="12fb7-106">Interface</span></span>|<span data-ttu-id="12fb7-107">描述</span><span class="sxs-lookup"><span data-stu-id="12fb7-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="12fb7-108">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="12fb7-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="12fb7-109">提供用于配置公共语言运行时 (CLR) 方法。</span><span class="sxs-lookup"><span data-stu-id="12fb7-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="12fb7-110">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="12fb7-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="12fb7-111">提供使主机能够显式启动和停止公共语言运行时，创建和配置应用程序域，以访问默认域，以及枚举进程中运行的所有域的方法。</span><span class="sxs-lookup"><span data-stu-id="12fb7-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="12fb7-112">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="12fb7-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="12fb7-113">提供用于获取有关调试服务的状态信息的方法。</span><span class="sxs-lookup"><span data-stu-id="12fb7-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="12fb7-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="12fb7-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="12fb7-115">提供用于获取有关垃圾回收系统的信息以及控制垃圾回收的某些方面的方法。</span><span class="sxs-lookup"><span data-stu-id="12fb7-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="12fb7-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="12fb7-116">"IValidator"</span></span>|<span data-ttu-id="12fb7-117">提供用于验证和验证错误的详细报告的可移植可执行映像的方法。</span><span class="sxs-lookup"><span data-stu-id="12fb7-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12fb7-118">惠?</span><span class="sxs-lookup"><span data-stu-id="12fb7-118">Requirements</span></span>  
 <span data-ttu-id="12fb7-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12fb7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12fb7-120">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="12fb7-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="12fb7-121">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="12fb7-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12fb7-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12fb7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12fb7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="12fb7-123">See Also</span></span>  
 [<span data-ttu-id="12fb7-124">承载组件类</span><span class="sxs-lookup"><span data-stu-id="12fb7-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
