---
title: ICorProfilerInfo::IsArrayClass 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
ms.openlocfilehash: 57515ac4670b9b7e25bb496851347a62e1b246df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438723"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="44c08-102">ICorProfilerInfo::IsArrayClass 方法</span><span class="sxs-lookup"><span data-stu-id="44c08-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="44c08-103">确定指定的类是否为数组类。</span><span class="sxs-lookup"><span data-stu-id="44c08-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c08-104">语法</span><span class="sxs-lookup"><span data-stu-id="44c08-104">Syntax</span></span>  
  
```cpp  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44c08-105">参数</span><span class="sxs-lookup"><span data-stu-id="44c08-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="44c08-106">中要检查的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="44c08-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="44c08-107">弄指向 CorElementType 枚举的值的指针，该枚举指示数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="44c08-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="44c08-108">弄指向数组元素的类 ID 的指针（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="44c08-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="44c08-109">弄指向一个整数的指针，该整数指示数组的秩（即维度的数目）。</span><span class="sxs-lookup"><span data-stu-id="44c08-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44c08-110">备注</span><span class="sxs-lookup"><span data-stu-id="44c08-110">Remarks</span></span>  
 <span data-ttu-id="44c08-111">如果指定的类是一个数组类，则 `IsArrayClass` 方法为任何非 null output 参数返回 S_OK HRESULT 和值。</span><span class="sxs-lookup"><span data-stu-id="44c08-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="44c08-112">否则，它将返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="44c08-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c08-113">要求</span><span class="sxs-lookup"><span data-stu-id="44c08-113">Requirements</span></span>  
 <span data-ttu-id="44c08-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44c08-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c08-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44c08-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44c08-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44c08-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44c08-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c08-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c08-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44c08-118">See also</span></span>

- [<span data-ttu-id="44c08-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="44c08-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
