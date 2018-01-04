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
ms.workload: dotnet
ms.openlocfilehash: 9ef6df997a4ba4369b87789e47ac7ead2206162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="d4460-102">ICorProfilerInfo2::GetBoxClassLayout 方法</span><span class="sxs-lookup"><span data-stu-id="d4460-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>
<span data-ttu-id="d4460-103">获取有关它进行装箱时指定的值类型所在的位置的信息。</span><span class="sxs-lookup"><span data-stu-id="d4460-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4460-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4460-104">Syntax</span></span>  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4460-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4460-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="d4460-106">[in]类，用于描述进行装箱的值类型的 ID。</span><span class="sxs-lookup"><span data-stu-id="d4460-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="d4460-107">[out]一个整数，表示相对于值类型的装箱的对象 ID 指针的偏移量。</span><span class="sxs-lookup"><span data-stu-id="d4460-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4460-108">备注</span><span class="sxs-lookup"><span data-stu-id="d4460-108">Remarks</span></span>  
 <span data-ttu-id="d4460-109">`pBufferOffset`值为一个框中的值类型的位置。</span><span class="sxs-lookup"><span data-stu-id="d4460-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="d4460-110">后`pBufferOffset`应用到的已装箱对象的值类型的类布局可用于解释对象的值。</span><span class="sxs-lookup"><span data-stu-id="d4460-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4460-111">惠?</span><span class="sxs-lookup"><span data-stu-id="d4460-111">Requirements</span></span>  
 <span data-ttu-id="d4460-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4460-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4460-113">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d4460-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d4460-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4460-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4460-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4460-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4460-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4460-116">See Also</span></span>  
 [<span data-ttu-id="d4460-117">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="d4460-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="d4460-118">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="d4460-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
