---
title: ICorDebugManagedCallback::CreateThread 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48e92c73347957d8acc5c209f6f5473e9e18524
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223246"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="264f8-102">ICorDebugManagedCallback::CreateThread 方法</span><span class="sxs-lookup"><span data-stu-id="264f8-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="264f8-103">通知调试器线程已开始执行托管的代码。</span><span class="sxs-lookup"><span data-stu-id="264f8-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="264f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="264f8-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="264f8-105">参数</span><span class="sxs-lookup"><span data-stu-id="264f8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="264f8-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含在线程的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="264f8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="264f8-107">[in]指向一个 ICorDebugThread 对象，表示在线程的指针。</span><span class="sxs-lookup"><span data-stu-id="264f8-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="264f8-108">备注</span><span class="sxs-lookup"><span data-stu-id="264f8-108">Remarks</span></span>  
 <span data-ttu-id="264f8-109">该线程将定位在要执行的第一个托管的代码指令。</span><span class="sxs-lookup"><span data-stu-id="264f8-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="264f8-110">要求</span><span class="sxs-lookup"><span data-stu-id="264f8-110">Requirements</span></span>  
 <span data-ttu-id="264f8-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="264f8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="264f8-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="264f8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="264f8-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="264f8-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="264f8-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="264f8-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="264f8-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="264f8-115">See also</span></span>

- [<span data-ttu-id="264f8-116">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="264f8-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
