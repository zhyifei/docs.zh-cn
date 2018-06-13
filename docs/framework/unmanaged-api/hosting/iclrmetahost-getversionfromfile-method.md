---
title: ICLRMetaHost::GetVersionFromFile 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 538e596c3a705020150f52c9e55605a49434ce8f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434046"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="54d02-102">ICLRMetaHost::GetVersionFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="54d02-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="54d02-103">获取程序集的原始.NET Framework 编译版本 （存储在元数据），将给定文件路径。</span><span class="sxs-lookup"><span data-stu-id="54d02-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="54d02-104">此方法取代[GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="54d02-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d02-105">语法</span><span class="sxs-lookup"><span data-stu-id="54d02-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54d02-106">参数</span><span class="sxs-lookup"><span data-stu-id="54d02-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="54d02-107">[in]完整的程序集文件路径。</span><span class="sxs-lookup"><span data-stu-id="54d02-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="54d02-108">[out]存储的元数据，采用格式中的.NET Framework 编译版本"v*A*。*B*[。*X*]"。</span><span class="sxs-lookup"><span data-stu-id="54d02-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="54d02-109">*A*， *B*，和*X*是对应于主版本、 次版本，以及内部版本号的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="54d02-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="54d02-110">此字符串的长度被限制为 MAX_PATH。</span><span class="sxs-lookup"><span data-stu-id="54d02-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54d02-111">为似乎在 C:\Windows\Microsoft.NET\Framework 下，此输出与匹配的.NET Framework 版本的目录名称。</span><span class="sxs-lookup"><span data-stu-id="54d02-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="54d02-112">示例值为"v1.0.3705"、"v1.1.4322"、"v2.0.50727"和"v4.0。*X*"，其中*X*取决于安装的内部版本号。</span><span class="sxs-lookup"><span data-stu-id="54d02-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="54d02-113">请注意，"v"前缀是必需的。</span><span class="sxs-lookup"><span data-stu-id="54d02-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="54d02-114">[在中，out]大小`pwzbuffer`以避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="54d02-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54d02-115">返回值</span><span class="sxs-lookup"><span data-stu-id="54d02-115">Return Value</span></span>  
 <span data-ttu-id="54d02-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="54d02-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="54d02-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="54d02-117">HRESULT</span></span>|<span data-ttu-id="54d02-118">描述</span><span class="sxs-lookup"><span data-stu-id="54d02-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="54d02-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="54d02-119">S_OK</span></span>|<span data-ttu-id="54d02-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="54d02-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="54d02-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="54d02-121">E_POINTER</span></span>|<span data-ttu-id="54d02-122">`pwzbuffer` 或 `pcchBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="54d02-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="54d02-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="54d02-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="54d02-124">缓冲区而言太小。</span><span class="sxs-lookup"><span data-stu-id="54d02-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="54d02-125">要求</span><span class="sxs-lookup"><span data-stu-id="54d02-125">Requirements</span></span>  
 <span data-ttu-id="54d02-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54d02-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54d02-127">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="54d02-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="54d02-128">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="54d02-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54d02-129">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54d02-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d02-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="54d02-130">See Also</span></span>  
 [<span data-ttu-id="54d02-131">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="54d02-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="54d02-132">承载</span><span class="sxs-lookup"><span data-stu-id="54d02-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
