---
title: "ICorProfilerInfo::GetAppDomainInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetAppDomainInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type: apiref
caps.latest.revision: "23"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9f7f4db595966293e87b5b115437df1bec56c00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a><span data-ttu-id="951c2-102">ICorProfilerInfo::GetAppDomainInfo 方法</span><span class="sxs-lookup"><span data-stu-id="951c2-102">ICorProfilerInfo::GetAppDomainInfo Method</span></span>
<span data-ttu-id="951c2-103">接受应用程序域 ID。</span><span class="sxs-lookup"><span data-stu-id="951c2-103">Accepts an application domain ID.</span></span> <span data-ttu-id="951c2-104">返回应用程序域名称和包含该域的进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="951c2-104">Returns an application domain name and the ID of the process that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951c2-105">语法</span><span class="sxs-lookup"><span data-stu-id="951c2-105">Syntax</span></span>  
  
```  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="951c2-106">参数</span><span class="sxs-lookup"><span data-stu-id="951c2-106">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="951c2-107">[in] 应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="951c2-107">[in] The ID of the application domain.</span></span>  
  
 `cchName`  
 <span data-ttu-id="951c2-108">[in] `szName` 返回缓冲区的长度（以字符为单位）。</span><span class="sxs-lookup"><span data-stu-id="951c2-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="951c2-109">[out] 指向应用程序域名称的总字符长度的指针。</span><span class="sxs-lookup"><span data-stu-id="951c2-109">[out] A pointer to the total character length of the application domain name.</span></span>  
  
 `szName`  
 <span data-ttu-id="951c2-110">[out] 调用方提供的宽字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="951c2-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="951c2-111">当方法返回时，`szName` 将包含整个或部分应用程序域名称。</span><span class="sxs-lookup"><span data-stu-id="951c2-111">When the method returns, `szName` will contain the full or partial application domain name.</span></span>  
  
 `pProcessId`  
 <span data-ttu-id="951c2-112">[out] 指向包含应用程序域的进程的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="951c2-112">[out] A pointer to the ID of the process that contains the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="951c2-113">备注</span><span class="sxs-lookup"><span data-stu-id="951c2-113">Remarks</span></span>  
 <span data-ttu-id="951c2-114">此方法返回后，必须验证 `szName` 缓冲区是否足够大从而可包含应用程序域的完整名称。</span><span class="sxs-lookup"><span data-stu-id="951c2-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the application domain.</span></span> <span data-ttu-id="951c2-115">为此，请比较 `pcchName` 指向的值和 `cchName` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="951c2-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="951c2-116">如果 `pcchName` 指向的值大于 `cchName`，请分配更大的 `szName` 缓冲区，并用新的、更大的大小更新 `cchName`，然后再次调用 `GetAppDomainInfo`。</span><span class="sxs-lookup"><span data-stu-id="951c2-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAppDomainInfo` again.</span></span>  
  
 <span data-ttu-id="951c2-117">或者，可先用长度为零的 `szName` 缓冲区调用 `GetAppDomainInfo` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="951c2-117">Alternatively, you can first call `GetAppDomainInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="951c2-118">然后，可将缓冲区大小设置为 `pcchName` 中返回的值，并再次调用 `GetAppDomainInfo`。</span><span class="sxs-lookup"><span data-stu-id="951c2-118">You can then set the buffer size to the value returned in `pcchName` and call `GetAppDomainInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="951c2-119">惠?</span><span class="sxs-lookup"><span data-stu-id="951c2-119">Requirements</span></span>  
 <span data-ttu-id="951c2-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="951c2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="951c2-121">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="951c2-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="951c2-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="951c2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="951c2-123">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="951c2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="951c2-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="951c2-124">See Also</span></span>  
 [<span data-ttu-id="951c2-125">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="951c2-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="951c2-126">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="951c2-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="951c2-127">分析</span><span class="sxs-lookup"><span data-stu-id="951c2-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
