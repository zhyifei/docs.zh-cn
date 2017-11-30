---
title: "ICorProfilerInfo2::GetBoxClassLayout 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetBoxClassLayout
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c11013781a4fc8f627dac97894ff9ef02bfda51c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="f3bf3-102">ICorProfilerInfo2::GetBoxClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="f3bf3-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="f3bf3-103">获取有关它进行装箱时指定的值类型所在的位置的信息。</span><span class="sxs-lookup"><span data-stu-id="f3bf3-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3bf3-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3bf3-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3bf3-105">参数</span><span class="sxs-lookup"><span data-stu-id="f3bf3-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="f3bf3-106">[in]类，用于描述进行装箱的值类型的 ID。</span><span class="sxs-lookup"><span data-stu-id="f3bf3-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="f3bf3-107">[out]一个整数，表示相对于值类型的装箱的对象 ID 指针的偏移量。</span><span class="sxs-lookup"><span data-stu-id="f3bf3-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3bf3-108">备注</span><span class="sxs-lookup"><span data-stu-id="f3bf3-108">Remarks</span></span>  
 <span data-ttu-id="f3bf3-109">`pBufferOffset`值为一个框中的值类型的位置。</span><span class="sxs-lookup"><span data-stu-id="f3bf3-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="f3bf3-110">后`pBufferOffset`应用到的已装箱对象的值类型的类布局可用于解释对象的值。</span><span class="sxs-lookup"><span data-stu-id="f3bf3-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3bf3-111">要求</span><span class="sxs-lookup"><span data-stu-id="f3bf3-111">Requirements</span></span>  
 <span data-ttu-id="f3bf3-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3bf3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3bf3-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3bf3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3bf3-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3bf3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3bf3-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3bf3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3bf3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3bf3-116">See Also</span></span>  
 [<span data-ttu-id="f3bf3-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="f3bf3-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="f3bf3-118">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="f3bf3-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
