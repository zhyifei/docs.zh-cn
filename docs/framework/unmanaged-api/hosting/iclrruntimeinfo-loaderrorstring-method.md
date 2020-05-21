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
ms.openlocfilehash: da6efae38cd70a68feea56b12e86be23fde7f0cb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762183"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="09783-102">ICLRRuntimeInfo::LoadErrorString 方法</span><span class="sxs-lookup"><span data-stu-id="09783-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="09783-103">将 HRESULT 值转换为指定区域性的适当错误消息。</span><span class="sxs-lookup"><span data-stu-id="09783-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="09783-104">此方法取代了以下函数：</span><span class="sxs-lookup"><span data-stu-id="09783-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="09783-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="09783-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="09783-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="09783-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="09783-107">语法</span><span class="sxs-lookup"><span data-stu-id="09783-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09783-108">参数</span><span class="sxs-lookup"><span data-stu-id="09783-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="09783-109">中要转换的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="09783-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="09783-110">弄与给定的 HRESULT 关联的消息字符串。</span><span class="sxs-lookup"><span data-stu-id="09783-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="09783-111">[in，out]`pwzbuffer`用于避免缓冲区溢出的的大小。</span><span class="sxs-lookup"><span data-stu-id="09783-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="09783-112">如果 `pwzbuffer` 为 null，则 `pcchBuffer` 提供的预期大小 `pwzbuffer` 允许预先分配。</span><span class="sxs-lookup"><span data-stu-id="09783-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="09783-113">中区域性标识符。</span><span class="sxs-lookup"><span data-stu-id="09783-113">[in] The culture identifier.</span></span> <span data-ttu-id="09783-114">若要使用默认区域性，则必须指定-1。</span><span class="sxs-lookup"><span data-stu-id="09783-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09783-115">返回值</span><span class="sxs-lookup"><span data-stu-id="09783-115">Return Value</span></span>  
 <span data-ttu-id="09783-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="09783-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="09783-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09783-117">HRESULT</span></span>|<span data-ttu-id="09783-118">说明</span><span class="sxs-lookup"><span data-stu-id="09783-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09783-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="09783-119">S_OK</span></span>|<span data-ttu-id="09783-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="09783-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="09783-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="09783-121">E_POINTER</span></span>|<span data-ttu-id="09783-122">`pcchBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="09783-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="09783-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="09783-123">E_INVALIDARG</span></span>|<span data-ttu-id="09783-124">`pwzBuffer` 为 null。</span><span class="sxs-lookup"><span data-stu-id="09783-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09783-125">要求</span><span class="sxs-lookup"><span data-stu-id="09783-125">Requirements</span></span>  
 <span data-ttu-id="09783-126">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09783-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09783-127">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="09783-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="09783-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="09783-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09783-129">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09783-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09783-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09783-130">See also</span></span>

- [<span data-ttu-id="09783-131">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="09783-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="09783-132">承载接口</span><span class="sxs-lookup"><span data-stu-id="09783-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="09783-133">承载</span><span class="sxs-lookup"><span data-stu-id="09783-133">Hosting</span></span>](index.md)
