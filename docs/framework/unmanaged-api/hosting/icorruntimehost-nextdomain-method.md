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
ms.openlocfilehash: 36eacedfb83c1248fc252091872bcfeecdbcd874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139512"
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="c37e3-102">ICorRuntimeHost::NextDomain 方法</span><span class="sxs-lookup"><span data-stu-id="c37e3-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="c37e3-103">获取一个接口指针，该指针指向枚举中的下一个域。</span><span class="sxs-lookup"><span data-stu-id="c37e3-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="c37e3-104">Syntax</span></span>  
  
```cpp  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c37e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="c37e3-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c37e3-106">中通过调用[EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)获取的枚举器。</span><span class="sxs-lookup"><span data-stu-id="c37e3-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="c37e3-107">弄指向表示枚举中下一个域的 <xref:System._AppDomain?displayProperty=nameWithType> 类型的接口指针; 如果不存在其他域，则为 null。</span><span class="sxs-lookup"><span data-stu-id="c37e3-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c37e3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c37e3-108">Return Value</span></span>  
  
|<span data-ttu-id="c37e3-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c37e3-109">HRESULT</span></span>|<span data-ttu-id="c37e3-110">描述</span><span class="sxs-lookup"><span data-stu-id="c37e3-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c37e3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c37e3-111">S_OK</span></span>|<span data-ttu-id="c37e3-112">操作成功。</span><span class="sxs-lookup"><span data-stu-id="c37e3-112">The operation was successful.</span></span>|  
|<span data-ttu-id="c37e3-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c37e3-113">S_FALSE</span></span>|<span data-ttu-id="c37e3-114">操作未能完成，或者枚举中没有更多的域。</span><span class="sxs-lookup"><span data-stu-id="c37e3-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="c37e3-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c37e3-115">E_FAIL</span></span>|<span data-ttu-id="c37e3-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c37e3-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c37e3-117">如果某个方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c37e3-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c37e3-118">对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c37e3-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c37e3-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c37e3-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c37e3-120">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c37e3-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c37e3-121">要求</span><span class="sxs-lookup"><span data-stu-id="c37e3-121">Requirements</span></span>  
 <span data-ttu-id="c37e3-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c37e3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37e3-123">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c37e3-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c37e3-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c37e3-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c37e3-125">**.NET Framework 版本：** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="c37e3-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37e3-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c37e3-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="c37e3-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="c37e3-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
