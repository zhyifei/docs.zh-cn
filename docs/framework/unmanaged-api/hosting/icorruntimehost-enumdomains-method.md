---
title: ICorRuntimeHost::EnumDomains 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69fcc862e98e305105a6f17ca49940bd10cef39c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072553"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="99282-102">ICorRuntimeHost::EnumDomains 方法</span><span class="sxs-lookup"><span data-stu-id="99282-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="99282-103">域当前进程中获取一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="99282-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99282-104">语法</span><span class="sxs-lookup"><span data-stu-id="99282-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99282-105">参数</span><span class="sxs-lookup"><span data-stu-id="99282-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="99282-106">[out]一个枚举器的域。</span><span class="sxs-lookup"><span data-stu-id="99282-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99282-107">返回值</span><span class="sxs-lookup"><span data-stu-id="99282-107">Return Value</span></span>  
  
|<span data-ttu-id="99282-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99282-108">HRESULT</span></span>|<span data-ttu-id="99282-109">描述</span><span class="sxs-lookup"><span data-stu-id="99282-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99282-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="99282-110">S_OK</span></span>|<span data-ttu-id="99282-111">操作成功。</span><span class="sxs-lookup"><span data-stu-id="99282-111">The operation was successful.</span></span>|  
|<span data-ttu-id="99282-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="99282-112">S_FALSE</span></span>|<span data-ttu-id="99282-113">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="99282-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="99282-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99282-114">E_FAIL</span></span>|<span data-ttu-id="99282-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="99282-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="99282-116">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="99282-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="99282-117">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="99282-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="99282-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99282-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99282-119">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="99282-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99282-120">要求</span><span class="sxs-lookup"><span data-stu-id="99282-120">Requirements</span></span>  
 <span data-ttu-id="99282-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99282-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99282-122">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="99282-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99282-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="99282-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99282-124">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="99282-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99282-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="99282-125">See also</span></span>

- [<span data-ttu-id="99282-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="99282-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
