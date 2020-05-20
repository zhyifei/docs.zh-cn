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
ms.openlocfilehash: 4e72cd8bee2cb4f35155d7b99cfe8d9cf63f463a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616068"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="d7b9f-102">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="d7b9f-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="d7b9f-103">提供了[IActionOnCLREvent：： OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)方法，该方法对已通过调用[ICLROnEventManager：： RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md)方法注册的事件执行回调。</span><span class="sxs-lookup"><span data-stu-id="d7b9f-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7b9f-104">方法</span><span class="sxs-lookup"><span data-stu-id="d7b9f-104">Methods</span></span>  
  
|<span data-ttu-id="d7b9f-105">方法</span><span class="sxs-lookup"><span data-stu-id="d7b9f-105">Method</span></span>|<span data-ttu-id="d7b9f-106">说明</span><span class="sxs-lookup"><span data-stu-id="d7b9f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7b9f-107">OnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="d7b9f-107">OnEvent Method</span></span>](iactiononclrevent-onevent-method.md)|<span data-ttu-id="d7b9f-108">对已注册的事件执行回调。</span><span class="sxs-lookup"><span data-stu-id="d7b9f-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7b9f-109">要求</span><span class="sxs-lookup"><span data-stu-id="d7b9f-109">Requirements</span></span>  
 <span data-ttu-id="d7b9f-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b9f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7b9f-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d7b9f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d7b9f-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d7b9f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7b9f-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7b9f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b9f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7b9f-114">See also</span></span>

- [<span data-ttu-id="d7b9f-115">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="d7b9f-115">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="d7b9f-116">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="d7b9f-116">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="d7b9f-117">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="d7b9f-117">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="d7b9f-118">承载接口</span><span class="sxs-lookup"><span data-stu-id="d7b9f-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
