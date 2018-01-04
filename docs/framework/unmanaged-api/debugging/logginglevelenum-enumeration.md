---
title: "LoggingLevelEnum 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoggingLevelEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: LoggingLevelEnum
helpviewer_keywords: LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a1f8bb53d53593073df7ef7aa095eeb3b9f8c632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="52172-102">LoggingLevelEnum 枚举</span><span class="sxs-lookup"><span data-stu-id="52172-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="52172-103">指示在托管线程记录事件时写入事件日志的描述性消息的严重级别。</span><span class="sxs-lookup"><span data-stu-id="52172-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52172-104">语法</span><span class="sxs-lookup"><span data-stu-id="52172-104">Syntax</span></span>  
  
```  
typedef enum LoggingLevelEnum {  
    LTraceLevel0 = 0,  
    LTraceLevel1,  
    LTraceLevel2,  
    LTraceLevel3,  
    LTraceLevel4,  
    LStatusLevel0 = 20,  
    LStatusLevel1,  
    LStatusLevel2,  
    LStatusLevel3,  
    LStatusLevel4,  
    LWarningLevel = 40,  
    LErrorLevel = 50,  
    LPanicLevel = 100  
} LoggingLevelEnum;  
```  
  
## <a name="members"></a><span data-ttu-id="52172-105">成员</span><span class="sxs-lookup"><span data-stu-id="52172-105">Members</span></span>  
  
|<span data-ttu-id="52172-106">成员</span><span class="sxs-lookup"><span data-stu-id="52172-106">Member</span></span>|<span data-ttu-id="52172-107">描述</span><span class="sxs-lookup"><span data-stu-id="52172-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="52172-108">消息是跟踪级别 0。</span><span class="sxs-lookup"><span data-stu-id="52172-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="52172-109">消息是一个跟踪第 1 级。</span><span class="sxs-lookup"><span data-stu-id="52172-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="52172-110">消息是 2 的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="52172-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="52172-111">消息为 3 的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="52172-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="52172-112">消息是 4 的跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="52172-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="52172-113">消息是状态级别 0。</span><span class="sxs-lookup"><span data-stu-id="52172-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="52172-114">消息是一个状态第 1 级。</span><span class="sxs-lookup"><span data-stu-id="52172-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="52172-115">消息是状态级别 2。</span><span class="sxs-lookup"><span data-stu-id="52172-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="52172-116">消息是状态级别 3。</span><span class="sxs-lookup"><span data-stu-id="52172-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="52172-117">消息是状态级别 4。</span><span class="sxs-lookup"><span data-stu-id="52172-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="52172-118">消息是警告级别。</span><span class="sxs-lookup"><span data-stu-id="52172-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="52172-119">消息是错误级别。</span><span class="sxs-lookup"><span data-stu-id="52172-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="52172-120">消息是 panic 级别。</span><span class="sxs-lookup"><span data-stu-id="52172-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52172-121">备注</span><span class="sxs-lookup"><span data-stu-id="52172-121">Remarks</span></span>  
 <span data-ttu-id="52172-122">公共语言运行时 (CLR) 调用[icordebugmanagedcallback:: Logmessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)方法，以通知调试器托管的线程记录事件。</span><span class="sxs-lookup"><span data-stu-id="52172-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="52172-123">CLR 中传递的值`LoggingLevelEnum`枚举，以指示托管的线程已写入到事件日志消息的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="52172-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52172-124">惠?</span><span class="sxs-lookup"><span data-stu-id="52172-124">Requirements</span></span>  
 <span data-ttu-id="52172-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="52172-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52172-126">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52172-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52172-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52172-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52172-128">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52172-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52172-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="52172-129">See Also</span></span>  
 <xref:System.Diagnostics.EventLog>  
 [<span data-ttu-id="52172-130">调试枚举</span><span class="sxs-lookup"><span data-stu-id="52172-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
