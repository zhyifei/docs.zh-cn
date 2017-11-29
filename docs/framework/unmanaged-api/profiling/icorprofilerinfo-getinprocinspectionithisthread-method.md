---
title: "ICorProfilerInfo::GetInprocInspectionIThisThread 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetInprocInspectionIThisThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9a260143e36939f4201d7949f5783f80e5c20ba7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="00600-102">ICorProfilerInfo::GetInprocInspectionIThisThread 方法</span><span class="sxs-lookup"><span data-stu-id="00600-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="00600-103">ICorDebugThread 接口获取可以查询的对象。</span><span class="sxs-lookup"><span data-stu-id="00600-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="00600-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="00600-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00600-105">语法</span><span class="sxs-lookup"><span data-stu-id="00600-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00600-106">参数</span><span class="sxs-lookup"><span data-stu-id="00600-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="00600-107">[out](/cpp/atl/iunknown)为查询的对象`ICorDebugThread`接口。</span><span class="sxs-lookup"><span data-stu-id="00600-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00600-108">备注</span><span class="sxs-lookup"><span data-stu-id="00600-108">Remarks</span></span>  
 <span data-ttu-id="00600-109">公共语言运行时 (CLR) 调试服务支持在.NET Framework 1.0 版中的有限进程内调试。</span><span class="sxs-lookup"><span data-stu-id="00600-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="00600-110">探查器使用了调试 API 的检查部分启用进程内调试。</span><span class="sxs-lookup"><span data-stu-id="00600-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="00600-111">由于客户反馈，进程内调试已从.NET Framework 2.0 版中，在中删除和替换为一组是根据分析 API 的详细信息的功能。</span><span class="sxs-lookup"><span data-stu-id="00600-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00600-112">要求</span><span class="sxs-lookup"><span data-stu-id="00600-112">Requirements</span></span>  
 <span data-ttu-id="00600-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00600-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00600-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00600-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="00600-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00600-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00600-116">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="00600-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00600-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00600-117">See Also</span></span>  
 [<span data-ttu-id="00600-118">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="00600-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
