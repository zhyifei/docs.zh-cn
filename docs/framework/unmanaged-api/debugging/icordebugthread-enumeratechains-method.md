---
title: ICorDebugThread::EnumerateChains 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
ms.openlocfilehash: 38fe50f5a6608bb27d7a7818dee4784a7f8113ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133605"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="efab5-102">ICorDebugThread::EnumerateChains 方法</span><span class="sxs-lookup"><span data-stu-id="efab5-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="efab5-103">获取一个接口指针，该指针指向包含此 ICorDebugThread 对象中所有堆栈链的 ICorDebugChainEnum 枚举器。</span><span class="sxs-lookup"><span data-stu-id="efab5-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efab5-104">语法</span><span class="sxs-lookup"><span data-stu-id="efab5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efab5-105">参数</span><span class="sxs-lookup"><span data-stu-id="efab5-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="efab5-106">弄指向 `ICorDebugChainEnum` 对象地址的指针，该对象允许枚举此线程中的所有堆栈链，从活动（即最近的）链开始。</span><span class="sxs-lookup"><span data-stu-id="efab5-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efab5-107">备注</span><span class="sxs-lookup"><span data-stu-id="efab5-107">Remarks</span></span>  
 <span data-ttu-id="efab5-108">堆栈链表示线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="efab5-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="efab5-109">以下情况会创建堆栈链边界：</span><span class="sxs-lookup"><span data-stu-id="efab5-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="efab5-110">托管到非托管或非托管的转换。</span><span class="sxs-lookup"><span data-stu-id="efab5-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="efab5-111">上下文切换。</span><span class="sxs-lookup"><span data-stu-id="efab5-111">A context switch.</span></span>  
  
- <span data-ttu-id="efab5-112">用户线程的调试器劫持。</span><span class="sxs-lookup"><span data-stu-id="efab5-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="efab5-113">在单个上下文中运行纯托管代码的线程的简单情况下，线程与堆栈链之间存在一对一的对应关系。</span><span class="sxs-lookup"><span data-stu-id="efab5-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="efab5-114">调试器可能需要将所有线程的物理调用堆栈重新排列为逻辑调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="efab5-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="efab5-115">这涉及到通过其调用方/被调用方关系对所有线程链进行排序并 regrouping 它们。</span><span class="sxs-lookup"><span data-stu-id="efab5-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efab5-116">要求</span><span class="sxs-lookup"><span data-stu-id="efab5-116">Requirements</span></span>  
 <span data-ttu-id="efab5-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efab5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efab5-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efab5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efab5-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efab5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efab5-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efab5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
