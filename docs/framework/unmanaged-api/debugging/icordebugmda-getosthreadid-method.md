---
title: ICorDebugMDA::GetOSThreadId 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51d29fed3d53611daa0042251ce09638399f7ed5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723142"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="7355b-102">ICorDebugMDA::GetOSThreadId 方法</span><span class="sxs-lookup"><span data-stu-id="7355b-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="7355b-103">获取在其托管调试助手 (MDA) 表示的操作系统 (OS) 线程标识符[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)正在执行。</span><span class="sxs-lookup"><span data-stu-id="7355b-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7355b-104">语法</span><span class="sxs-lookup"><span data-stu-id="7355b-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7355b-105">参数</span><span class="sxs-lookup"><span data-stu-id="7355b-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="7355b-106">[out]一个指向 OS 线程标识符。</span><span class="sxs-lookup"><span data-stu-id="7355b-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7355b-107">备注</span><span class="sxs-lookup"><span data-stu-id="7355b-107">Remarks</span></span>  
 <span data-ttu-id="7355b-108">OS 线程而不是 ICorDebugThread 用于本机线程或尚未输入托管的代码的托管线程 MDA 触发的情况下允许。</span><span class="sxs-lookup"><span data-stu-id="7355b-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7355b-109">要求</span><span class="sxs-lookup"><span data-stu-id="7355b-109">Requirements</span></span>  
 <span data-ttu-id="7355b-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7355b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7355b-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7355b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7355b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7355b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7355b-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7355b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7355b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7355b-114">See also</span></span>

- [<span data-ttu-id="7355b-115">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="7355b-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="7355b-116">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="7355b-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
