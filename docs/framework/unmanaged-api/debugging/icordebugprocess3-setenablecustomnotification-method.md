---
title: ICorDebugProcess3::SetEnableCustomNotification 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a84061cff7cc5dbdeba1e0e66396e04a8f345cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423151"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="5339c-102">ICorDebugProcess3::SetEnableCustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="5339c-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="5339c-103">启用和禁用的指定类型的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="5339c-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5339c-104">语法</span><span class="sxs-lookup"><span data-stu-id="5339c-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5339c-105">参数</span><span class="sxs-lookup"><span data-stu-id="5339c-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="5339c-106">[in]指定自定义调试器通知的类型。</span><span class="sxs-lookup"><span data-stu-id="5339c-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="5339c-107">[in]`true`启用自定义调试器通知;`false`禁用通知。</span><span class="sxs-lookup"><span data-stu-id="5339c-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="5339c-108">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5339c-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5339c-109">备注</span><span class="sxs-lookup"><span data-stu-id="5339c-109">Remarks</span></span>  
 <span data-ttu-id="5339c-110">当`fEnable`设置为`true`，调用<xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>方法触发器[icordebugmanagedcallback3:: Customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="5339c-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="5339c-111">默认情况下; 禁用通知因此，调试器必须指定它就会了解有关并想要处理的任何通知类型。</span><span class="sxs-lookup"><span data-stu-id="5339c-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="5339c-112">因为[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)类的作用范围由应用程序域，调试器必须调用`SetEnableCustomNotification`的每个应用程序域中的过程，如果想要在整个进程接收通知。</span><span class="sxs-lookup"><span data-stu-id="5339c-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="5339c-113">从开始[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]，则仅支持的通知是一个跨线程依赖项通知。</span><span class="sxs-lookup"><span data-stu-id="5339c-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5339c-114">要求</span><span class="sxs-lookup"><span data-stu-id="5339c-114">Requirements</span></span>  
 <span data-ttu-id="5339c-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5339c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5339c-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5339c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5339c-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5339c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5339c-118">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5339c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5339c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5339c-119">See Also</span></span>  
 [<span data-ttu-id="5339c-120">ICorDebugProcess3 接口</span><span class="sxs-lookup"><span data-stu-id="5339c-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [<span data-ttu-id="5339c-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="5339c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="5339c-122">调试</span><span class="sxs-lookup"><span data-stu-id="5339c-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
