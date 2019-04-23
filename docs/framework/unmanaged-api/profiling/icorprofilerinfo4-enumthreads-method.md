---
title: ICorProfilerInfo4::EnumThreads 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumThreads
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumThreads
helpviewer_keywords:
- ICorProfilerInfo4::EnumThreads method [.NET Framework profiling]
- EnumThreads method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: bca7a5b4-c207-4894-918c-0733926296dd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd0a4149b6dc6023579e8bc5b40751d23416e3a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202360"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="b262e-102">ICorProfilerInfo4::EnumThreads 方法</span><span class="sxs-lookup"><span data-stu-id="b262e-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="b262e-103">返回提供方法以按顺序循环访问所分析进程中的所有托管线程的集合的枚举器。</span><span class="sxs-lookup"><span data-stu-id="b262e-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b262e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b262e-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b262e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b262e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b262e-106">[out]一个指向[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="b262e-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b262e-107">备注</span><span class="sxs-lookup"><span data-stu-id="b262e-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b262e-108">要求</span><span class="sxs-lookup"><span data-stu-id="b262e-108">Requirements</span></span>  
 <span data-ttu-id="b262e-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b262e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b262e-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b262e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b262e-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b262e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b262e-112">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b262e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b262e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b262e-113">See also</span></span>

- [<span data-ttu-id="b262e-114">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b262e-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="b262e-115">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="b262e-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="b262e-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="b262e-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b262e-117">分析</span><span class="sxs-lookup"><span data-stu-id="b262e-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
