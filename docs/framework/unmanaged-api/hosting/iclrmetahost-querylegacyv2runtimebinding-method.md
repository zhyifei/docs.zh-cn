---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0252f27f30c3ce8abe349a2ddc45b20692fbb5ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993182"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="3036b-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding 方法</span><span class="sxs-lookup"><span data-stu-id="3036b-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="3036b-103">返回表示旧式激活策略具有已绑定到，例如，使用的运行时的接口`useLegacyV2RuntimeActivationPolicy`特性，可以在[\<启动 > 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)直接使用配置文件条目旧激活 Api 或通过调用[ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3036b-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3036b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3036b-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3036b-105">参数</span><span class="sxs-lookup"><span data-stu-id="3036b-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="3036b-106">[in]此参数的唯一有效的值是的 Required.Currently `IID_ICLRRuntimeInfo`。</span><span class="sxs-lookup"><span data-stu-id="3036b-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="3036b-107">[out] 必需。</span><span class="sxs-lookup"><span data-stu-id="3036b-107">[out] Required.</span></span> <span data-ttu-id="3036b-108">此方法返回时，包含一个指向[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)表示已绑定到旧式激活策略的运行时的接口。</span><span class="sxs-lookup"><span data-stu-id="3036b-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3036b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="3036b-109">Return Value</span></span>  
 <span data-ttu-id="3036b-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="3036b-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3036b-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3036b-111">HRESULT</span></span>|<span data-ttu-id="3036b-112">描述</span><span class="sxs-lookup"><span data-stu-id="3036b-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3036b-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3036b-113">S_OK</span></span>|<span data-ttu-id="3036b-114">该方法已成功完成，并返回一个绑定到旧式激活策略的运行时。</span><span class="sxs-lookup"><span data-stu-id="3036b-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="3036b-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3036b-115">S_FALSE</span></span>|<span data-ttu-id="3036b-116">该方法已成功完成，但尚未绑定旧式运行时。</span><span class="sxs-lookup"><span data-stu-id="3036b-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="3036b-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="3036b-117">E_NOINTERFACE</span></span>|<span data-ttu-id="3036b-118">该方法找到了绑定到旧式激活策略的运行时，但该运行时不支持 `riid`。</span><span class="sxs-lookup"><span data-stu-id="3036b-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3036b-119">备注</span><span class="sxs-lookup"><span data-stu-id="3036b-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3036b-120">要求</span><span class="sxs-lookup"><span data-stu-id="3036b-120">Requirements</span></span>  
 <span data-ttu-id="3036b-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3036b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3036b-122">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3036b-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3036b-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3036b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3036b-124">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3036b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3036b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3036b-125">See also</span></span>

- [<span data-ttu-id="3036b-126">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="3036b-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="3036b-127">承载</span><span class="sxs-lookup"><span data-stu-id="3036b-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
