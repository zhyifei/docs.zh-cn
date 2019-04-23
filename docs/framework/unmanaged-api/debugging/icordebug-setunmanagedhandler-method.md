---
title: ICorDebug::SetUnmanagedHandler 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c234b3953130f53d7e6b583cd92670149a70689b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168849"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="cc0ee-102">ICorDebug::SetUnmanagedHandler 方法</span><span class="sxs-lookup"><span data-stu-id="cc0ee-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="cc0ee-103">指定非托管事件的事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="cc0ee-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc0ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc0ee-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc0ee-105">参数</span><span class="sxs-lookup"><span data-stu-id="cc0ee-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="cc0ee-106">[in]一个指向[ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)对象，表示非托管事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cc0ee-106">[in] A pointer to an [ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc0ee-107">备注</span><span class="sxs-lookup"><span data-stu-id="cc0ee-107">Remarks</span></span>  
 <span data-ttu-id="cc0ee-108">事件处理程序对象的非托管事件必须在调用后设置[icordebug:: Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)以及对任何调用之前[icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)或[icordebug:: Debugactiveprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span><span class="sxs-lookup"><span data-stu-id="cc0ee-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="cc0ee-109">但是，出于兼容目的，不需要设置非托管事件，直到第一个本机调试事件引发的事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="cc0ee-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="cc0ee-110">具体而言，如果`ICorDebug::CreateProcess`已设置 CREATE_SUSPENDED 标志，无法调度事件，直到恢复主线程的本机调试。</span><span class="sxs-lookup"><span data-stu-id="cc0ee-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc0ee-111">要求</span><span class="sxs-lookup"><span data-stu-id="cc0ee-111">Requirements</span></span>  
 <span data-ttu-id="cc0ee-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc0ee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc0ee-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc0ee-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc0ee-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc0ee-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc0ee-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc0ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0ee-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc0ee-116">See also</span></span>

- [<span data-ttu-id="cc0ee-117">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="cc0ee-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
