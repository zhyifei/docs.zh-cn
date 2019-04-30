---
title: CorRuntimeHost 组件类
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2143fc13db1757ac2fa8a9c5a43f104a0c519ca0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985824"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="9fe0e-102">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="9fe0e-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="9fe0e-103">提供用于管理应用程序正在执行公共语言运行时的接口。</span><span class="sxs-lookup"><span data-stu-id="9fe0e-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9fe0e-104">Syntax</span></span>  
  
```  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="9fe0e-105">接口</span><span class="sxs-lookup"><span data-stu-id="9fe0e-105">Interfaces</span></span>  
  
|<span data-ttu-id="9fe0e-106">接口</span><span class="sxs-lookup"><span data-stu-id="9fe0e-106">Interface</span></span>|<span data-ttu-id="9fe0e-107">描述</span><span class="sxs-lookup"><span data-stu-id="9fe0e-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="9fe0e-108">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="9fe0e-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="9fe0e-109">提供用于配置公共语言运行时 (CLR) 方法。</span><span class="sxs-lookup"><span data-stu-id="9fe0e-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="9fe0e-110">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="9fe0e-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="9fe0e-111">提供了使宿主能够显式启动和停止公共语言运行时，若要创建和配置应用程序域，若要访问默认域，并要枚举的进程中运行的所有域的方法。</span><span class="sxs-lookup"><span data-stu-id="9fe0e-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="9fe0e-112">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="9fe0e-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="9fe0e-113">提供用于获取有关调试的服务的状态信息的方法。</span><span class="sxs-lookup"><span data-stu-id="9fe0e-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="9fe0e-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="9fe0e-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="9fe0e-115">提供方法用于获取有关垃圾回收系统的信息以及用于控制垃圾回收的某些方面。</span><span class="sxs-lookup"><span data-stu-id="9fe0e-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="9fe0e-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="9fe0e-116">"IValidator"</span></span>|<span data-ttu-id="9fe0e-117">提供了用于验证的可移植可执行映像和详细报告验证错误的方法。</span><span class="sxs-lookup"><span data-stu-id="9fe0e-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fe0e-118">要求</span><span class="sxs-lookup"><span data-stu-id="9fe0e-118">Requirements</span></span>  
 <span data-ttu-id="9fe0e-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe0e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe0e-120">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="9fe0e-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9fe0e-121">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9fe0e-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fe0e-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe0e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe0e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9fe0e-123">See also</span></span>

- [<span data-ttu-id="9fe0e-124">承载组件类</span><span class="sxs-lookup"><span data-stu-id="9fe0e-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
