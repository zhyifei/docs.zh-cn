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
ms.openlocfilehash: 34590744407b25d7d53c06c452fff5bac2a95246
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136388"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="8c661-102">ICLRRuntimeInfo::IsStarted 方法</span><span class="sxs-lookup"><span data-stu-id="8c661-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="8c661-103">指示运行时是否已启动（即是否已调用[ICLRRuntimeHost：： Start 方法](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)并且已成功）。</span><span class="sxs-lookup"><span data-stu-id="8c661-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c661-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c661-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c661-105">参数</span><span class="sxs-lookup"><span data-stu-id="8c661-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="8c661-106">[out] 如果此运行时已启动，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="8c661-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="8c661-107">弄返回用于启动运行时的标志。</span><span class="sxs-lookup"><span data-stu-id="8c661-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c661-108">返回值</span><span class="sxs-lookup"><span data-stu-id="8c661-108">Return Value</span></span>  
 <span data-ttu-id="8c661-109">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="8c661-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8c661-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c661-110">HRESULT</span></span>|<span data-ttu-id="8c661-111">描述</span><span class="sxs-lookup"><span data-stu-id="8c661-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c661-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c661-112">S_OK</span></span>|<span data-ttu-id="8c661-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8c661-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="8c661-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8c661-114">E_NOTIMPL</span></span>|<span data-ttu-id="8c661-115">公共语言运行时（CLR）的版本早于 .NET Framework 4 的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="8c661-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c661-116">备注</span><span class="sxs-lookup"><span data-stu-id="8c661-116">Remarks</span></span>  
 <span data-ttu-id="8c661-117">此方法不适用于 CLR 版本早于 .NET Framework 4 的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="8c661-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c661-118">要求</span><span class="sxs-lookup"><span data-stu-id="8c661-118">Requirements</span></span>  
 <span data-ttu-id="8c661-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c661-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c661-120">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="8c661-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8c661-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8c661-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c661-122">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c661-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c661-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c661-123">See also</span></span>

- [<span data-ttu-id="8c661-124">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="8c661-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="8c661-125">承载接口</span><span class="sxs-lookup"><span data-stu-id="8c661-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="8c661-126">承载</span><span class="sxs-lookup"><span data-stu-id="8c661-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
