---
title: ICorProfilerInfo2::GetStaticFieldInfo 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0106b2dd1151e302c0082b306d999ab5a1c4322
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791633"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="f2fec-102">ICorProfilerInfo2::GetStaticFieldInfo 方法</span><span class="sxs-lookup"><span data-stu-id="f2fec-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="f2fec-103">获取一个值，指示将应用于指定的字段的静态类型。</span><span class="sxs-lookup"><span data-stu-id="f2fec-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2fec-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2fec-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2fec-105">参数</span><span class="sxs-lookup"><span data-stu-id="f2fec-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="f2fec-106">[in]在其中定义的静态字段的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="f2fec-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="f2fec-107">[in]静态字段的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f2fec-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="f2fec-108">[out]指向的值的指针[COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)枚举，指示指定的字段是否是静态的以及如果因此，静态类型，将应用于字段。</span><span class="sxs-lookup"><span data-stu-id="f2fec-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2fec-109">备注</span><span class="sxs-lookup"><span data-stu-id="f2fec-109">Remarks</span></span>  
 <span data-ttu-id="f2fec-110">此信息可以用于确定要获取静态字段的地址调用的函数。</span><span class="sxs-lookup"><span data-stu-id="f2fec-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="f2fec-111">探查器代码仍应检查以确保它实际上有一个地址的静态字段的元数据。</span><span class="sxs-lookup"><span data-stu-id="f2fec-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="f2fec-112">静态文本 （即，常数） 仅在元数据中存在，但没有一个地址。</span><span class="sxs-lookup"><span data-stu-id="f2fec-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2fec-113">要求</span><span class="sxs-lookup"><span data-stu-id="f2fec-113">Requirements</span></span>  
 <span data-ttu-id="f2fec-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2fec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2fec-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2fec-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2fec-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2fec-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2fec-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2fec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2fec-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2fec-118">See also</span></span>

- [<span data-ttu-id="f2fec-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="f2fec-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="f2fec-120">ICorProfilerInfo2 接口</span><span class="sxs-lookup"><span data-stu-id="f2fec-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
