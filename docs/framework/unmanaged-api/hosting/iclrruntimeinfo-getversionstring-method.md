---
title: ICLRRuntimeInfo::GetVersionString 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: ccf48b6aea25bd602b55727c2e5958811702f6bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762573"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="7b9b7-102">ICLRRuntimeInfo::GetVersionString 方法</span><span class="sxs-lookup"><span data-stu-id="7b9b7-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="7b9b7-103">获取与给定的[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)接口相关联的公共语言运行时（CLR）版本信息。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="7b9b7-104">此方法取代了以下函数：</span><span class="sxs-lookup"><span data-stu-id="7b9b7-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="7b9b7-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="7b9b7-105">GetRequestedRuntimeInfo</span></span>](getrequestedruntimeinfo-function.md)  
  
- [<span data-ttu-id="7b9b7-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="7b9b7-106">GetRequestedRuntimeVersion</span></span>](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="7b9b7-107">语法</span><span class="sxs-lookup"><span data-stu-id="7b9b7-107">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b9b7-108">参数</span><span class="sxs-lookup"><span data-stu-id="7b9b7-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="7b9b7-109">弄"V*A*" 格式的 .NET Framework 编译版本。*B.*[。*X*] "。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="7b9b7-110">*A*、 *B*和*X*是与主版本、次版本和生成号对应的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="7b9b7-111">*X*是可选的。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-111">*X* is optional.</span></span> <span data-ttu-id="7b9b7-112">如果*X*不存在，则没有尾随句点。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b9b7-113">此参数必须匹配 .NET Framework 版本的目录名称，因为它显示在 C:\Windows\Microsoft.NET\Framework. 下。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="7b9b7-114">示例值为 "v1.0.3705"、"v 1.1.4322"、"v 2.0.50727" 和 "v4.0"。*x*"，其中*x*依赖于安装的生成号。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="7b9b7-115">请注意，"v" 前缀是必需的。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="7b9b7-116">[in，out]指定的大小 `pwzBuffer` 以避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="7b9b7-117">如果 `pwzBuffer` 为 `null` ，则 `pchBuffer` 返回所需的大小 `pwzBuffer` 以允许预先分配。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b9b7-118">返回值</span><span class="sxs-lookup"><span data-stu-id="7b9b7-118">Return Value</span></span>  
 <span data-ttu-id="7b9b7-119">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7b9b7-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7b9b7-120">HRESULT</span></span>|<span data-ttu-id="7b9b7-121">说明</span><span class="sxs-lookup"><span data-stu-id="7b9b7-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b9b7-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b9b7-122">S_OK</span></span>|<span data-ttu-id="7b9b7-123">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="7b9b7-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7b9b7-124">E_POINTER</span></span>|<span data-ttu-id="7b9b7-125">`pwzBuffer` 或 `pchBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7b9b7-126">要求</span><span class="sxs-lookup"><span data-stu-id="7b9b7-126">Requirements</span></span>  
 <span data-ttu-id="7b9b7-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b9b7-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b9b7-128">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="7b9b7-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7b9b7-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7b9b7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b9b7-130">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b9b7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b9b7-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b9b7-131">See also</span></span>

- [<span data-ttu-id="7b9b7-132">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="7b9b7-132">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7b9b7-133">承载接口</span><span class="sxs-lookup"><span data-stu-id="7b9b7-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="7b9b7-134">.NET Framework 4 和 4.5 中添加的 CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="7b9b7-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="7b9b7-135">承载</span><span class="sxs-lookup"><span data-stu-id="7b9b7-135">Hosting</span></span>](index.md)
