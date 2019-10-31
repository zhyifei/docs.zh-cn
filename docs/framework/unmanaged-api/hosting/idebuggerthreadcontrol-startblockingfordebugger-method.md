---
title: IDebuggerThreadControl::StartBlockingForDebugger 方法
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 72f7bee79e74c69acff90861ceada8a91afe2157
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134920"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="da0f0-102">IDebuggerThreadControl::StartBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="da0f0-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="da0f0-103">通知宿主调试服务即将开始阻塞所有线程。</span><span class="sxs-lookup"><span data-stu-id="da0f0-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da0f0-104">语法</span><span class="sxs-lookup"><span data-stu-id="da0f0-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da0f0-105">参数</span><span class="sxs-lookup"><span data-stu-id="da0f0-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="da0f0-106">中保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="da0f0-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da0f0-107">备注</span><span class="sxs-lookup"><span data-stu-id="da0f0-107">Remarks</span></span>  
 <span data-ttu-id="da0f0-108">可以在运行时线程上调用 `StartBlockingForDebugger` 方法。</span><span class="sxs-lookup"><span data-stu-id="da0f0-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da0f0-109">要求</span><span class="sxs-lookup"><span data-stu-id="da0f0-109">Requirements</span></span>  
 <span data-ttu-id="da0f0-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="da0f0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da0f0-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="da0f0-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da0f0-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="da0f0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da0f0-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da0f0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da0f0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="da0f0-114">See also</span></span>

- [<span data-ttu-id="da0f0-115">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="da0f0-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
