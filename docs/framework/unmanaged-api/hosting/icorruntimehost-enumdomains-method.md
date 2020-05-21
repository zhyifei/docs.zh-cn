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
ms.openlocfilehash: a97471e1c257902633b7eb363c3cc51288c70917
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762248"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="d65b1-102">ICorRuntimeHost::EnumDomains 方法</span><span class="sxs-lookup"><span data-stu-id="d65b1-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="d65b1-103">获取当前进程中的域的枚举数。</span><span class="sxs-lookup"><span data-stu-id="d65b1-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d65b1-104">语法</span><span class="sxs-lookup"><span data-stu-id="d65b1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d65b1-105">参数</span><span class="sxs-lookup"><span data-stu-id="d65b1-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="d65b1-106">弄域的枚举数。</span><span class="sxs-lookup"><span data-stu-id="d65b1-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d65b1-107">返回值</span><span class="sxs-lookup"><span data-stu-id="d65b1-107">Return Value</span></span>  
  
|<span data-ttu-id="d65b1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d65b1-108">HRESULT</span></span>|<span data-ttu-id="d65b1-109">说明</span><span class="sxs-lookup"><span data-stu-id="d65b1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d65b1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d65b1-110">S_OK</span></span>|<span data-ttu-id="d65b1-111">操作成功。</span><span class="sxs-lookup"><span data-stu-id="d65b1-111">The operation was successful.</span></span>|  
|<span data-ttu-id="d65b1-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d65b1-112">S_FALSE</span></span>|<span data-ttu-id="d65b1-113">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="d65b1-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="d65b1-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d65b1-114">E_FAIL</span></span>|<span data-ttu-id="d65b1-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d65b1-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="d65b1-116">如果方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d65b1-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="d65b1-117">对任何宿主 Api 的后续调用都会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d65b1-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d65b1-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d65b1-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d65b1-119">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d65b1-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d65b1-120">要求</span><span class="sxs-lookup"><span data-stu-id="d65b1-120">Requirements</span></span>  
 <span data-ttu-id="d65b1-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d65b1-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d65b1-122">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d65b1-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d65b1-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d65b1-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d65b1-124">**.NET Framework 版本：** 1.0、1。1</span><span class="sxs-lookup"><span data-stu-id="d65b1-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65b1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d65b1-125">See also</span></span>

- [<span data-ttu-id="d65b1-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="d65b1-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
