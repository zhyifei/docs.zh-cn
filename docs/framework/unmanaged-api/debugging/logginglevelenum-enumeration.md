---
title: LoggingLevelEnum 枚举
ms.date: 03/30/2017
api_name:
- LoggingLevelEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LoggingLevelEnum
helpviewer_keywords:
- LoggingLevelEnum enumeration [.NET Framework debugging]
ms.assetid: 09daac08-005a-46b2-beab-408d0820c5e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fe8e1355382273a681e927897f4a8ff5814b8de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086502"
---
# <a name="logginglevelenum-enumeration"></a><span data-ttu-id="fa7f7-102">LoggingLevelEnum 枚举</span><span class="sxs-lookup"><span data-stu-id="fa7f7-102">LoggingLevelEnum Enumeration</span></span>
<span data-ttu-id="fa7f7-103">指示在托管线程记录事件时写入事件日志的描述性消息的严重级别。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-103">Indicates the severity level of a descriptive message that is written to the event log when a managed thread logs an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa7f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa7f7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="fa7f7-105">成员</span><span class="sxs-lookup"><span data-stu-id="fa7f7-105">Members</span></span>  
  
|<span data-ttu-id="fa7f7-106">成员</span><span class="sxs-lookup"><span data-stu-id="fa7f7-106">Member</span></span>|<span data-ttu-id="fa7f7-107">描述</span><span class="sxs-lookup"><span data-stu-id="fa7f7-107">Description</span></span>|  
|------------|-----------------|  
|`LTraceLevel0`|<span data-ttu-id="fa7f7-108">该消息是跟踪级别 0。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-108">The message is a trace level 0.</span></span>|  
|`LTraceLevel1`|<span data-ttu-id="fa7f7-109">该消息是跟踪级别 1。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-109">The message is a trace level 1.</span></span>|  
|`LTraceLevel2`|<span data-ttu-id="fa7f7-110">该消息是跟踪级别 2。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-110">The message is a trace level 2.</span></span>|  
|`LTraceLevel3`|<span data-ttu-id="fa7f7-111">该消息是跟踪级别 3。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-111">The message is a trace level 3.</span></span>|  
|`LTraceLevel4`|<span data-ttu-id="fa7f7-112">该消息是跟踪级别 4。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-112">The message is a trace level 4.</span></span>|  
|`LStatusLevel0`|<span data-ttu-id="fa7f7-113">该消息为状态级别 0。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-113">The message is a status level 0.</span></span>|  
|`LStatusLevel1`|<span data-ttu-id="fa7f7-114">该消息是状态级别 1。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-114">The message is a status level 1.</span></span>|  
|`LStatusLevel2`|<span data-ttu-id="fa7f7-115">该消息是状态级别 2。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-115">The message is a status level 2.</span></span>|  
|`LStatusLevel3`|<span data-ttu-id="fa7f7-116">该消息是状态级别 3。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-116">The message is a status level 3.</span></span>|  
|`LStatusLevel4`|<span data-ttu-id="fa7f7-117">该消息是状态级别 4。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-117">The message is a status level 4.</span></span>|  
|`LWarningLevel`|<span data-ttu-id="fa7f7-118">该消息是警告级别。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-118">The message is a warning level.</span></span>|  
|`LErrorLevel`|<span data-ttu-id="fa7f7-119">该消息是错误级别。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-119">The message is an error level.</span></span>|  
|`LPanicLevel`|<span data-ttu-id="fa7f7-120">该消息是 panic 级别。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-120">The message is a panic level.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa7f7-121">备注</span><span class="sxs-lookup"><span data-stu-id="fa7f7-121">Remarks</span></span>  
 <span data-ttu-id="fa7f7-122">公共语言运行时 (CLR) 调用[icordebugmanagedcallback:: Logmessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)方法以通知调试器托管的线程记录事件。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-122">The common language runtime (CLR) calls the [ICorDebugManagedCallback::LogMessage](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md) method to notify the debugger that a managed thread has logged an event.</span></span> <span data-ttu-id="fa7f7-123">CLR 将传递的值为`LoggingLevelEnum`枚举来指示托管的线程已写入到事件日志的消息的严重性级别。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-123">The CLR passes a value of the `LoggingLevelEnum` enumeration to indicate the severity level of the message that the managed thread wrote to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa7f7-124">要求</span><span class="sxs-lookup"><span data-stu-id="fa7f7-124">Requirements</span></span>  
 <span data-ttu-id="fa7f7-125">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fa7f7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa7f7-126">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa7f7-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa7f7-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa7f7-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fa7f7-128">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="fa7f7-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fa7f7-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa7f7-129">See also</span></span>

- <xref:System.Diagnostics.EventLog>
- [<span data-ttu-id="fa7f7-130">调试枚举</span><span class="sxs-lookup"><span data-stu-id="fa7f7-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
