---
title: ICorDebug::SetManagedHandler 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.SetManagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetManagedHandler
helpviewer_keywords:
- ICorDebug::SetManagedHandler method [.NET Framework debugging]
- SetManagedHandler method [.NET Framework debugging]
ms.assetid: d079131b-685b-4869-95be-826b88d28bd2
topic_type:
- apiref
ms.openlocfilehash: a197d260c55d24f906da7d7f2768bb7ba1ad751f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895346"
---
# <a name="icordebugsetmanagedhandler-method"></a><span data-ttu-id="05314-102">ICorDebug::SetManagedHandler 方法</span><span class="sxs-lookup"><span data-stu-id="05314-102">ICorDebug::SetManagedHandler Method</span></span>
<span data-ttu-id="05314-103">指定托管事件的事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="05314-103">Specifies the event handler object for managed events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05314-104">语法</span><span class="sxs-lookup"><span data-stu-id="05314-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManagedHandler (  
    [in] ICorDebugManagedCallback     *pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05314-105">参数</span><span class="sxs-lookup"><span data-stu-id="05314-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="05314-106">中指向[ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)对象的指针，该对象为事件处理程序对象。</span><span class="sxs-lookup"><span data-stu-id="05314-106">[in] A pointer to an [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) object, which is the event handler object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05314-107">备注</span><span class="sxs-lookup"><span data-stu-id="05314-107">Remarks</span></span>  
 <span data-ttu-id="05314-108">`SetManagedHandler`必须在创建时调用。</span><span class="sxs-lookup"><span data-stu-id="05314-108">`SetManagedHandler` must be called at creation time.</span></span>  
  
 <span data-ttu-id="05314-109">如果`ICorDebugManagedCallback`实现未包含足够的接口来处理要调试的应用程序的调试事件， `SetManagedHandler`则将返回 E_NOINTERFACE 的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="05314-109">If the `ICorDebugManagedCallback` implementation does not contain sufficient interfaces to handle debugging events for the application that is being debugged, `SetManagedHandler` returns an HRESULT of E_NOINTERFACE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05314-110">要求</span><span class="sxs-lookup"><span data-stu-id="05314-110">Requirements</span></span>  
 <span data-ttu-id="05314-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05314-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05314-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05314-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05314-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05314-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05314-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05314-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05314-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05314-115">See also</span></span>

- [<span data-ttu-id="05314-116">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="05314-116">ICorDebug Interface</span></span>](icordebug-interface.md)
