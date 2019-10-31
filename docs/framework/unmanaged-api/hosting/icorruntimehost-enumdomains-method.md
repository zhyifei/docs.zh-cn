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
ms.openlocfilehash: e5a1642f968228c5815732ecd470cb8f02a0eb83
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139579"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="816dd-102">ICorRuntimeHost::EnumDomains 方法</span><span class="sxs-lookup"><span data-stu-id="816dd-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="816dd-103">获取当前进程中的域的枚举数。</span><span class="sxs-lookup"><span data-stu-id="816dd-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="816dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="816dd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="816dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="816dd-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="816dd-106">弄域的枚举数。</span><span class="sxs-lookup"><span data-stu-id="816dd-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="816dd-107">返回值</span><span class="sxs-lookup"><span data-stu-id="816dd-107">Return Value</span></span>  
  
|<span data-ttu-id="816dd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="816dd-108">HRESULT</span></span>|<span data-ttu-id="816dd-109">描述</span><span class="sxs-lookup"><span data-stu-id="816dd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="816dd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="816dd-110">S_OK</span></span>|<span data-ttu-id="816dd-111">操作成功。</span><span class="sxs-lookup"><span data-stu-id="816dd-111">The operation was successful.</span></span>|  
|<span data-ttu-id="816dd-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="816dd-112">S_FALSE</span></span>|<span data-ttu-id="816dd-113">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="816dd-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="816dd-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="816dd-114">E_FAIL</span></span>|<span data-ttu-id="816dd-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="816dd-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="816dd-116">如果某个方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="816dd-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="816dd-117">对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="816dd-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="816dd-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="816dd-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="816dd-119">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="816dd-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="816dd-120">要求</span><span class="sxs-lookup"><span data-stu-id="816dd-120">Requirements</span></span>  
 <span data-ttu-id="816dd-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="816dd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="816dd-122">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="816dd-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="816dd-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="816dd-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="816dd-124">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="816dd-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="816dd-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="816dd-125">See also</span></span>

- [<span data-ttu-id="816dd-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="816dd-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
