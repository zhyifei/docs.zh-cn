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
ms.openlocfilehash: 5bea1b75e94d8011d3582d4f07d36bbc7a560502
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862212"
---
# <a name="icorprofilerinfo4enumthreads-method"></a><span data-ttu-id="714c1-102">ICorProfilerInfo4::EnumThreads 方法</span><span class="sxs-lookup"><span data-stu-id="714c1-102">ICorProfilerInfo4::EnumThreads Method</span></span>
<span data-ttu-id="714c1-103">返回一个枚举器，该枚举器提供按顺序循环访问所分析进程中所有托管线程的集合的方法。</span><span class="sxs-lookup"><span data-stu-id="714c1-103">Returns an enumerator that provides methods to sequentially iterate through the collection of all managed threads in the profiled process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="714c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="714c1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumThreads([out]  
            ICorProfilerThreadEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="714c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="714c1-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="714c1-106">弄指向[ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="714c1-106">[out] A pointer to an [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="714c1-107">备注</span><span class="sxs-lookup"><span data-stu-id="714c1-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="714c1-108">需求</span><span class="sxs-lookup"><span data-stu-id="714c1-108">Requirements</span></span>  
 <span data-ttu-id="714c1-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="714c1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="714c1-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="714c1-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="714c1-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="714c1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="714c1-112">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="714c1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714c1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="714c1-113">See also</span></span>

- [<span data-ttu-id="714c1-114">ICorProfilerThreadEnum 接口</span><span class="sxs-lookup"><span data-stu-id="714c1-114">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="714c1-115">ICorProfilerInfo4 接口</span><span class="sxs-lookup"><span data-stu-id="714c1-115">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="714c1-116">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="714c1-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="714c1-117">分析</span><span class="sxs-lookup"><span data-stu-id="714c1-117">Profiling</span></span>](index.md)
