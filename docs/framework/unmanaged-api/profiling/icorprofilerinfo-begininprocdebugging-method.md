---
title: ICorProfilerInfo::BeginInprocDebugging 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
ms.openlocfilehash: fffc028c7706c86e8384483cc92ebad90b292861
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447753"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="4a77e-102">ICorProfilerInfo::BeginInprocDebugging 方法</span><span class="sxs-lookup"><span data-stu-id="4a77e-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="4a77e-103">初始化进程内调试支持。</span><span class="sxs-lookup"><span data-stu-id="4a77e-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="4a77e-104">此方法在 .NET Framework 版本2.0 中已过时。</span><span class="sxs-lookup"><span data-stu-id="4a77e-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a77e-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a77e-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a77e-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a77e-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="4a77e-107">中将此值设置为 `true` 以仅初始化当前线程的调试支持;将它设置为 "`false`"，以初始化所有线程的调试支持。</span><span class="sxs-lookup"><span data-stu-id="4a77e-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="4a77e-108">弄指向用于标识调试会话的返回值的指针。</span><span class="sxs-lookup"><span data-stu-id="4a77e-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a77e-109">备注</span><span class="sxs-lookup"><span data-stu-id="4a77e-109">Remarks</span></span>  
 <span data-ttu-id="4a77e-110">CLR 调试服务支持 .NET Framework 版本1.0 和1.1 中的有限进程内调试。</span><span class="sxs-lookup"><span data-stu-id="4a77e-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="4a77e-111">进程内调试使探查器能够使用调试 API 的检查部分。</span><span class="sxs-lookup"><span data-stu-id="4a77e-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="4a77e-112">不过，由于客户反馈，已从版本2.0 中的 .NET Framework 中删除进程内调试，并将其替换为一组功能，这些功能与分析 API 行更详细。</span><span class="sxs-lookup"><span data-stu-id="4a77e-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a77e-113">要求</span><span class="sxs-lookup"><span data-stu-id="4a77e-113">Requirements</span></span>  
 <span data-ttu-id="4a77e-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a77e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a77e-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4a77e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4a77e-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a77e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a77e-117">**.NET Framework 版本：** 1.0</span><span class="sxs-lookup"><span data-stu-id="4a77e-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a77e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a77e-118">See also</span></span>

- [<span data-ttu-id="4a77e-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4a77e-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
