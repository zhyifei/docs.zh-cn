---
title: ICLRRuntimeInfo::LoadErrorString 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a565c19285b00c807ef6fbfc018a40467139638e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466344"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="a5376-102">ICLRRuntimeInfo::LoadErrorString 方法</span><span class="sxs-lookup"><span data-stu-id="a5376-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="a5376-103">HRESULT 值转换为相应的错误消息为指定的区域性。</span><span class="sxs-lookup"><span data-stu-id="a5376-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="a5376-104">此方法取代了以下函数：</span><span class="sxs-lookup"><span data-stu-id="a5376-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="a5376-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="a5376-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="a5376-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="a5376-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="a5376-107">语法</span><span class="sxs-lookup"><span data-stu-id="a5376-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5376-108">参数</span><span class="sxs-lookup"><span data-stu-id="a5376-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="a5376-109">[in]若要转换的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a5376-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="a5376-110">[out]给定的 HRESULT 与关联的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="a5376-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="a5376-111">[in、 out]大小`pwzbuffer`以避免缓冲区溢出。</span><span class="sxs-lookup"><span data-stu-id="a5376-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="a5376-112">如果`pwzbuffer`为 null，`pcchBuffer`提供的预期的大小`pwzbuffer`以允许预分配。</span><span class="sxs-lookup"><span data-stu-id="a5376-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="a5376-113">[in]区域性标识符。</span><span class="sxs-lookup"><span data-stu-id="a5376-113">[in] The culture identifier.</span></span> <span data-ttu-id="a5376-114">若要使用的默认区域性，必须指定-1。</span><span class="sxs-lookup"><span data-stu-id="a5376-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5376-115">返回值</span><span class="sxs-lookup"><span data-stu-id="a5376-115">Return Value</span></span>  
 <span data-ttu-id="a5376-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="a5376-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a5376-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5376-117">HRESULT</span></span>|<span data-ttu-id="a5376-118">描述</span><span class="sxs-lookup"><span data-stu-id="a5376-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5376-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5376-119">S_OK</span></span>|<span data-ttu-id="a5376-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="a5376-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="a5376-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a5376-121">E_POINTER</span></span>|<span data-ttu-id="a5376-122">`pcchBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="a5376-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="a5376-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a5376-123">E_INVALIDARG</span></span>|<span data-ttu-id="a5376-124">`pwzBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="a5376-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5376-125">要求</span><span class="sxs-lookup"><span data-stu-id="a5376-125">Requirements</span></span>  
 <span data-ttu-id="a5376-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5376-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5376-127">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a5376-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a5376-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a5376-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5376-129">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5376-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5376-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5376-130">See also</span></span>
- [<span data-ttu-id="a5376-131">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="a5376-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a5376-132">承载接口</span><span class="sxs-lookup"><span data-stu-id="a5376-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a5376-133">承载</span><span class="sxs-lookup"><span data-stu-id="a5376-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
