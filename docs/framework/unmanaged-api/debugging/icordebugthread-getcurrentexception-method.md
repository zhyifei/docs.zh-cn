---
title: "ICorDebugThread::GetCurrentException 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c18e2dfa68d425e5ec23d4573428018bc971f8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="28064-102">ICorDebugThread::GetCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="28064-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="28064-103">获取一个表示托管代码所引发的异常的 ICorDebugValue 对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="28064-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28064-104">语法</span><span class="sxs-lookup"><span data-stu-id="28064-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28064-105">参数</span><span class="sxs-lookup"><span data-stu-id="28064-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="28064-106">[out]指向的地址的指针`ICorDebugValue`表示当前所引发的异常的对象托管代码。</span><span class="sxs-lookup"><span data-stu-id="28064-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28064-107">备注</span><span class="sxs-lookup"><span data-stu-id="28064-107">Remarks</span></span>  
 <span data-ttu-id="28064-108">从异常结束前的时间将存在的异常对象`catch`块。</span><span class="sxs-lookup"><span data-stu-id="28064-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="28064-109">由 ICorDebugEval 方法执行，则函数求值将清空在安装中的异常对象，并将其还原完成。</span><span class="sxs-lookup"><span data-stu-id="28064-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="28064-110">可以嵌套异常，（例如，如果筛选器中或函数求值，将引发异常），所以可能有对单个线程的多个未处理异常。</span><span class="sxs-lookup"><span data-stu-id="28064-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="28064-111">`GetCurrentException`返回最新的异常。</span><span class="sxs-lookup"><span data-stu-id="28064-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="28064-112">在异常的生命周期更改可能的异常对象和类型。</span><span class="sxs-lookup"><span data-stu-id="28064-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="28064-113">例如，将引发异常的类型为 x 后，公共语言运行时 (CLR) 可能内存不足的情况并将其升级到内存不足异常。</span><span class="sxs-lookup"><span data-stu-id="28064-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28064-114">惠?</span><span class="sxs-lookup"><span data-stu-id="28064-114">Requirements</span></span>  
 <span data-ttu-id="28064-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28064-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28064-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28064-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28064-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28064-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28064-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28064-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
