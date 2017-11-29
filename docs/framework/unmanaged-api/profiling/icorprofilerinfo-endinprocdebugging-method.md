---
title: "ICorProfilerInfo::EndInprocDebugging 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.EndInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6e87cf210fb2717379e6bdc0b687028d680fe624
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="f762a-102">ICorProfilerInfo::EndInprocDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="f762a-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="f762a-103">关闭进程内调试会话。</span><span class="sxs-lookup"><span data-stu-id="f762a-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="f762a-104">此方法是.NET Framework 2.0 版中过时。</span><span class="sxs-lookup"><span data-stu-id="f762a-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f762a-105">语法</span><span class="sxs-lookup"><span data-stu-id="f762a-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f762a-106">参数</span><span class="sxs-lookup"><span data-stu-id="f762a-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="f762a-107">[in]一个值，标识的调试会话。</span><span class="sxs-lookup"><span data-stu-id="f762a-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="f762a-108">此值必须与在中收到相同[icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f762a-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f762a-109">备注</span><span class="sxs-lookup"><span data-stu-id="f762a-109">Remarks</span></span>  
 <span data-ttu-id="f762a-110">必须调用[icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)和`EndInprocDebugging`中相同的回叫方法。</span><span class="sxs-lookup"><span data-stu-id="f762a-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="f762a-111">CLR 调试服务支持在.NET framework 1.0 和 1.1 版中的有限进程内调试。</span><span class="sxs-lookup"><span data-stu-id="f762a-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="f762a-112">探查器使用了调试 API 的检查部分启用进程内调试。</span><span class="sxs-lookup"><span data-stu-id="f762a-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="f762a-113">但是，由于客户反馈，进程内调试已从.NET Framework 2.0 版中，在中删除和替换为一组是根据分析 API 的详细信息的功能。</span><span class="sxs-lookup"><span data-stu-id="f762a-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f762a-114">要求</span><span class="sxs-lookup"><span data-stu-id="f762a-114">Requirements</span></span>  
 <span data-ttu-id="f762a-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f762a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f762a-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f762a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f762a-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f762a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f762a-118">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="f762a-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f762a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f762a-119">See Also</span></span>  
 [<span data-ttu-id="f762a-120">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="f762a-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
