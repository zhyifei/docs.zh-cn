---
title: "ICLRMetaHost::GetVersionFromFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetVersionFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61e6cd1c83cc369e06099c72a6012eb448d6d37a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="8905d-102">ICLRMetaHost::GetVersionFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="8905d-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="8905d-103">获取程序集的原始.NET Framework 编译版本 （存储在元数据），将给定文件路径。</span><span class="sxs-lookup"><span data-stu-id="8905d-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="8905d-104">此方法取代[GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="8905d-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8905d-105">语法</span><span class="sxs-lookup"><span data-stu-id="8905d-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8905d-106">参数</span><span class="sxs-lookup"><span data-stu-id="8905d-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="8905d-107">[in]完整的程序集文件路径。</span><span class="sxs-lookup"><span data-stu-id="8905d-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="8905d-108">[out]存储的元数据，采用格式中的.NET Framework 编译版本"v*A*。*B*[。*X*]"。</span><span class="sxs-lookup"><span data-stu-id="8905d-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="8905d-109">*A*， *B*，和*X*是对应于主版本、 次版本，以及内部版本号的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="8905d-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="8905d-110">此字符串的长度被限制为 MAX_PATH。</span><span class="sxs-lookup"><span data-stu-id="8905d-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8905d-111">为似乎在 C:\Windows\Microsoft.NET\Framework 下，此输出与匹配的.NET Framework 版本的目录名称。</span><span class="sxs-lookup"><span data-stu-id="8905d-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="8905d-112">示例值为"v1.0.3705"、"v1.1.4322"、"v2.0.50727"和"v4.0。*X*"，其中*X*取决于安装的内部版本号。</span><span class="sxs-lookup"><span data-stu-id="8905d-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="8905d-113">请注意，"v"前缀是必需的。</span><span class="sxs-lookup"><span data-stu-id="8905d-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="8905d-114">[在中，out]大小`pwzbuffer`以避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="8905d-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8905d-115">返回值</span><span class="sxs-lookup"><span data-stu-id="8905d-115">Return Value</span></span>  
 <span data-ttu-id="8905d-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="8905d-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8905d-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8905d-117">HRESULT</span></span>|<span data-ttu-id="8905d-118">描述</span><span class="sxs-lookup"><span data-stu-id="8905d-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8905d-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="8905d-119">S_OK</span></span>|<span data-ttu-id="8905d-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8905d-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="8905d-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8905d-121">E_POINTER</span></span>|<span data-ttu-id="8905d-122">`pwzbuffer` 或 `pcchBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="8905d-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="8905d-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="8905d-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="8905d-124">缓冲区而言太小。</span><span class="sxs-lookup"><span data-stu-id="8905d-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8905d-125">惠?</span><span class="sxs-lookup"><span data-stu-id="8905d-125">Requirements</span></span>  
 <span data-ttu-id="8905d-126">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8905d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8905d-127">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8905d-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8905d-128">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8905d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8905d-129">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8905d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8905d-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="8905d-130">See Also</span></span>  
 [<span data-ttu-id="8905d-131">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="8905d-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="8905d-132">承载</span><span class="sxs-lookup"><span data-stu-id="8905d-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
