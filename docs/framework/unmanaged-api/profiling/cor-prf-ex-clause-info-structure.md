---
title: "COR_PRF_EX_CLAUSE_INFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_EX_CLAUSE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords: COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65025384aa94ac363336bae7f37f8ea88a3bab67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="21359-102">COR_PRF_EX_CLAUSE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="21359-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="21359-103">存储有关特定的异常子句实例及其关联的帧的信息。</span><span class="sxs-lookup"><span data-stu-id="21359-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21359-104">语法</span><span class="sxs-lookup"><span data-stu-id="21359-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="21359-105">成员</span><span class="sxs-lookup"><span data-stu-id="21359-105">Members</span></span>  
  
|<span data-ttu-id="21359-106">成员</span><span class="sxs-lookup"><span data-stu-id="21359-106">Member</span></span>|<span data-ttu-id="21359-107">描述</span><span class="sxs-lookup"><span data-stu-id="21359-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="21359-108">值为[COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)指定异常子句的代码刚进入或离开的类型的枚举。</span><span class="sxs-lookup"><span data-stu-id="21359-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="21359-109">子句处理程序的本机入口点-例如，X86 EIP 寄存器的内容。</span><span class="sxs-lookup"><span data-stu-id="21359-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="21359-110">子句处理程序的逻辑帧指针 — 例如，X86 EBP 寄存器的内容。</span><span class="sxs-lookup"><span data-stu-id="21359-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="21359-111">指向阴影堆栈指针。</span><span class="sxs-lookup"><span data-stu-id="21359-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="21359-112">此值是 BSP 寄存器的内容，仅适用于 IA64。</span><span class="sxs-lookup"><span data-stu-id="21359-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21359-113">备注</span><span class="sxs-lookup"><span data-stu-id="21359-113">Remarks</span></span>  
 <span data-ttu-id="21359-114">当收到的异常通知时， [icorprofilerinfo2:: Getnotifiedexceptionclauseinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)可用来获取的异常子句的本机地址和帧信息 (`catch` / `finally`/筛选)，是要运行或只需运行。</span><span class="sxs-lookup"><span data-stu-id="21359-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="21359-115">异常子句的执行涉及从公共语言运行时 (CLR) 的这些回调：</span><span class="sxs-lookup"><span data-stu-id="21359-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="21359-116">Icorprofilercallback:: Exceptioncatcherenter</span><span class="sxs-lookup"><span data-stu-id="21359-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="21359-117">Icorprofilercallback:: Exceptionunwindfinallyenter</span><span class="sxs-lookup"><span data-stu-id="21359-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="21359-118">Icorprofilercallback:: Exceptionsearchfilterenter</span><span class="sxs-lookup"><span data-stu-id="21359-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="21359-119">Icorprofilercallback:: Exceptioncatcherleave</span><span class="sxs-lookup"><span data-stu-id="21359-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="21359-120">Icorprofilercallback:: Exceptionunwindfinallyleave</span><span class="sxs-lookup"><span data-stu-id="21359-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="21359-121">Icorprofilercallback:: Exceptionsearchfilterleave</span><span class="sxs-lookup"><span data-stu-id="21359-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="21359-122">惠?</span><span class="sxs-lookup"><span data-stu-id="21359-122">Requirements</span></span>  
 <span data-ttu-id="21359-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21359-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21359-124">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="21359-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="21359-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21359-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21359-126">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21359-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21359-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="21359-127">See Also</span></span>  
 [<span data-ttu-id="21359-128">分析结构</span><span class="sxs-lookup"><span data-stu-id="21359-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
