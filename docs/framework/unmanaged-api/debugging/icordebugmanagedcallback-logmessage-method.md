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
ms.openlocfilehash: 4306c4ae44b0ae1ade2bf374981492fa1a4df76f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788371"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="36769-102">ICorDebugManagedCallback::LogMessage 方法</span><span class="sxs-lookup"><span data-stu-id="36769-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="36769-103">通知调试器公共语言运行时（CLR）托管线程在 <xref:System.Diagnostics.EventLog> 类中调用了方法来记录事件。</span><span class="sxs-lookup"><span data-stu-id="36769-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36769-104">语法</span><span class="sxs-lookup"><span data-stu-id="36769-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36769-105">参数</span><span class="sxs-lookup"><span data-stu-id="36769-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="36769-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含记录事件的托管线程的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="36769-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="36769-107">中指向 ICorDebugThread 对象的指针，该对象表示托管线程。</span><span class="sxs-lookup"><span data-stu-id="36769-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="36769-108">中[LoggingLevelEnum](logginglevelenum-enumeration.md)枚举的一个值，该值指示写入事件日志的描述性消息的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="36769-108">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="36769-109">中指向跟踪开关名称的指针。</span><span class="sxs-lookup"><span data-stu-id="36769-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="36769-110">中指向写入事件日志的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="36769-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36769-111">需求</span><span class="sxs-lookup"><span data-stu-id="36769-111">Requirements</span></span>  
 <span data-ttu-id="36769-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36769-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36769-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="36769-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="36769-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36769-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36769-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36769-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36769-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36769-116">See also</span></span>

- [<span data-ttu-id="36769-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="36769-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
