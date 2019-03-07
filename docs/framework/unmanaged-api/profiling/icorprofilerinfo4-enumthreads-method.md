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
ms.openlocfilehash: 8c4d754ea00dae3893b8630e248523b97ae96d78
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496776"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="9d124-102">ICorProfilerInfo4::EnumThreads 方法</span><span class="sxs-lookup"><span data-stu-id="9d124-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="9d124-103">返回提供方法以按顺序循环访问所分析进程中的所有托管线程的集合的枚举器。</span><span class="sxs-lookup"><span data-stu-id="9d124-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d124-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d124-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d124-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d124-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="9d124-106">[out]一个指向[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="9d124-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d124-107">备注</span><span class="sxs-lookup"><span data-stu-id="9d124-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d124-108">要求</span><span class="sxs-lookup"><span data-stu-id="9d124-108">Requirements</span></span>  
 <span data-ttu-id="9d124-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d124-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d124-110">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d124-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d124-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d124-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d124-112">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d124-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d124-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d124-113">See also</span></span>
- [<span data-ttu-id="9d124-114">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="9d124-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="9d124-115">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="9d124-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="9d124-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="9d124-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="9d124-117">分析</span><span class="sxs-lookup"><span data-stu-id="9d124-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
