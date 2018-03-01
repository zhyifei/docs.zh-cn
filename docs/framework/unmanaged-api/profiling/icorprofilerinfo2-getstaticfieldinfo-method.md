---
title: "ICorProfilerInfo2::GetStaticFieldInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8a13a07aeb90d7ad05ca83bf273fe999b9a81bd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="d7f9c-102">ICorProfilerInfo2::GetStaticFieldInfo 方法</span><span class="sxs-lookup"><span data-stu-id="d7f9c-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="d7f9c-103">获取一个值，该值指示的将应用到指定的字段的静态类型。</span><span class="sxs-lookup"><span data-stu-id="d7f9c-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f9c-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7f9c-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7f9c-105">参数</span><span class="sxs-lookup"><span data-stu-id="d7f9c-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="d7f9c-106">[in]在其中定义的静态字段的类 ID。</span><span class="sxs-lookup"><span data-stu-id="d7f9c-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="d7f9c-107">[in]静态字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d7f9c-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="d7f9c-108">[out]指向的值的指针[COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)枚举，指示是否指定的字段为静态，和如果因此，静态的种类，它将应用于字段。</span><span class="sxs-lookup"><span data-stu-id="d7f9c-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7f9c-109">备注</span><span class="sxs-lookup"><span data-stu-id="d7f9c-109">Remarks</span></span>  
 <span data-ttu-id="d7f9c-110">此信息可以用于确定哪一个函数调用以获取静态字段的地址。</span><span class="sxs-lookup"><span data-stu-id="d7f9c-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="d7f9c-111">探查器代码仍应检查以确保它确实拥有一个地址的静态字段的元数据。</span><span class="sxs-lookup"><span data-stu-id="d7f9c-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="d7f9c-112">静态文本 （即，常量） 仅在元数据中存在，但没有一个地址。</span><span class="sxs-lookup"><span data-stu-id="d7f9c-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f9c-113">惠?</span><span class="sxs-lookup"><span data-stu-id="d7f9c-113">Requirements</span></span>  
 <span data-ttu-id="d7f9c-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f9c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f9c-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7f9c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7f9c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7f9c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7f9c-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f9c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f9c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7f9c-118">See Also</span></span>  
 [<span data-ttu-id="d7f9c-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="d7f9c-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="d7f9c-120">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="d7f9c-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
