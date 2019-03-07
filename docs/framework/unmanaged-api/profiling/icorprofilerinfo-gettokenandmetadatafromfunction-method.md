---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fb81972a7f52889d10a59cd5cd9ea0e8e1e3e571
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492876"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="e3b63-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction 方法</span><span class="sxs-lookup"><span data-stu-id="e3b63-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="e3b63-103">获取元数据标记和可用于指定的函数对令牌的元数据接口实例。</span><span class="sxs-lookup"><span data-stu-id="e3b63-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b63-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3b63-104">Syntax</span></span>  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3b63-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3b63-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e3b63-106">[in]要为其获取元数据标记和元数据接口的函数的 ID。</span><span class="sxs-lookup"><span data-stu-id="e3b63-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="e3b63-107">[in]要获取的实例元数据接口的引用 ID。</span><span class="sxs-lookup"><span data-stu-id="e3b63-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="e3b63-108">[out]指向可用于指定的函数对令牌的元数据接口实例的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e3b63-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="e3b63-109">[out]指向指定函数的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="e3b63-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3b63-110">要求</span><span class="sxs-lookup"><span data-stu-id="e3b63-110">Requirements</span></span>  
 <span data-ttu-id="e3b63-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3b63-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3b63-112">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3b63-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3b63-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3b63-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3b63-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3b63-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b63-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3b63-115">See also</span></span>
- [<span data-ttu-id="e3b63-116">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="e3b63-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
