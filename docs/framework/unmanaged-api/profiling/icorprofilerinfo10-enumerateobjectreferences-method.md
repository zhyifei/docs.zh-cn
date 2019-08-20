---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 4b13659f7c9909e9795caee1eace8da8092c5b9a
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974027"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="07c13-102">ICorProfilerInfo10:: EnumerateObjectReferences 方法</span><span class="sxs-lookup"><span data-stu-id="07c13-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>
  
 <span data-ttu-id="07c13-103">给定 ObjectID、callback 和 clientData, 枚举每个对象引用 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="07c13-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="07c13-104">语法</span><span class="sxs-lookup"><span data-stu-id="07c13-104">Syntax</span></span>  
  
```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```  
  
#### <a name="parameters"></a><span data-ttu-id="07c13-105">参数</span><span class="sxs-lookup"><span data-stu-id="07c13-105">Parameters</span></span>  

 `objectId` \
 <span data-ttu-id="07c13-106">中要在其上枚举引用的对象。</span><span class="sxs-lookup"><span data-stu-id="07c13-106">[in] The object to enumerate references on.</span></span>

 `callback` \
 <span data-ttu-id="07c13-107">中将用对象的引用调用的函数。</span><span class="sxs-lookup"><span data-stu-id="07c13-107">[in] The function that will be called with the references for the object.</span></span>

 `clientData` \
 <span data-ttu-id="07c13-108">中探查器提供的要传递给函数`callback`的数据。</span><span class="sxs-lookup"><span data-stu-id="07c13-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="07c13-109">备注</span><span class="sxs-lookup"><span data-stu-id="07c13-109">Remarks</span></span>  
 <span data-ttu-id="07c13-110">方法类似于 [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), 只不过它会按需对探查器进行引用, 而不是预先分配用于存储引用的数组。 `EnumerateObjectReferences`</span><span class="sxs-lookup"><span data-stu-id="07c13-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>  

## <a name="requirements"></a><span data-ttu-id="07c13-111">要求</span><span class="sxs-lookup"><span data-stu-id="07c13-111">Requirements</span></span>  
 <span data-ttu-id="07c13-112">**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。</span><span class="sxs-lookup"><span data-stu-id="07c13-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="07c13-113">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="07c13-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="07c13-114">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07c13-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07c13-115">**.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07c13-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="07c13-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="07c13-116">See also</span></span>
- [<span data-ttu-id="07c13-117">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="07c13-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

