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
ms.openlocfilehash: 20f2041599e85b8df20a7a9cf44680da9f17244e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195932"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="894ad-102">ICLRRuntimeInfo::LoadErrorString 方法</span><span class="sxs-lookup"><span data-stu-id="894ad-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="894ad-103">将 HRESULT 值转换为指定区域性的适当错误消息。</span><span class="sxs-lookup"><span data-stu-id="894ad-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="894ad-104">此方法取代了以下函数：</span><span class="sxs-lookup"><span data-stu-id="894ad-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="894ad-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="894ad-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [<span data-ttu-id="894ad-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="894ad-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="894ad-107">语法</span><span class="sxs-lookup"><span data-stu-id="894ad-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="894ad-108">参数</span><span class="sxs-lookup"><span data-stu-id="894ad-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="894ad-109">中要转换的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="894ad-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="894ad-110">弄与给定的 HRESULT 关联的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="894ad-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="894ad-111">[in，out]用于避免缓冲区溢出的 `pwzbuffer` 大小。</span><span class="sxs-lookup"><span data-stu-id="894ad-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="894ad-112">如果 `pwzbuffer` 为 null，则 `pcchBuffer` 提供 `pwzbuffer` 允许预先分配的预期大小。</span><span class="sxs-lookup"><span data-stu-id="894ad-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="894ad-113">中区域性标识符。</span><span class="sxs-lookup"><span data-stu-id="894ad-113">[in] The culture identifier.</span></span> <span data-ttu-id="894ad-114">若要使用默认区域性，则必须指定-1。</span><span class="sxs-lookup"><span data-stu-id="894ad-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="894ad-115">返回值</span><span class="sxs-lookup"><span data-stu-id="894ad-115">Return Value</span></span>  
 <span data-ttu-id="894ad-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="894ad-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="894ad-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="894ad-117">HRESULT</span></span>|<span data-ttu-id="894ad-118">描述</span><span class="sxs-lookup"><span data-stu-id="894ad-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="894ad-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="894ad-119">S_OK</span></span>|<span data-ttu-id="894ad-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="894ad-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="894ad-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="894ad-121">E_POINTER</span></span>|<span data-ttu-id="894ad-122">`pcchBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="894ad-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="894ad-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="894ad-123">E_INVALIDARG</span></span>|<span data-ttu-id="894ad-124">`pwzBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="894ad-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="894ad-125">要求</span><span class="sxs-lookup"><span data-stu-id="894ad-125">Requirements</span></span>  
 <span data-ttu-id="894ad-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="894ad-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="894ad-127">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="894ad-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="894ad-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="894ad-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="894ad-129">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="894ad-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="894ad-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="894ad-130">See also</span></span>

- [<span data-ttu-id="894ad-131">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="894ad-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="894ad-132">承载接口</span><span class="sxs-lookup"><span data-stu-id="894ad-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="894ad-133">承载</span><span class="sxs-lookup"><span data-stu-id="894ad-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
