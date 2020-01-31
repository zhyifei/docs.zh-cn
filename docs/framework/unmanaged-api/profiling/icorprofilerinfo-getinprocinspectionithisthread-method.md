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
ms.openlocfilehash: 0ab383f0968061667b3580a2058687eecda99dde
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869993"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="b3eef-102">ICorProfilerInfo::GetInprocInspectionIThisThread 方法</span><span class="sxs-lookup"><span data-stu-id="b3eef-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="b3eef-103">获取一个对象，该对象可查询 ICorDebugThread 接口。</span><span class="sxs-lookup"><span data-stu-id="b3eef-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="b3eef-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="b3eef-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3eef-105">语法</span><span class="sxs-lookup"><span data-stu-id="b3eef-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3eef-106">参数</span><span class="sxs-lookup"><span data-stu-id="b3eef-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="b3eef-107">[out](/cpp/atl/iunknown)对象，可查询 `ICorDebugThread` 接口。</span><span class="sxs-lookup"><span data-stu-id="b3eef-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3eef-108">备注</span><span class="sxs-lookup"><span data-stu-id="b3eef-108">Remarks</span></span>  
 <span data-ttu-id="b3eef-109">在 .NET Framework 版本1.0 中，公共语言运行时（CLR）调试服务支持有限的进程内调试。</span><span class="sxs-lookup"><span data-stu-id="b3eef-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="b3eef-110">进程内调试使探查器能够使用调试 API 的检查部分。</span><span class="sxs-lookup"><span data-stu-id="b3eef-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b3eef-111">由于客户反馈，已从版本2.0 中的 .NET Framework 中删除进程内调试，并将其替换为一组功能，这些功能与分析 API 是一种更多的功能。</span><span class="sxs-lookup"><span data-stu-id="b3eef-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3eef-112">需求</span><span class="sxs-lookup"><span data-stu-id="b3eef-112">Requirements</span></span>  
 <span data-ttu-id="b3eef-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b3eef-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3eef-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3eef-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3eef-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3eef-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3eef-116">**.NET Framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="b3eef-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3eef-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3eef-117">See also</span></span>

- [<span data-ttu-id="b3eef-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="b3eef-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
