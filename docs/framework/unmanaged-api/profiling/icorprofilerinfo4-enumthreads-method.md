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
ms.openlocfilehash: 6c394690f6c8d7f3618b385b0a1432fc396fb819
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458015"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="f7474-102">ICorProfilerInfo4::EnumThreads 方法</span><span class="sxs-lookup"><span data-stu-id="f7474-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="f7474-103">返回一个枚举器提供方法以按顺序循环访问集合的所分析进程中的所有托管线程。</span><span class="sxs-lookup"><span data-stu-id="f7474-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7474-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7474-104">Syntax</span></span>  
  
```  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7474-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7474-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f7474-106">[out]指向的指针[ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="f7474-106">[out] A pointer to an [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7474-107">备注</span><span class="sxs-lookup"><span data-stu-id="f7474-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7474-108">要求</span><span class="sxs-lookup"><span data-stu-id="f7474-108">Requirements</span></span>  
 <span data-ttu-id="f7474-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7474-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7474-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7474-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7474-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7474-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7474-112">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7474-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7474-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7474-113">See Also</span></span>  
 [<span data-ttu-id="f7474-114">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="f7474-114">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="f7474-115">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="f7474-115">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="f7474-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="f7474-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="f7474-117">分析</span><span class="sxs-lookup"><span data-stu-id="f7474-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
