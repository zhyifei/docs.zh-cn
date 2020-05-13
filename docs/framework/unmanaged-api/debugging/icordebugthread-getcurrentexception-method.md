---
title: ICorDebugThread::GetCurrentException 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 3a4da6f958407c0b704ffb7372a77b7f022fc824
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379771"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="3940c-102">ICorDebugThread::GetCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="3940c-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="3940c-103">获取一个指向 ICorDebugValue 对象的接口指针，该对象表示当前由托管代码引发的异常。</span><span class="sxs-lookup"><span data-stu-id="3940c-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3940c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3940c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3940c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3940c-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="3940c-106">弄指向对象地址的指针 `ICorDebugValue` ，该对象表示当前由托管代码引发的异常。</span><span class="sxs-lookup"><span data-stu-id="3940c-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3940c-107">备注</span><span class="sxs-lookup"><span data-stu-id="3940c-107">Remarks</span></span>  
 <span data-ttu-id="3940c-108">异常对象将在引发异常时出现，直至 `catch` 该块结束。</span><span class="sxs-lookup"><span data-stu-id="3940c-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="3940c-109">由 ICorDebugEval 方法执行的函数计算将清除安装程序上的异常对象并在完成时将其还原。</span><span class="sxs-lookup"><span data-stu-id="3940c-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="3940c-110">可以嵌套异常（例如，如果在筛选器或函数计算中引发了异常），则单个线程上可能存在多个未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="3940c-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="3940c-111">`GetCurrentException`返回最新的异常。</span><span class="sxs-lookup"><span data-stu-id="3940c-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="3940c-112">异常对象和类型在异常的整个生命周期中可能会更改。</span><span class="sxs-lookup"><span data-stu-id="3940c-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="3940c-113">例如，在引发类型 x 的异常后，公共语言运行时（CLR）可能会耗尽内存，并将其提升为内存不足的异常。</span><span class="sxs-lookup"><span data-stu-id="3940c-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3940c-114">要求</span><span class="sxs-lookup"><span data-stu-id="3940c-114">Requirements</span></span>  
 <span data-ttu-id="3940c-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3940c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3940c-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3940c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3940c-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3940c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3940c-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3940c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
