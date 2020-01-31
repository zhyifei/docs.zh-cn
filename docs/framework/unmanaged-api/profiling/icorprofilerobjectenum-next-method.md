---
title: ICorProfilerObjectEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
ms.openlocfilehash: 0c833416cca965f2655266152c5bdf5f11624d14
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861121"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="c7857-102">ICorProfilerObjectEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="c7857-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="c7857-103">从对象的顺序集合中获取指定数目的连续对象，从该序列中的枚举器的当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="c7857-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7857-104">语法</span><span class="sxs-lookup"><span data-stu-id="c7857-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7857-105">参数</span><span class="sxs-lookup"><span data-stu-id="c7857-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c7857-106">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="c7857-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="c7857-107">弄`ObjectID` 值的数组，其中每个值都表示检索到的对象。</span><span class="sxs-lookup"><span data-stu-id="c7857-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c7857-108">[out] 指向 `objects` 数组中实际返回的元素数目的指针。</span><span class="sxs-lookup"><span data-stu-id="c7857-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7857-109">需求</span><span class="sxs-lookup"><span data-stu-id="c7857-109">Requirements</span></span>  
 <span data-ttu-id="c7857-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7857-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7857-111">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7857-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7857-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7857-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7857-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7857-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7857-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7857-114">See also</span></span>

- [<span data-ttu-id="c7857-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="c7857-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
