---
title: ICorProfilerInfo::EndInprocDebugging 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7365deb11bf620fcda43e7f04347cfe4685b5a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780241"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="8e769-102">ICorProfilerInfo::EndInprocDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="8e769-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="8e769-103">关闭进程内调试会话。</span><span class="sxs-lookup"><span data-stu-id="8e769-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="8e769-104">此方法是在.NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="8e769-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e769-105">语法</span><span class="sxs-lookup"><span data-stu-id="8e769-105">Syntax</span></span>  
  
```cpp  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e769-106">参数</span><span class="sxs-lookup"><span data-stu-id="8e769-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="8e769-107">[in]一个值，标识的调试会话。</span><span class="sxs-lookup"><span data-stu-id="8e769-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="8e769-108">此值必须与在中收到相同[icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8e769-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e769-109">备注</span><span class="sxs-lookup"><span data-stu-id="8e769-109">Remarks</span></span>  
 <span data-ttu-id="8e769-110">必须调用[icorprofilerinfo:: Begininprocdebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)和`EndInprocDebugging`中相同的回调方法。</span><span class="sxs-lookup"><span data-stu-id="8e769-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="8e769-111">CLR 调试服务支持在.NET framework 1.0 和 1.1 版中进行有限进程内调试。</span><span class="sxs-lookup"><span data-stu-id="8e769-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="8e769-112">探查器可以使用调试 API 的检查部分启用进程内调试。</span><span class="sxs-lookup"><span data-stu-id="8e769-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="8e769-113">但是，由于客户反馈，进程内调试已从.NET Framework 2.0 版中，在中删除并替换为符合分析 API 的更多的功能的一组。</span><span class="sxs-lookup"><span data-stu-id="8e769-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e769-114">要求</span><span class="sxs-lookup"><span data-stu-id="8e769-114">Requirements</span></span>  
 <span data-ttu-id="8e769-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e769-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e769-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e769-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e769-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e769-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e769-118">**.NET framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="8e769-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e769-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e769-119">See also</span></span>

- [<span data-ttu-id="8e769-120">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="8e769-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
