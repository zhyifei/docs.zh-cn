---
title: "ICLRMetaHost::QueryLegacyV2RuntimeBinding 方法"
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
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 889d8ca00726c0b271a1d43519803af73018b2a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="50f1f-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding 方法</span><span class="sxs-lookup"><span data-stu-id="50f1f-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="50f1f-103">返回表示旧式激活策略具有已绑定到，例如，通过使用的运行时的接口`useLegacyV2RuntimeActivationPolicy`属性[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)配置文件项，直接使用通过旧激活 Api 或通过调用[iclrruntimeinfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="50f1f-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f1f-104">语法</span><span class="sxs-lookup"><span data-stu-id="50f1f-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50f1f-105">参数</span><span class="sxs-lookup"><span data-stu-id="50f1f-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="50f1f-106">[in]为此参数唯一有效的值是的 Required.Currently `IID_ICLRRuntimeInfo`。</span><span class="sxs-lookup"><span data-stu-id="50f1f-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="50f1f-107">[out] 必需。</span><span class="sxs-lookup"><span data-stu-id="50f1f-107">[out] Required.</span></span> <span data-ttu-id="50f1f-108">此方法返回时，包含指向的[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)表示已绑定到旧式激活策略的运行时的接口。</span><span class="sxs-lookup"><span data-stu-id="50f1f-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50f1f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="50f1f-109">Return Value</span></span>  
 <span data-ttu-id="50f1f-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="50f1f-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="50f1f-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50f1f-111">HRESULT</span></span>|<span data-ttu-id="50f1f-112">描述</span><span class="sxs-lookup"><span data-stu-id="50f1f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50f1f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="50f1f-113">S_OK</span></span>|<span data-ttu-id="50f1f-114">该方法已成功完成，并返回一个绑定到旧式激活策略的运行时。</span><span class="sxs-lookup"><span data-stu-id="50f1f-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="50f1f-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="50f1f-115">S_FALSE</span></span>|<span data-ttu-id="50f1f-116">该方法已成功完成，但尚未绑定旧式运行时。</span><span class="sxs-lookup"><span data-stu-id="50f1f-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="50f1f-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="50f1f-117">E_NOINTERFACE</span></span>|<span data-ttu-id="50f1f-118">该方法找到了绑定到旧式激活策略的运行时，但该运行时不支持 `riid`。</span><span class="sxs-lookup"><span data-stu-id="50f1f-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50f1f-119">备注</span><span class="sxs-lookup"><span data-stu-id="50f1f-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50f1f-120">惠?</span><span class="sxs-lookup"><span data-stu-id="50f1f-120">Requirements</span></span>  
 <span data-ttu-id="50f1f-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50f1f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50f1f-122">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="50f1f-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="50f1f-123">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="50f1f-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50f1f-124">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50f1f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f1f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="50f1f-125">See Also</span></span>  
 [<span data-ttu-id="50f1f-126">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="50f1f-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="50f1f-127">承载</span><span class="sxs-lookup"><span data-stu-id="50f1f-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
