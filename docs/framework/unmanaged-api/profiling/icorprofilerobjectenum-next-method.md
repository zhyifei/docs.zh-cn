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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 221752b537cd3a890ad646290a64a7022692f625
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173935"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="3ce11-102">ICorProfilerObjectEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="3ce11-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="3ce11-103">从对象，从当前位置开始枚举器的序列中的序列集合获取指定的数目的连续对象。</span><span class="sxs-lookup"><span data-stu-id="3ce11-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce11-104">语法</span><span class="sxs-lookup"><span data-stu-id="3ce11-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ce11-105">参数</span><span class="sxs-lookup"><span data-stu-id="3ce11-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="3ce11-106">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="3ce11-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="3ce11-107">[out]一个数组`ObjectID`值，其中每个表示检索到的对象。</span><span class="sxs-lookup"><span data-stu-id="3ce11-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="3ce11-108">[out] 指向 `objects` 数组中实际返回的元素数目的指针。</span><span class="sxs-lookup"><span data-stu-id="3ce11-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ce11-109">要求</span><span class="sxs-lookup"><span data-stu-id="3ce11-109">Requirements</span></span>  
 <span data-ttu-id="3ce11-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ce11-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ce11-111">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ce11-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ce11-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ce11-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ce11-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ce11-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce11-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ce11-114">See also</span></span>

- [<span data-ttu-id="3ce11-115">ICorProfilerObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="3ce11-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
