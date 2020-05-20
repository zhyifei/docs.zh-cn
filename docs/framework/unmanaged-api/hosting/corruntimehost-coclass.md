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
ms.openlocfilehash: fe378307ce2bda6e1a267e46433ead70a0e2299e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616511"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="47d5c-102">CorRuntimeHost 组件类</span><span class="sxs-lookup"><span data-stu-id="47d5c-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="47d5c-103">提供用于管理由公共语言运行时执行的应用程序的接口。</span><span class="sxs-lookup"><span data-stu-id="47d5c-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d5c-104">语法</span><span class="sxs-lookup"><span data-stu-id="47d5c-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="47d5c-105">接口</span><span class="sxs-lookup"><span data-stu-id="47d5c-105">Interfaces</span></span>  
  
|<span data-ttu-id="47d5c-106">接口</span><span class="sxs-lookup"><span data-stu-id="47d5c-106">Interface</span></span>|<span data-ttu-id="47d5c-107">说明</span><span class="sxs-lookup"><span data-stu-id="47d5c-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="47d5c-108">ICorConfiguration 接口</span><span class="sxs-lookup"><span data-stu-id="47d5c-108">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)|<span data-ttu-id="47d5c-109">提供用于配置公共语言运行时（CLR）的方法。</span><span class="sxs-lookup"><span data-stu-id="47d5c-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="47d5c-110">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="47d5c-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)|<span data-ttu-id="47d5c-111">提供使宿主可以显式启动和停止公共语言运行时、创建和配置应用程序域、访问默认域和枚举进程中运行的所有域的方法。</span><span class="sxs-lookup"><span data-stu-id="47d5c-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="47d5c-112">IDebuggerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="47d5c-112">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)|<span data-ttu-id="47d5c-113">提供用于获取有关调试服务状态的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="47d5c-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="47d5c-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="47d5c-114">IGCHost Interface</span></span>](igchost-interface.md)|<span data-ttu-id="47d5c-115">提供一些方法，用于获取有关垃圾回收系统的信息并控制垃圾回收的某些方面。</span><span class="sxs-lookup"><span data-stu-id="47d5c-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="47d5c-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="47d5c-116">"IValidator"</span></span>|<span data-ttu-id="47d5c-117">提供可移植可执行映像的验证和验证错误的详细报告的方法。</span><span class="sxs-lookup"><span data-stu-id="47d5c-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47d5c-118">要求</span><span class="sxs-lookup"><span data-stu-id="47d5c-118">Requirements</span></span>  
 <span data-ttu-id="47d5c-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47d5c-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47d5c-120">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="47d5c-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="47d5c-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="47d5c-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47d5c-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47d5c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d5c-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47d5c-123">See also</span></span>

- [<span data-ttu-id="47d5c-124">承载 Coclass</span><span class="sxs-lookup"><span data-stu-id="47d5c-124">Hosting Coclasses</span></span>](hosting-coclasses.md)
