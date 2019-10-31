---
title: IActionOnCLREvent 接口
ms.date: 03/30/2017
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
ms.openlocfilehash: 9277fe2c241ce4f502339de826dccd08a2ce8055
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126961"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="81bae-102">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="81bae-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="81bae-103">提供了[IActionOnCLREvent：： OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)方法，该方法对已通过调用[ICLROnEventManager：： RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)方法注册的事件执行回调。</span><span class="sxs-lookup"><span data-stu-id="81bae-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81bae-104">方法</span><span class="sxs-lookup"><span data-stu-id="81bae-104">Methods</span></span>  
  
|<span data-ttu-id="81bae-105">方法</span><span class="sxs-lookup"><span data-stu-id="81bae-105">Method</span></span>|<span data-ttu-id="81bae-106">描述</span><span class="sxs-lookup"><span data-stu-id="81bae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="81bae-107">OnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="81bae-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="81bae-108">对已注册的事件执行回调。</span><span class="sxs-lookup"><span data-stu-id="81bae-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81bae-109">要求</span><span class="sxs-lookup"><span data-stu-id="81bae-109">Requirements</span></span>  
 <span data-ttu-id="81bae-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81bae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81bae-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="81bae-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81bae-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="81bae-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81bae-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81bae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bae-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="81bae-114">See also</span></span>

- [<span data-ttu-id="81bae-115">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="81bae-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="81bae-116">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="81bae-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="81bae-117">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="81bae-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="81bae-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="81bae-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
