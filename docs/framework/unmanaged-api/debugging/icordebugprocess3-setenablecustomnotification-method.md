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
ms.openlocfilehash: f2f365f3fe1568f2dd3bad677dd77a13946002e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792467"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="d6249-102">ICorDebugProcess3::SetEnableCustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="d6249-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="d6249-103">启用和禁用指定类型的自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="d6249-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6249-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6249-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6249-105">参数</span><span class="sxs-lookup"><span data-stu-id="d6249-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="d6249-106">中指定自定义调试器通知的类型。</span><span class="sxs-lookup"><span data-stu-id="d6249-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="d6249-107">[in] 用于启用自定义调试器通知的 `true`;`false` 禁用通知。</span><span class="sxs-lookup"><span data-stu-id="d6249-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="d6249-108">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="d6249-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6249-109">备注</span><span class="sxs-lookup"><span data-stu-id="d6249-109">Remarks</span></span>  
 <span data-ttu-id="d6249-110">将 `fEnable` 设置为 `true`时，对 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 方法的调用会触发[ICorDebugManagedCallback3：： CustomNotification](icordebugmanagedcallback3-customnotification-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="d6249-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="d6249-111">默认情况下禁用通知;因此，调试器必须指定它知道的任何通知类型并想要处理。</span><span class="sxs-lookup"><span data-stu-id="d6249-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="d6249-112">由于[ICorDebugClass](icordebug-interface.md)类的作用域由应用程序域确定，因此，如果要在整个过程中接收通知，则调试器必须为进程中的每个应用程序域调用 `SetEnableCustomNotification`。</span><span class="sxs-lookup"><span data-stu-id="d6249-112">Because the [ICorDebugClass](icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="d6249-113">从 .NET Framework 4 开始，唯一受支持的通知是跨线程依赖项通知。</span><span class="sxs-lookup"><span data-stu-id="d6249-113">Starting with the .NET Framework 4, the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6249-114">需求</span><span class="sxs-lookup"><span data-stu-id="d6249-114">Requirements</span></span>  
 <span data-ttu-id="d6249-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6249-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6249-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6249-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6249-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6249-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6249-118">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6249-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6249-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6249-119">See also</span></span>

- [<span data-ttu-id="d6249-120">ICorDebugProcess3 接口</span><span class="sxs-lookup"><span data-stu-id="d6249-120">ICorDebugProcess3 Interface</span></span>](icordebugprocess3-interface.md)
- [<span data-ttu-id="d6249-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="d6249-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d6249-122">调试</span><span class="sxs-lookup"><span data-stu-id="d6249-122">Debugging</span></span>](index.md)
