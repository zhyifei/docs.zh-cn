---
title: "ICorDebugMDA::GetOSThreadId 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetOSThreadId
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6cc53eecadd982d7cea045424de52d8e6f64107b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="9fe8d-102">ICorDebugMDA::GetOSThreadId 方法</span><span class="sxs-lookup"><span data-stu-id="9fe8d-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="9fe8d-103">获取在其托管调试助手 (MDA) 由的操作系统 (OS) 线程标识符[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)正在执行。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9fe8d-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fe8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="9fe8d-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="9fe8d-106">[out]指向 OS 线程标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fe8d-107">备注</span><span class="sxs-lookup"><span data-stu-id="9fe8d-107">Remarks</span></span>  
 <span data-ttu-id="9fe8d-108">OS 线程而不是 ICorDebugThread 用于允许的情况下在本机线程上或没有尚未进入托管的代码的托管线程上 MDA 激发。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fe8d-109">要求</span><span class="sxs-lookup"><span data-stu-id="9fe8d-109">Requirements</span></span>  
 <span data-ttu-id="9fe8d-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe8d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe8d-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fe8d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fe8d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fe8d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fe8d-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe8d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe8d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fe8d-114">See Also</span></span>  
 [<span data-ttu-id="9fe8d-115">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="9fe8d-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="9fe8d-116">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="9fe8d-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
