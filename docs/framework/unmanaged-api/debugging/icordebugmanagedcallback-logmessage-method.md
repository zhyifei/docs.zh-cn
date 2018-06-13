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
ms.openlocfilehash: d4c8494b1ffc80fc49acce01c5de0b3fd18c0f5c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414088"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="d06b5-102">ICorDebugManagedCallback::LogMessage 方法</span><span class="sxs-lookup"><span data-stu-id="d06b5-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="d06b5-103">通知调试器公共语言运行时 (CLR) 托管线程，调用方法<xref:System.Diagnostics.EventLog>记录事件的类。</span><span class="sxs-lookup"><span data-stu-id="d06b5-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d06b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="d06b5-104">Syntax</span></span>  
  
```  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d06b5-105">参数</span><span class="sxs-lookup"><span data-stu-id="d06b5-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d06b5-106">[in]指向一个表示包含托管的线程记录事件的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d06b5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d06b5-107">[in]指向表示托管的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d06b5-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="d06b5-108">[in]值为[LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)枚举，指示已写入到事件日志的描述性消息的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="d06b5-108">[in] A value of the [LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="d06b5-109">[in]指向跟踪开关的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="d06b5-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="d06b5-110">[in]指向事件日志中写入的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="d06b5-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d06b5-111">要求</span><span class="sxs-lookup"><span data-stu-id="d06b5-111">Requirements</span></span>  
 <span data-ttu-id="d06b5-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d06b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d06b5-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d06b5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d06b5-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d06b5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d06b5-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d06b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d06b5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d06b5-116">See Also</span></span>  
 [<span data-ttu-id="d06b5-117">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="d06b5-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
