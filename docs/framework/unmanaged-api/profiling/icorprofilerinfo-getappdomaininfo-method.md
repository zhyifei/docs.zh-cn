---
title: ICorProfilerInfo::GetAppDomainInfo 方法
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83468e13e1e028b031c31791910c4dd2d792f232
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992116"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a><span data-ttu-id="9126a-102">ICorProfilerInfo::GetAppDomainInfo 方法</span><span class="sxs-lookup"><span data-stu-id="9126a-102">ICorProfilerInfo::GetAppDomainInfo Method</span></span>
<span data-ttu-id="9126a-103">接受应用程序域 ID。</span><span class="sxs-lookup"><span data-stu-id="9126a-103">Accepts an application domain ID.</span></span> <span data-ttu-id="9126a-104">返回应用程序域名称和包含该域的进程的 ID。</span><span class="sxs-lookup"><span data-stu-id="9126a-104">Returns an application domain name and the ID of the process that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9126a-105">语法</span><span class="sxs-lookup"><span data-stu-id="9126a-105">Syntax</span></span>  
  
```  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9126a-106">参数</span><span class="sxs-lookup"><span data-stu-id="9126a-106">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="9126a-107">[in] 应用程序域的 ID。</span><span class="sxs-lookup"><span data-stu-id="9126a-107">[in] The ID of the application domain.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9126a-108">[in] `szName` 返回缓冲区的长度（以字符为单位）。</span><span class="sxs-lookup"><span data-stu-id="9126a-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9126a-109">[out] 指向应用程序域名称的总字符长度的指针。</span><span class="sxs-lookup"><span data-stu-id="9126a-109">[out] A pointer to the total character length of the application domain name.</span></span>  
  
 `szName`  
 <span data-ttu-id="9126a-110">[out] 调用方提供的宽字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9126a-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="9126a-111">当方法返回时，`szName` 将包含整个或部分应用程序域名称。</span><span class="sxs-lookup"><span data-stu-id="9126a-111">When the method returns, `szName` will contain the full or partial application domain name.</span></span>  
  
 `pProcessId`  
 <span data-ttu-id="9126a-112">[out] 指向包含应用程序域的进程的 ID 的指针。</span><span class="sxs-lookup"><span data-stu-id="9126a-112">[out] A pointer to the ID of the process that contains the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9126a-113">备注</span><span class="sxs-lookup"><span data-stu-id="9126a-113">Remarks</span></span>  
 <span data-ttu-id="9126a-114">此方法返回后，必须验证 `szName` 缓冲区是否足够大从而可包含应用程序域的完整名称。</span><span class="sxs-lookup"><span data-stu-id="9126a-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the application domain.</span></span> <span data-ttu-id="9126a-115">为此，请比较 `pcchName` 指向的值和 `cchName` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="9126a-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="9126a-116">如果 `pcchName` 指向的值大于 `cchName`，请分配更大的 `szName` 缓冲区，并用新的、更大的大小更新 `cchName`，然后再次调用 `GetAppDomainInfo`。</span><span class="sxs-lookup"><span data-stu-id="9126a-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAppDomainInfo` again.</span></span>  
  
 <span data-ttu-id="9126a-117">或者，可以先用长度为零的 `szName` 缓冲区调用 `GetAppDomainInfo` 以获取正确的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="9126a-117">Alternatively, you can first call `GetAppDomainInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="9126a-118">然后，可将缓冲区大小设置为 `pcchName` 中返回的值，并再次调用 `GetAppDomainInfo`。</span><span class="sxs-lookup"><span data-stu-id="9126a-118">You can then set the buffer size to the value returned in `pcchName` and call `GetAppDomainInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9126a-119">要求</span><span class="sxs-lookup"><span data-stu-id="9126a-119">Requirements</span></span>  
 <span data-ttu-id="9126a-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9126a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9126a-121">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9126a-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9126a-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9126a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9126a-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9126a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9126a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="9126a-124">See also</span></span>

- [<span data-ttu-id="9126a-125">ICorProfilerInfo 接口</span><span class="sxs-lookup"><span data-stu-id="9126a-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="9126a-126">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="9126a-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="9126a-127">分析</span><span class="sxs-lookup"><span data-stu-id="9126a-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
