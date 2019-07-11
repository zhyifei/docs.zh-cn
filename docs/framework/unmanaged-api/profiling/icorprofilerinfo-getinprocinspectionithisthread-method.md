---
title: ICorProfilerInfo::GetInprocInspectionIThisThread 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e0f56dd6ece32b1f05418ea288da409af5cad5f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782766"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="b8ecb-102">ICorProfilerInfo::GetInprocInspectionIThisThread 方法</span><span class="sxs-lookup"><span data-stu-id="b8ecb-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="b8ecb-103">ICorDebugThread 接口获取可查询的对象。</span><span class="sxs-lookup"><span data-stu-id="b8ecb-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="b8ecb-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="b8ecb-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8ecb-105">语法</span><span class="sxs-lookup"><span data-stu-id="b8ecb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8ecb-106">参数</span><span class="sxs-lookup"><span data-stu-id="b8ecb-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="b8ecb-107">[out](/cpp/atl/iunknown)对象，可用于查询`ICorDebugThread`接口。</span><span class="sxs-lookup"><span data-stu-id="b8ecb-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8ecb-108">备注</span><span class="sxs-lookup"><span data-stu-id="b8ecb-108">Remarks</span></span>  
 <span data-ttu-id="b8ecb-109">公共语言运行时 (CLR) 调试服务支持有限的进程中调试.NET Framework 1.0 版中。</span><span class="sxs-lookup"><span data-stu-id="b8ecb-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="b8ecb-110">探查器可以使用调试 API 的检查部分启用进程内调试。</span><span class="sxs-lookup"><span data-stu-id="b8ecb-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b8ecb-111">由于客户反馈，进程内调试已删除从.NET Framework 版本 2.0 中，并替换为一系列更加符合分析 API 的功能。</span><span class="sxs-lookup"><span data-stu-id="b8ecb-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8ecb-112">要求</span><span class="sxs-lookup"><span data-stu-id="b8ecb-112">Requirements</span></span>  
 <span data-ttu-id="b8ecb-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b8ecb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8ecb-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8ecb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8ecb-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8ecb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8ecb-116">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="b8ecb-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ecb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8ecb-117">See also</span></span>

- [<span data-ttu-id="b8ecb-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b8ecb-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
