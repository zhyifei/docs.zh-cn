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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cb314f2afce0cbbf1c5fb185f516a30ad8313af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780507"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="d2c42-102">IDebuggerThreadControl::StartBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="d2c42-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="d2c42-103">通知主机调试服务即将启动阻塞所有线程。</span><span class="sxs-lookup"><span data-stu-id="d2c42-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2c42-104">语法</span><span class="sxs-lookup"><span data-stu-id="d2c42-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2c42-105">参数</span><span class="sxs-lookup"><span data-stu-id="d2c42-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="d2c42-106">[in]保留供将来使用。</span><span class="sxs-lookup"><span data-stu-id="d2c42-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2c42-107">备注</span><span class="sxs-lookup"><span data-stu-id="d2c42-107">Remarks</span></span>  
 <span data-ttu-id="d2c42-108">`StartBlockingForDebugger`无法在运行时线程上调用方法。</span><span class="sxs-lookup"><span data-stu-id="d2c42-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2c42-109">要求</span><span class="sxs-lookup"><span data-stu-id="d2c42-109">Requirements</span></span>  
 <span data-ttu-id="d2c42-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d2c42-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2c42-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d2c42-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d2c42-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d2c42-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2c42-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2c42-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c42-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2c42-114">See also</span></span>

- [<span data-ttu-id="d2c42-115">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="d2c42-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
