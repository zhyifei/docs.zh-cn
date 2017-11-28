---
title: "ICorProfilerInfo::IsArrayClass 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.IsArrayClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd07541095158d17b80333b83015d6b1f33a5dcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="4db92-102">ICorProfilerInfo::IsArrayClass 方法</span><span class="sxs-lookup"><span data-stu-id="4db92-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="4db92-103">确定指定的类是否是一个数组类。</span><span class="sxs-lookup"><span data-stu-id="4db92-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db92-104">语法</span><span class="sxs-lookup"><span data-stu-id="4db92-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4db92-105">参数</span><span class="sxs-lookup"><span data-stu-id="4db92-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="4db92-106">[in]要检查其类的 ID。</span><span class="sxs-lookup"><span data-stu-id="4db92-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="4db92-107">[out]指向 CorElementType 枚举，该值指示数组元素的类型的值的指针。</span><span class="sxs-lookup"><span data-stu-id="4db92-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="4db92-108">[out]指向数组元素，在可用时的类 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="4db92-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="4db92-109">[out]指向一个整数，指示该数组的秩 （也就是说，多个维度） 的指针。</span><span class="sxs-lookup"><span data-stu-id="4db92-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4db92-110">备注</span><span class="sxs-lookup"><span data-stu-id="4db92-110">Remarks</span></span>  
 <span data-ttu-id="4db92-111">如果指定的类是一个数组类、`IsArrayClass`方法返回，则为 S_OK HRESULT 和任何非 null 输出参数的值。</span><span class="sxs-lookup"><span data-stu-id="4db92-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="4db92-112">否则，它将返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="4db92-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4db92-113">要求</span><span class="sxs-lookup"><span data-stu-id="4db92-113">Requirements</span></span>  
 <span data-ttu-id="4db92-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4db92-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4db92-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4db92-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4db92-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4db92-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4db92-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4db92-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db92-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4db92-118">See Also</span></span>  
 [<span data-ttu-id="4db92-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="4db92-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
