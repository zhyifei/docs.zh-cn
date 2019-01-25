---
title: ICorRuntimeHost::NextDomain 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.NextDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f8e9c91ddddd0e0b14c79bef86c7665ff4e3dcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723316"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="3b61b-102">ICorRuntimeHost::NextDomain 方法</span><span class="sxs-lookup"><span data-stu-id="3b61b-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="3b61b-103">获取到下一个域中枚举的接口指针。</span><span class="sxs-lookup"><span data-stu-id="3b61b-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b61b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b61b-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b61b-105">参数</span><span class="sxs-lookup"><span data-stu-id="3b61b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="3b61b-106">[in]枚举器获取通过调用[EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)。</span><span class="sxs-lookup"><span data-stu-id="3b61b-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="3b61b-107">[out]接口指针<xref:System._AppDomain?displayProperty=nameWithType>表示下一个域中的枚举或为 null，如果没有更多域存在的类型。</span><span class="sxs-lookup"><span data-stu-id="3b61b-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b61b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3b61b-108">Return Value</span></span>  
  
|<span data-ttu-id="3b61b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3b61b-109">HRESULT</span></span>|<span data-ttu-id="3b61b-110">描述</span><span class="sxs-lookup"><span data-stu-id="3b61b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3b61b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3b61b-111">S_OK</span></span>|<span data-ttu-id="3b61b-112">操作成功。</span><span class="sxs-lookup"><span data-stu-id="3b61b-112">The operation was successful.</span></span>|  
|<span data-ttu-id="3b61b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3b61b-113">S_FALSE</span></span>|<span data-ttu-id="3b61b-114">该操作无法完成，或者在枚举中没有更多域。</span><span class="sxs-lookup"><span data-stu-id="3b61b-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="3b61b-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3b61b-115">E_FAIL</span></span>|<span data-ttu-id="3b61b-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3b61b-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3b61b-117">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="3b61b-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="3b61b-118">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3b61b-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3b61b-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3b61b-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3b61b-120">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3b61b-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b61b-121">要求</span><span class="sxs-lookup"><span data-stu-id="3b61b-121">Requirements</span></span>  
 <span data-ttu-id="3b61b-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b61b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b61b-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3b61b-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3b61b-124">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3b61b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b61b-125">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3b61b-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b61b-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b61b-126">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="3b61b-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="3b61b-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
