---
title: "ICorDebugManagedCallback::CreateThread 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.CreateThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8acb12d216949fc4e0636b5a2c28657ef5c79bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="6c06a-102">ICorDebugManagedCallback::CreateThread 方法</span><span class="sxs-lookup"><span data-stu-id="6c06a-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="6c06a-103">通知调试器线程已开始执行托管的代码。</span><span class="sxs-lookup"><span data-stu-id="6c06a-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c06a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c06a-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c06a-105">参数</span><span class="sxs-lookup"><span data-stu-id="6c06a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6c06a-106">[in]指向一个表示包含线程的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6c06a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="6c06a-107">[in]指向一个 ICorDebugThread 对象，表示线程的指针。</span><span class="sxs-lookup"><span data-stu-id="6c06a-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c06a-108">备注</span><span class="sxs-lookup"><span data-stu-id="6c06a-108">Remarks</span></span>  
 <span data-ttu-id="6c06a-109">该线程将放置在要执行的第一个托管的代码指令。</span><span class="sxs-lookup"><span data-stu-id="6c06a-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c06a-110">惠?</span><span class="sxs-lookup"><span data-stu-id="6c06a-110">Requirements</span></span>  
 <span data-ttu-id="6c06a-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6c06a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c06a-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c06a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c06a-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c06a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c06a-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c06a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c06a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c06a-115">See Also</span></span>  
 [<span data-ttu-id="6c06a-116">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6c06a-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
