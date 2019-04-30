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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e01f94e9574ebc032bc45490fd88ff92e9104aa3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994040"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="83789-102">ICorDebugThread::EnumerateChains 方法</span><span class="sxs-lookup"><span data-stu-id="83789-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="83789-103">获取包含此 ICorDebugThread 对象中的所有堆栈链的 ICorDebugChainEnum 枚举器的接口指针。</span><span class="sxs-lookup"><span data-stu-id="83789-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83789-104">语法</span><span class="sxs-lookup"><span data-stu-id="83789-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83789-105">参数</span><span class="sxs-lookup"><span data-stu-id="83789-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="83789-106">[out]指向的地址的指针`ICorDebugChainEnum`允许所有堆栈的枚举对象链接在此线程开始活动 （即，最新的） 链中。</span><span class="sxs-lookup"><span data-stu-id="83789-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83789-107">备注</span><span class="sxs-lookup"><span data-stu-id="83789-107">Remarks</span></span>  
 <span data-ttu-id="83789-108">堆栈链表示在线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="83789-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="83789-109">在以下情况下创建一个堆栈链边界：</span><span class="sxs-lookup"><span data-stu-id="83789-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="83789-110">托管到非托管或非托管到托管的转换。</span><span class="sxs-lookup"><span data-stu-id="83789-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="83789-111">上下文切换。</span><span class="sxs-lookup"><span data-stu-id="83789-111">A context switch.</span></span>  
  
- <span data-ttu-id="83789-112">一个调试器用户线程进行的攻击。</span><span class="sxs-lookup"><span data-stu-id="83789-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="83789-113">在单一上下文中运行纯托管的代码的线程的简单情况下，线程和堆栈链之间存在一对一的对应关系。</span><span class="sxs-lookup"><span data-stu-id="83789-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="83789-114">调试程序可能想要为逻辑调用堆栈中重新排列的所有线程的物理调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="83789-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="83789-115">这通常需要对所有线程的链由其调用方/被调用方关系进行排序并重新分组。</span><span class="sxs-lookup"><span data-stu-id="83789-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83789-116">要求</span><span class="sxs-lookup"><span data-stu-id="83789-116">Requirements</span></span>  
 <span data-ttu-id="83789-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83789-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83789-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83789-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83789-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83789-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83789-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83789-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
