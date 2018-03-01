---
title: "ICorProfilerInfo::GetModuleMetaData 方法"
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
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6ad52460bcd6eb320e970cd0ce2078f2e93df353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="a8462-102">ICorProfilerInfo::GetModuleMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="a8462-102">ICorProfilerInfo::GetModuleMetaData Method</span></span>
<span data-ttu-id="a8462-103">获取映射到指定的模块的元数据接口实例。</span><span class="sxs-lookup"><span data-stu-id="a8462-103">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8462-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8462-104">Syntax</span></span>  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8462-105">参数</span><span class="sxs-lookup"><span data-stu-id="a8462-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a8462-106">[in]接口实例将映射到模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="a8462-106">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="a8462-107">[in]值为[CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)指定打开清单文件的模式的枚举。</span><span class="sxs-lookup"><span data-stu-id="a8462-107">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="a8462-108">仅`ofRead`，`ofWrite`和`ofNoTransform`位均有效。</span><span class="sxs-lookup"><span data-stu-id="a8462-108">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="a8462-109">[in]引用的元数据接口将检索其实例的 ID (GUID)。</span><span class="sxs-lookup"><span data-stu-id="a8462-109">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="a8462-110">请参阅[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)的接口的列表。</span><span class="sxs-lookup"><span data-stu-id="a8462-110">See [Metadata Interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="a8462-111">[out]指向元数据接口实例的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a8462-111">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8462-112">备注</span><span class="sxs-lookup"><span data-stu-id="a8462-112">Remarks</span></span>  
 <span data-ttu-id="a8462-113">你可能会要求针对元数据要打开在读/写模式下，但这将导致该程序的执行速度变慢的元数据，因为对更改它们从编译器的不能优化元数据。</span><span class="sxs-lookup"><span data-stu-id="a8462-113">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="a8462-114">一些模块 （如资源模块） 具有任何元数据。</span><span class="sxs-lookup"><span data-stu-id="a8462-114">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="a8462-115">在这些情况下，`GetModuleMetaData`将返回的 HRESULT 值为 S_FALSE 和中的 null \*`ppOut`。</span><span class="sxs-lookup"><span data-stu-id="a8462-115">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in \*`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8462-116">惠?</span><span class="sxs-lookup"><span data-stu-id="a8462-116">Requirements</span></span>  
 <span data-ttu-id="a8462-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8462-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8462-118">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8462-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8462-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8462-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8462-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8462-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8462-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8462-121">See Also</span></span>  
 [<span data-ttu-id="a8462-122">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="a8462-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
