---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0529dee17469018e872951740a5899ef8664300a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420997"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="33e99-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification 方法</span><span class="sxs-lookup"><span data-stu-id="33e99-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>
<span data-ttu-id="33e99-103">获取当前[icordebugmanagedcallback3:: Customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)当前线程上的对象。</span><span class="sxs-lookup"><span data-stu-id="33e99-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e99-104">语法</span><span class="sxs-lookup"><span data-stu-id="33e99-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentCustomDebuggerNotification(  
    [out] ICorDebugValue **ppNotificationObject  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33e99-105">参数</span><span class="sxs-lookup"><span data-stu-id="33e99-105">Parameters</span></span>  
 `ppNOtificationObject`  
 <span data-ttu-id="33e99-106">[out]指向当前`ICorDebugManagedCallback3::CustomNotification`当前线程上的对象。</span><span class="sxs-lookup"><span data-stu-id="33e99-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33e99-107">备注</span><span class="sxs-lookup"><span data-stu-id="33e99-107">Remarks</span></span>  
 <span data-ttu-id="33e99-108">值`ppNotificationObject`如果在不调用该方法为 null`ICorDebugManagedCallback3::CustomNotification`回调，或如果没有任何当前的通知对象存在。</span><span class="sxs-lookup"><span data-stu-id="33e99-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33e99-109">要求</span><span class="sxs-lookup"><span data-stu-id="33e99-109">Requirements</span></span>  
 <span data-ttu-id="33e99-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33e99-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33e99-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33e99-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33e99-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33e99-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33e99-113">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33e99-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e99-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="33e99-114">See Also</span></span>  
 [<span data-ttu-id="33e99-115">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="33e99-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="33e99-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="33e99-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="33e99-117">调试</span><span class="sxs-lookup"><span data-stu-id="33e99-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
