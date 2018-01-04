---
title: "ICorDebugThread::EnumerateChains 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.EnumerateChains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e6a9637edb4a846b4d10dd6565533a9219ad558
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="b733b-102">ICorDebugThread::EnumerateChains 方法</span><span class="sxs-lookup"><span data-stu-id="b733b-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="b733b-103">获取包含此 ICorDebugThread 对象中的所有堆栈链的 ICorDebugChainEnum 枚举的接口指针。</span><span class="sxs-lookup"><span data-stu-id="b733b-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b733b-104">语法</span><span class="sxs-lookup"><span data-stu-id="b733b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b733b-105">参数</span><span class="sxs-lookup"><span data-stu-id="b733b-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="b733b-106">[out]指向的地址的指针`ICorDebugChainEnum`开始 （即，最近） 活动链，此线程中链接的对象，它允许的所有堆栈的枚举。</span><span class="sxs-lookup"><span data-stu-id="b733b-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b733b-107">备注</span><span class="sxs-lookup"><span data-stu-id="b733b-107">Remarks</span></span>  
 <span data-ttu-id="b733b-108">堆栈链表示线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="b733b-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="b733b-109">以下情况下创建堆栈链边界：</span><span class="sxs-lookup"><span data-stu-id="b733b-109">The following circumstances create a stack chain boundary:</span></span>  
  
-   <span data-ttu-id="b733b-110">托管到非托管或非托管到托管的转换。</span><span class="sxs-lookup"><span data-stu-id="b733b-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
-   <span data-ttu-id="b733b-111">上下文切换。</span><span class="sxs-lookup"><span data-stu-id="b733b-111">A context switch.</span></span>  
  
-   <span data-ttu-id="b733b-112">一个调试器的用户线程劫持。</span><span class="sxs-lookup"><span data-stu-id="b733b-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="b733b-113">在为单一上下文中运行纯托管的代码的线程简单的情况下，存在一对一的对应关系将存在线程堆栈链之间。</span><span class="sxs-lookup"><span data-stu-id="b733b-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="b733b-114">调试器可能需要重新排列为逻辑调用堆栈的所有线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="b733b-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="b733b-115">这将涉及对所有线程的链通过其调用方/被调用方关系进行排序和重新分组。</span><span class="sxs-lookup"><span data-stu-id="b733b-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b733b-116">惠?</span><span class="sxs-lookup"><span data-stu-id="b733b-116">Requirements</span></span>  
 <span data-ttu-id="b733b-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b733b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b733b-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b733b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b733b-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b733b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b733b-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b733b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
