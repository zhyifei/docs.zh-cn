---
title: ICLROnEventManager 接口
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: 30312e6e09535cee2968b1f9e8ac87b461c5ff40
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703519"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="92012-102">ICLROnEventManager 接口</span><span class="sxs-lookup"><span data-stu-id="92012-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="92012-103">提供允许主机注册和注销公共语言运行时（CLR）事件的回调的方法。</span><span class="sxs-lookup"><span data-stu-id="92012-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="92012-104">方法</span><span class="sxs-lookup"><span data-stu-id="92012-104">Methods</span></span>  
  
|<span data-ttu-id="92012-105">方法</span><span class="sxs-lookup"><span data-stu-id="92012-105">Method</span></span>|<span data-ttu-id="92012-106">说明</span><span class="sxs-lookup"><span data-stu-id="92012-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="92012-107">RegisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="92012-107">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="92012-108">为指定事件注册回调指针。</span><span class="sxs-lookup"><span data-stu-id="92012-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="92012-109">UnregisterActionOnEvent 方法</span><span class="sxs-lookup"><span data-stu-id="92012-109">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="92012-110">为指定的事件注销先前注册的回调指针。</span><span class="sxs-lookup"><span data-stu-id="92012-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92012-111">备注</span><span class="sxs-lookup"><span data-stu-id="92012-111">Remarks</span></span>  
 <span data-ttu-id="92012-112">若要注册和注销事件回调，主机可 `ICLROnEventManager` 通过调用[ICLRControl：： GetCLRManager](iclrcontrol-getclrmanager-method.md)方法获取对的引用。</span><span class="sxs-lookup"><span data-stu-id="92012-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="92012-113">[EClrEvent](eclrevent-enumeration.md)描述的事件可以从不同的线程激发一次，以指示卸载或禁用 CLR。</span><span class="sxs-lookup"><span data-stu-id="92012-113">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92012-114">要求</span><span class="sxs-lookup"><span data-stu-id="92012-114">Requirements</span></span>  
 <span data-ttu-id="92012-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92012-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92012-116">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="92012-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="92012-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="92012-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92012-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92012-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92012-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92012-119">See also</span></span>

- [<span data-ttu-id="92012-120">EClrEvent 枚举</span><span class="sxs-lookup"><span data-stu-id="92012-120">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="92012-121">IActionOnCLREvent 接口</span><span class="sxs-lookup"><span data-stu-id="92012-121">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="92012-122">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="92012-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="92012-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="92012-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
