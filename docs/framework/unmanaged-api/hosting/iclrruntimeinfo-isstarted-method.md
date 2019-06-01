---
title: ICLRRuntimeInfo::IsStarted 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b09c509c3e0ba941a34f60ff522117ff30d83caf
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457390"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="58201-102">ICLRRuntimeInfo::IsStarted 方法</span><span class="sxs-lookup"><span data-stu-id="58201-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="58201-103">指示是否已启动运行时 (即，是否[iclrruntimehost:: Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)已调用并已成功)。</span><span class="sxs-lookup"><span data-stu-id="58201-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58201-104">语法</span><span class="sxs-lookup"><span data-stu-id="58201-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58201-105">参数</span><span class="sxs-lookup"><span data-stu-id="58201-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="58201-106">[out]`true`如果此运行时已启动; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="58201-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="58201-107">[out]返回用来启动运行时的标志。</span><span class="sxs-lookup"><span data-stu-id="58201-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58201-108">返回值</span><span class="sxs-lookup"><span data-stu-id="58201-108">Return Value</span></span>  
 <span data-ttu-id="58201-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="58201-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="58201-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58201-110">HRESULT</span></span>|<span data-ttu-id="58201-111">描述</span><span class="sxs-lookup"><span data-stu-id="58201-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="58201-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="58201-112">S_OK</span></span>|<span data-ttu-id="58201-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="58201-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="58201-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="58201-114">E_NOTIMPL</span></span>|<span data-ttu-id="58201-115">公共语言运行时 (CLR) 版本低于中的 CLR 版本[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="58201-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58201-116">备注</span><span class="sxs-lookup"><span data-stu-id="58201-116">Remarks</span></span>  
 <span data-ttu-id="58201-117">此方法并不适用于 CLR 版本早于.NET Framework 4 中的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="58201-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58201-118">要求</span><span class="sxs-lookup"><span data-stu-id="58201-118">Requirements</span></span>  
 <span data-ttu-id="58201-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58201-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58201-120">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="58201-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="58201-121">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="58201-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58201-122">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58201-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58201-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="58201-123">See also</span></span>

- [<span data-ttu-id="58201-124">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="58201-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="58201-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="58201-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="58201-126">承载</span><span class="sxs-lookup"><span data-stu-id="58201-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
