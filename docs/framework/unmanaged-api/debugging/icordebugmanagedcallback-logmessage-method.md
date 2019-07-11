---
title: ICorDebugManagedCallback::LogMessage 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14b10b94f66a6b5434befeac1cd9562cb8a0f27f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761555"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="d936a-102">ICorDebugManagedCallback::LogMessage 方法</span><span class="sxs-lookup"><span data-stu-id="d936a-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="d936a-103">通知调试器公共语言运行时 (CLR) 托管线程已调用的一个方法<xref:System.Diagnostics.EventLog>类来记录事件。</span><span class="sxs-lookup"><span data-stu-id="d936a-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d936a-104">语法</span><span class="sxs-lookup"><span data-stu-id="d936a-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d936a-105">参数</span><span class="sxs-lookup"><span data-stu-id="d936a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d936a-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含托管的线程记录事件的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="d936a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d936a-107">[in]指向表示托管的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d936a-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="d936a-108">[in]值为[LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)枚举，指示已写入事件日志的描述性消息的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="d936a-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="d936a-109">[in]一个指向跟踪开关的名称。</span><span class="sxs-lookup"><span data-stu-id="d936a-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="d936a-110">[in]指向已写入事件日志的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="d936a-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d936a-111">要求</span><span class="sxs-lookup"><span data-stu-id="d936a-111">Requirements</span></span>  
 <span data-ttu-id="d936a-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d936a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d936a-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d936a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d936a-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d936a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d936a-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d936a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d936a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d936a-116">See also</span></span>

- [<span data-ttu-id="d936a-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d936a-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
