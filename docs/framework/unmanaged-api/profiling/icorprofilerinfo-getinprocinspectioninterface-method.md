---
title: ICorProfilerInfo::GetInprocInspectionInterface 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 456dd8aedf11b1b27ee4926988fc615ebb7a76d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209926"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="55e3f-102">ICorProfilerInfo::GetInprocInspectionInterface 方法</span><span class="sxs-lookup"><span data-stu-id="55e3f-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="55e3f-103">对于"ICorDebugProcess"接口获取可查询的对象。</span><span class="sxs-lookup"><span data-stu-id="55e3f-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="55e3f-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="55e3f-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e3f-105">语法</span><span class="sxs-lookup"><span data-stu-id="55e3f-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55e3f-106">参数</span><span class="sxs-lookup"><span data-stu-id="55e3f-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="55e3f-107">[out](/cpp/atl/iunknown)对象，可用于查询`ICorDebugProcess`接口。</span><span class="sxs-lookup"><span data-stu-id="55e3f-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55e3f-108">备注</span><span class="sxs-lookup"><span data-stu-id="55e3f-108">Remarks</span></span>  
 <span data-ttu-id="55e3f-109">公共语言运行时 (CLR) 调试 API 支持.NET Framework 1.0 版中的有限进程内调试。</span><span class="sxs-lookup"><span data-stu-id="55e3f-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="55e3f-110">探查器可以使用调试 API 的检查部分启用进程内调试。</span><span class="sxs-lookup"><span data-stu-id="55e3f-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="55e3f-111">由于客户反馈，进程内调试已删除从.NET Framework 版本 2.0 中，并替换为一系列更加符合分析 API 的功能。</span><span class="sxs-lookup"><span data-stu-id="55e3f-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e3f-112">要求</span><span class="sxs-lookup"><span data-stu-id="55e3f-112">Requirements</span></span>  
 <span data-ttu-id="55e3f-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55e3f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e3f-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55e3f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55e3f-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55e3f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55e3f-116">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="55e3f-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e3f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="55e3f-117">See also</span></span>

- [<span data-ttu-id="55e3f-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="55e3f-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
