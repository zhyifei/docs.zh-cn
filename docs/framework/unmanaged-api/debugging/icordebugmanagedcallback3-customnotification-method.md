---
title: ICorDebugManagedCallback3::CustomNotification 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 276a45c9f7b66fecdc4df07da94f813fe025fcb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592505"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="ae7db-102">ICorDebugManagedCallback3::CustomNotification 方法</span><span class="sxs-lookup"><span data-stu-id="ae7db-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="ae7db-103">指示已引发自定义调试器通知。</span><span class="sxs-lookup"><span data-stu-id="ae7db-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae7db-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae7db-104">Syntax</span></span>  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae7db-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae7db-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="ae7db-106">[in]指向引发通知的线程的指针。</span><span class="sxs-lookup"><span data-stu-id="ae7db-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="ae7db-107">[in]指向包含引发通知的线程的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="ae7db-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae7db-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ae7db-108">Return Value</span></span>  
 <span data-ttu-id="ae7db-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ae7db-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ae7db-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae7db-110">HRESULT</span></span>|<span data-ttu-id="ae7db-111">描述</span><span class="sxs-lookup"><span data-stu-id="ae7db-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae7db-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae7db-112">S_OK</span></span>|<span data-ttu-id="ae7db-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ae7db-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ae7db-114">Exceptions</span><span class="sxs-lookup"><span data-stu-id="ae7db-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae7db-115">备注</span><span class="sxs-lookup"><span data-stu-id="ae7db-115">Remarks</span></span>  
 <span data-ttu-id="ae7db-116">随后调用[ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)方法检索线程的对象传递给<xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="ae7db-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ae7db-117">线程对象的类型必须之前已启用通过调用[ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ae7db-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="ae7db-118">调试器可以从线程对象的字段读取特定于类型的参数，并可以将响应存储到字段。</span><span class="sxs-lookup"><span data-stu-id="ae7db-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="ae7db-119">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)接口施加的通知或其内容类型上没有策略和通知的语义是严格的调试器、 应用程序和.NET Framework 之间的协定。</span><span class="sxs-lookup"><span data-stu-id="ae7db-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae7db-120">要求</span><span class="sxs-lookup"><span data-stu-id="ae7db-120">Requirements</span></span>  
 <span data-ttu-id="ae7db-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae7db-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae7db-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae7db-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae7db-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae7db-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae7db-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae7db-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7db-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae7db-125">See also</span></span>
- [<span data-ttu-id="ae7db-126">ICorDebugManagedCallback3 接口</span><span class="sxs-lookup"><span data-stu-id="ae7db-126">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="ae7db-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="ae7db-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ae7db-128">调试</span><span class="sxs-lookup"><span data-stu-id="ae7db-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
