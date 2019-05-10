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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 148ca261e717b9a54192a13c317fe385b98f4ccd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651165"
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="8f174-102">COR_PRF_EX_CLAUSE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="8f174-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="8f174-103">存储有关特定的异常子句实例及其关联的帧的信息。</span><span class="sxs-lookup"><span data-stu-id="8f174-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f174-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f174-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="8f174-105">成员</span><span class="sxs-lookup"><span data-stu-id="8f174-105">Members</span></span>  
  
|<span data-ttu-id="8f174-106">成员</span><span class="sxs-lookup"><span data-stu-id="8f174-106">Member</span></span>|<span data-ttu-id="8f174-107">描述</span><span class="sxs-lookup"><span data-stu-id="8f174-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="8f174-108">值为[COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)枚举，用于指定异常子句只需输入的代码或左侧的类型。</span><span class="sxs-lookup"><span data-stu-id="8f174-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="8f174-109">子句处理程序的本机入口点 — 例如，X86 EIP 寄存器的内容。</span><span class="sxs-lookup"><span data-stu-id="8f174-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="8f174-110">子句处理程序的逻辑帧指针 — 例如，X86 EBP 寄存器的内容。</span><span class="sxs-lookup"><span data-stu-id="8f174-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="8f174-111">指向阴影堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="8f174-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="8f174-112">此值是 BSP 寄存器的内容，仅适用于 IA64。</span><span class="sxs-lookup"><span data-stu-id="8f174-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f174-113">备注</span><span class="sxs-lookup"><span data-stu-id="8f174-113">Remarks</span></span>  
 <span data-ttu-id="8f174-114">收到的异常通知后， [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)可用于获取在异常子句的本机地址和帧信息 (`catch` / `finally`/筛选)，要在运行或刚运行过。</span><span class="sxs-lookup"><span data-stu-id="8f174-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="8f174-115">执行的异常子句包括公共语言运行时 (CLR) 从这些回调：</span><span class="sxs-lookup"><span data-stu-id="8f174-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="8f174-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="8f174-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="8f174-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="8f174-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="8f174-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="8f174-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="8f174-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="8f174-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="8f174-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="8f174-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="8f174-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="8f174-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="8f174-122">要求</span><span class="sxs-lookup"><span data-stu-id="8f174-122">Requirements</span></span>  
 <span data-ttu-id="8f174-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f174-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f174-124">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8f174-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8f174-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f174-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f174-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f174-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f174-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f174-127">See also</span></span>

- [<span data-ttu-id="8f174-128">分析结构</span><span class="sxs-lookup"><span data-stu-id="8f174-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
