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
ms.openlocfilehash: 193cbf3fe7ba99a70039c11983c6a203337290eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453680"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="72066-102">ICorProfilerInfo::GetClassIDInfo 方法</span><span class="sxs-lookup"><span data-stu-id="72066-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="72066-103">获取指定的类的父模块和元数据标记。</span><span class="sxs-lookup"><span data-stu-id="72066-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72066-104">语法</span><span class="sxs-lookup"><span data-stu-id="72066-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="72066-105">参数</span><span class="sxs-lookup"><span data-stu-id="72066-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="72066-106">[in]要为其获取信息的类 ID。</span><span class="sxs-lookup"><span data-stu-id="72066-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="72066-107">[out]指向类的父模块 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="72066-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="72066-108">[out]指向类的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="72066-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72066-109">备注</span><span class="sxs-lookup"><span data-stu-id="72066-109">Remarks</span></span>  
 <span data-ttu-id="72066-110">探查器代码可以调用[icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)以获取给定模块的元数据接口。</span><span class="sxs-lookup"><span data-stu-id="72066-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="72066-111">返回至 `pTypeDefToken` 所引用的位置的元数据标记可用于访问类的元数据。</span><span class="sxs-lookup"><span data-stu-id="72066-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="72066-112">若要获取泛型类型的详细信息，请使用[icorprofilerinfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)。</span><span class="sxs-lookup"><span data-stu-id="72066-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72066-113">要求</span><span class="sxs-lookup"><span data-stu-id="72066-113">Requirements</span></span>  
 <span data-ttu-id="72066-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72066-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72066-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72066-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72066-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72066-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72066-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72066-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72066-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="72066-118">See Also</span></span>  
 [<span data-ttu-id="72066-119">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="72066-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
