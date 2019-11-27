---
title: COR_PRF_EX_CLAUSE_INFO 结构
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: df4bfe69b22439073342693a03376a0b506f9c70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428374"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="aaa7c-102">COR_PRF_EX_CLAUSE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="aaa7c-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="aaa7c-103">存储有关特定的异常子句实例及其关联的帧的信息。</span><span class="sxs-lookup"><span data-stu-id="aaa7c-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="aaa7c-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="aaa7c-105">Members</span><span class="sxs-lookup"><span data-stu-id="aaa7c-105">Members</span></span>  
  
|<span data-ttu-id="aaa7c-106">成员</span><span class="sxs-lookup"><span data-stu-id="aaa7c-106">Member</span></span>|<span data-ttu-id="aaa7c-107">说明</span><span class="sxs-lookup"><span data-stu-id="aaa7c-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="aaa7c-108">一个[COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)枚举的值，该值指定代码刚刚进入或离开的异常子句的类型。</span><span class="sxs-lookup"><span data-stu-id="aaa7c-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="aaa7c-109">子句处理程序的本地入口点（例如 X86 EIP 寄存器的内容）。</span><span class="sxs-lookup"><span data-stu-id="aaa7c-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="aaa7c-110">指向子句处理程序的逻辑帧的指针，例如 X86 EBP 寄存器的内容。</span><span class="sxs-lookup"><span data-stu-id="aaa7c-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="aaa7c-111">指向阴影堆栈的指针。</span><span class="sxs-lookup"><span data-stu-id="aaa7c-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="aaa7c-112">此值为 BSP 寄存器的内容，并且仅适用于 IA64。</span><span class="sxs-lookup"><span data-stu-id="aaa7c-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaa7c-113">备注</span><span class="sxs-lookup"><span data-stu-id="aaa7c-113">Remarks</span></span>  
 <span data-ttu-id="aaa7c-114">收到异常通知时， [ICorProfilerInfo2：： GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)可用于获取即将运行或刚刚运行的异常子句（`catch`/`finally`/filter）的本机地址和帧信息。</span><span class="sxs-lookup"><span data-stu-id="aaa7c-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="aaa7c-115">执行 exception 子句涉及来自公共语言运行时（CLR）的这些回调：</span><span class="sxs-lookup"><span data-stu-id="aaa7c-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="aaa7c-116">ICorProfilerCallback：： ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="aaa7c-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="aaa7c-117">ICorProfilerCallback：： ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="aaa7c-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="aaa7c-118">ICorProfilerCallback：： ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="aaa7c-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="aaa7c-119">ICorProfilerCallback：： ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="aaa7c-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="aaa7c-120">ICorProfilerCallback：： ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="aaa7c-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="aaa7c-121">ICorProfilerCallback：： ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="aaa7c-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="aaa7c-122">要求</span><span class="sxs-lookup"><span data-stu-id="aaa7c-122">Requirements</span></span>  
 <span data-ttu-id="aaa7c-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa7c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaa7c-124">**标头：** Corprof.idl .idl</span><span class="sxs-lookup"><span data-stu-id="aaa7c-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="aaa7c-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaa7c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaa7c-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaa7c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa7c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aaa7c-127">See also</span></span>

- [<span data-ttu-id="aaa7c-128">分析结构</span><span class="sxs-lookup"><span data-stu-id="aaa7c-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
