---
title: "IActionOnCLREvent 接口"
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
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4b51784f07a90faa9eeb29c18a784d4fbc2c4654
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="63672-102">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="63672-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="63672-103">提供[iactiononclrevent:: Onevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)方法，用于通过对的调用已注册的事件执行回调[iclroneventmanager:: Registeractiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="63672-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63672-104">方法</span><span class="sxs-lookup"><span data-stu-id="63672-104">Methods</span></span>  
  
|<span data-ttu-id="63672-105">方法</span><span class="sxs-lookup"><span data-stu-id="63672-105">Method</span></span>|<span data-ttu-id="63672-106">描述</span><span class="sxs-lookup"><span data-stu-id="63672-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63672-107">OnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="63672-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="63672-108">执行已注册的事件回调。</span><span class="sxs-lookup"><span data-stu-id="63672-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63672-109">惠?</span><span class="sxs-lookup"><span data-stu-id="63672-109">Requirements</span></span>  
 <span data-ttu-id="63672-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63672-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63672-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63672-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63672-112">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="63672-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63672-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63672-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63672-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="63672-114">See Also</span></span>  
 [<span data-ttu-id="63672-115">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="63672-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="63672-116">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="63672-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="63672-117">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="63672-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="63672-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="63672-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
