---
title: ICorProfilerInfo3::GetAppDomainsContainingModule 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b5658ac87c7a938381639442216df03853f02998
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195782"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="4ae89-102">ICorProfilerInfo3::GetAppDomainsContainingModule 方法</span><span class="sxs-lookup"><span data-stu-id="4ae89-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="4ae89-103">获取其中已加载给定模块的应用程序域的标识符。</span><span class="sxs-lookup"><span data-stu-id="4ae89-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ae89-104">语法</span><span class="sxs-lookup"><span data-stu-id="4ae89-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ae89-105">参数</span><span class="sxs-lookup"><span data-stu-id="4ae89-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4ae89-106">[in] 已加载模块的 ID。</span><span class="sxs-lookup"><span data-stu-id="4ae89-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="4ae89-107">[in] `appDomainIds` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="4ae89-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="4ae89-108">[out] 指向所返回元素总数的指针。</span><span class="sxs-lookup"><span data-stu-id="4ae89-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="4ae89-109">[out] 应用程序域 ID 值的数组。</span><span class="sxs-lookup"><span data-stu-id="4ae89-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ae89-110">备注</span><span class="sxs-lookup"><span data-stu-id="4ae89-110">Remarks</span></span>  
 <span data-ttu-id="4ae89-111">此方法使用调用方分配的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4ae89-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ae89-112">要求</span><span class="sxs-lookup"><span data-stu-id="4ae89-112">Requirements</span></span>  
 <span data-ttu-id="4ae89-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4ae89-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ae89-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ae89-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ae89-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ae89-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4ae89-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="4ae89-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4ae89-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ae89-117">See also</span></span>

- [<span data-ttu-id="4ae89-118">ICorProfilerFunctionEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4ae89-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="4ae89-119">ICorProfilerInfo3 接口</span><span class="sxs-lookup"><span data-stu-id="4ae89-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="4ae89-120">分析接口</span><span class="sxs-lookup"><span data-stu-id="4ae89-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4ae89-121">分析</span><span class="sxs-lookup"><span data-stu-id="4ae89-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
