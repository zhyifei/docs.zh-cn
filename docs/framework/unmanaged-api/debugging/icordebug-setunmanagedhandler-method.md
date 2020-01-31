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
ms.openlocfilehash: cafa1c99a8988c199d866796911d1983aabb7208
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785068"
---
# <a name="icordebugsetunmanagedhandler-method"></a><span data-ttu-id="e9a91-102">ICorDebug::SetUnmanagedHandler 方法</span><span class="sxs-lookup"><span data-stu-id="e9a91-102">ICorDebug::SetUnmanagedHandler Method</span></span>
<span data-ttu-id="e9a91-103">指定非托管事件的事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="e9a91-103">Specifies the event handler object for unmanaged events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9a91-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9a91-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9a91-105">参数</span><span class="sxs-lookup"><span data-stu-id="e9a91-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="e9a91-106">中指向[ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)对象的指针，该对象表示非托管事件的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e9a91-106">[in] A pointer to an [ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md) object that represents the event handler for unmanaged events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9a91-107">备注</span><span class="sxs-lookup"><span data-stu-id="e9a91-107">Remarks</span></span>  
 <span data-ttu-id="e9a91-108">非托管事件的事件处理程序对象必须在调用[ICorDebug：： Initialize](icordebug-initialize-method.md)之后以及对[ICorDebug：： CreateProcess](icordebug-createprocess-method.md)或[ICorDebug：:D ebugactiveprocess](icordebug-debugactiveprocess-method.md)的任何调用之前设置。</span><span class="sxs-lookup"><span data-stu-id="e9a91-108">The event handler object for unmanaged events must be set after a call to [ICorDebug::Initialize](icordebug-initialize-method.md) and before any calls to [ICorDebug::CreateProcess](icordebug-createprocess-method.md) or [ICorDebug::DebugActiveProcess](icordebug-debugactiveprocess-method.md).</span></span> <span data-ttu-id="e9a91-109">但出于传统目的，在引发第一个本机调试事件之前，不需要为非托管事件设置事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="e9a91-109">However, for legacy purposes, you are not required to set the event handler object for unmanaged events until the first native debug event is raised.</span></span> <span data-ttu-id="e9a91-110">具体来说，如果 `ICorDebug::CreateProcess` 设置 CREATE_SUSPENDED 标志，则在主线程恢复之前，不能调度本机调试事件。</span><span class="sxs-lookup"><span data-stu-id="e9a91-110">Specifically, if `ICorDebug::CreateProcess` has set the CREATE_SUSPENDED flag, native debug events cannot be dispatched until the main thread is resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9a91-111">需求</span><span class="sxs-lookup"><span data-stu-id="e9a91-111">Requirements</span></span>  
 <span data-ttu-id="e9a91-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a91-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a91-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9a91-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9a91-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9a91-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9a91-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a91-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a91-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9a91-116">See also</span></span>

- [<span data-ttu-id="e9a91-117">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="e9a91-117">ICorDebug Interface</span></span>](icordebug-interface.md)
