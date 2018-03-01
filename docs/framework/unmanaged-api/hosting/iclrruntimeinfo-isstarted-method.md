---
title: "ICLRRuntimeInfo::IsStarted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 991470ca0df3e0cf0470a8c40d3e8e4c40d96026
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="13114-102">ICLRRuntimeInfo::IsStarted 方法</span><span class="sxs-lookup"><span data-stu-id="13114-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="13114-103">该值指示是否已启动运行时 (即，是否[iclrruntimehost:: Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)已调用并已成功)。</span><span class="sxs-lookup"><span data-stu-id="13114-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13114-104">语法</span><span class="sxs-lookup"><span data-stu-id="13114-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13114-105">参数</span><span class="sxs-lookup"><span data-stu-id="13114-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="13114-106">[out]`true`此运行时是否已启动; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="13114-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="13114-107">[out]返回用来启动运行时的标志。</span><span class="sxs-lookup"><span data-stu-id="13114-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13114-108">返回值</span><span class="sxs-lookup"><span data-stu-id="13114-108">Return Value</span></span>  
 <span data-ttu-id="13114-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="13114-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="13114-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13114-110">HRESULT</span></span>|<span data-ttu-id="13114-111">描述</span><span class="sxs-lookup"><span data-stu-id="13114-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13114-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="13114-112">S_OK</span></span>|<span data-ttu-id="13114-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="13114-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="13114-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="13114-114">E_NOTIMPL</span></span>|<span data-ttu-id="13114-115">公共语言运行时 (CLR) 版本低于中的 CLR 版本[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="13114-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13114-116">备注</span><span class="sxs-lookup"><span data-stu-id="13114-116">Remarks</span></span>  
 <span data-ttu-id="13114-117">此方法不起使用 CLR 版本早于中的 CLR 版本[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="13114-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13114-118">惠?</span><span class="sxs-lookup"><span data-stu-id="13114-118">Requirements</span></span>  
 <span data-ttu-id="13114-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13114-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13114-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="13114-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="13114-121">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="13114-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13114-122">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13114-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13114-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="13114-123">See Also</span></span>  
 [<span data-ttu-id="13114-124">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="13114-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="13114-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="13114-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="13114-126">承载</span><span class="sxs-lookup"><span data-stu-id="13114-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
