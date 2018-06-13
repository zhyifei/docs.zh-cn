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
ms.openlocfilehash: 48aa7452373f83465b3e5ec8a09a9a00c902a22c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437929"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="219c7-102">IDebuggerThreadControl::StartBlockingForDebugger 方法</span><span class="sxs-lookup"><span data-stu-id="219c7-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="219c7-103">通知主机调试服务即将开始阻止所有线程。</span><span class="sxs-lookup"><span data-stu-id="219c7-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="219c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="219c7-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="219c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="219c7-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="219c7-106">[in]留待将来使用。</span><span class="sxs-lookup"><span data-stu-id="219c7-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="219c7-107">备注</span><span class="sxs-lookup"><span data-stu-id="219c7-107">Remarks</span></span>  
 <span data-ttu-id="219c7-108">`StartBlockingForDebugger`无法在运行时线程上调用方法。</span><span class="sxs-lookup"><span data-stu-id="219c7-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="219c7-109">要求</span><span class="sxs-lookup"><span data-stu-id="219c7-109">Requirements</span></span>  
 <span data-ttu-id="219c7-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="219c7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="219c7-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="219c7-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="219c7-112">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="219c7-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="219c7-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="219c7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219c7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="219c7-114">See Also</span></span>  
 [<span data-ttu-id="219c7-115">IDebuggerThreadControl 接口</span><span class="sxs-lookup"><span data-stu-id="219c7-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
