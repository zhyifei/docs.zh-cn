---
title: ICorRuntimeHost::GetDefaultDomain 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
ms.openlocfilehash: 6dc25cbeef2576a2ecc6ec39b2cb3f9abb7b9964
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139552"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="b86be-102">ICorRuntimeHost::GetDefaultDomain 方法</span><span class="sxs-lookup"><span data-stu-id="b86be-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="b86be-103">获取 <xref:System._AppDomain?displayProperty=nameWithType> 类型的接口指针，该指针表示当前进程的默认域。</span><span class="sxs-lookup"><span data-stu-id="b86be-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b86be-104">语法</span><span class="sxs-lookup"><span data-stu-id="b86be-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b86be-105">参数</span><span class="sxs-lookup"><span data-stu-id="b86be-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="b86be-106">弄类型 <xref:System._AppDomain?displayProperty=nameWithType> 的接口指针，用于表示进程的默认应用程序域的 <xref:System.AppDomain> 实例。</span><span class="sxs-lookup"><span data-stu-id="b86be-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="b86be-107">此指针 `IUnknown`类型化，因此调用方通常应调用 `QueryInterface` 以获取 <xref:System._AppDomain?displayProperty=nameWithType>类型的接口指针。</span><span class="sxs-lookup"><span data-stu-id="b86be-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b86be-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b86be-108">Return Value</span></span>  
  
|<span data-ttu-id="b86be-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b86be-109">HRESULT</span></span>|<span data-ttu-id="b86be-110">描述</span><span class="sxs-lookup"><span data-stu-id="b86be-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b86be-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b86be-111">S_OK</span></span>|<span data-ttu-id="b86be-112">操作成功。</span><span class="sxs-lookup"><span data-stu-id="b86be-112">The operation was successful.</span></span>|  
|<span data-ttu-id="b86be-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b86be-113">S_FALSE</span></span>|<span data-ttu-id="b86be-114">操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="b86be-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b86be-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b86be-115">E_FAIL</span></span>|<span data-ttu-id="b86be-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="b86be-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b86be-117">如果某个方法返回 E_FAIL，则公共语言运行时（CLR）在该过程中将不再可用。</span><span class="sxs-lookup"><span data-stu-id="b86be-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b86be-118">对任何托管 Api 的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="b86be-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b86be-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b86be-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b86be-120">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="b86be-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b86be-121">要求</span><span class="sxs-lookup"><span data-stu-id="b86be-121">Requirements</span></span>  
 <span data-ttu-id="b86be-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b86be-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b86be-123">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b86be-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b86be-124">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b86be-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b86be-125">**.NET Framework 版本：** 1.0、1.1</span><span class="sxs-lookup"><span data-stu-id="b86be-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b86be-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b86be-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="b86be-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="b86be-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
