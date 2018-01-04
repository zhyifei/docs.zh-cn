---
title: "ICorProfilerInfo::BeginInprocDebugging 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.BeginInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91306bbea7b099f7e9e408f8bf69625f1d7da68e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="5260a-102">ICorProfilerInfo::BeginInprocDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="5260a-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="5260a-103">初始化进程内调试支持。</span><span class="sxs-lookup"><span data-stu-id="5260a-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="5260a-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="5260a-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5260a-105">语法</span><span class="sxs-lookup"><span data-stu-id="5260a-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5260a-106">参数</span><span class="sxs-lookup"><span data-stu-id="5260a-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="5260a-107">[in]将此值设置为`true`初始化调试支持仅当前线程; 将其设置为`false`初始化的所有线程的调试支持。</span><span class="sxs-lookup"><span data-stu-id="5260a-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="5260a-108">[out]指向标识调试会话的返回值的指针。</span><span class="sxs-lookup"><span data-stu-id="5260a-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5260a-109">备注</span><span class="sxs-lookup"><span data-stu-id="5260a-109">Remarks</span></span>  
 <span data-ttu-id="5260a-110">CLR 调试服务支持在.NET framework 1.0 和 1.1 版中的有限进程内调试。</span><span class="sxs-lookup"><span data-stu-id="5260a-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="5260a-111">探查器使用了调试 API 的检查部分启用进程内调试。</span><span class="sxs-lookup"><span data-stu-id="5260a-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="5260a-112">但是，由于客户反馈，进程内调试已从.NET Framework 2.0 版中，在中删除和替换为一组是根据分析 API 的详细信息的功能。</span><span class="sxs-lookup"><span data-stu-id="5260a-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5260a-113">惠?</span><span class="sxs-lookup"><span data-stu-id="5260a-113">Requirements</span></span>  
 <span data-ttu-id="5260a-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5260a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5260a-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5260a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5260a-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5260a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5260a-117">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="5260a-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5260a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5260a-118">See Also</span></span>  
 [<span data-ttu-id="5260a-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="5260a-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
