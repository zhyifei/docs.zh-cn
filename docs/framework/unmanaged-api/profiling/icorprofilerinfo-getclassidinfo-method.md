---
title: ICorProfilerInfo::GetClassIDInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 30c57130c2ea504cc94cfed9cdf99077b9a897f0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492941"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="8347d-102">ICorProfilerInfo::GetClassIDInfo 方法</span><span class="sxs-lookup"><span data-stu-id="8347d-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="8347d-103">获取指定的类的父模块和元数据标记。</span><span class="sxs-lookup"><span data-stu-id="8347d-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8347d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8347d-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8347d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8347d-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="8347d-106">[in]若要获取的信息的类的 ID。</span><span class="sxs-lookup"><span data-stu-id="8347d-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="8347d-107">[out]指向类的父模块 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="8347d-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="8347d-108">[out]指向类的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="8347d-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8347d-109">备注</span><span class="sxs-lookup"><span data-stu-id="8347d-109">Remarks</span></span>  
 <span data-ttu-id="8347d-110">探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)以获取给定模块的元数据接口。</span><span class="sxs-lookup"><span data-stu-id="8347d-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="8347d-111">返回至 `pTypeDefToken` 所引用的位置的元数据标记可用于访问类的元数据。</span><span class="sxs-lookup"><span data-stu-id="8347d-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="8347d-112">若要获取泛型类型的详细信息，请使用[ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)。</span><span class="sxs-lookup"><span data-stu-id="8347d-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8347d-113">要求</span><span class="sxs-lookup"><span data-stu-id="8347d-113">Requirements</span></span>  
 <span data-ttu-id="8347d-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8347d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8347d-115">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8347d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8347d-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8347d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8347d-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8347d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8347d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="8347d-118">See also</span></span>
- [<span data-ttu-id="8347d-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="8347d-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
