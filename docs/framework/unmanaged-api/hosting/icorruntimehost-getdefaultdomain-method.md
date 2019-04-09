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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a6c5ee73cad77368e83792d11d455d8fb163fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106166"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="74525-102">ICorRuntimeHost::GetDefaultDomain 方法</span><span class="sxs-lookup"><span data-stu-id="74525-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="74525-103">获取类型的接口指针<xref:System._AppDomain?displayProperty=nameWithType>，表示当前进程的默认域。</span><span class="sxs-lookup"><span data-stu-id="74525-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74525-104">语法</span><span class="sxs-lookup"><span data-stu-id="74525-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74525-105">参数</span><span class="sxs-lookup"><span data-stu-id="74525-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="74525-106">[out]类型的接口指针<xref:System._AppDomain?displayProperty=nameWithType>到<xref:System.AppDomain>表示进程的默认应用程序域的实例。</span><span class="sxs-lookup"><span data-stu-id="74525-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="74525-107">此指针被类型化为`IUnknown`，因此调用方通常应调用`QueryInterface`若要获取类型的接口指针<xref:System._AppDomain?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="74525-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74525-108">返回值</span><span class="sxs-lookup"><span data-stu-id="74525-108">Return Value</span></span>  
  
|<span data-ttu-id="74525-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74525-109">HRESULT</span></span>|<span data-ttu-id="74525-110">描述</span><span class="sxs-lookup"><span data-stu-id="74525-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74525-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74525-111">S_OK</span></span>|<span data-ttu-id="74525-112">操作成功。</span><span class="sxs-lookup"><span data-stu-id="74525-112">The operation was successful.</span></span>|  
|<span data-ttu-id="74525-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="74525-113">S_FALSE</span></span>|<span data-ttu-id="74525-114">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="74525-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="74525-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74525-115">E_FAIL</span></span>|<span data-ttu-id="74525-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="74525-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="74525-117">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="74525-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="74525-118">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="74525-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="74525-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="74525-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74525-120">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="74525-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="74525-121">要求</span><span class="sxs-lookup"><span data-stu-id="74525-121">Requirements</span></span>  
 <span data-ttu-id="74525-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="74525-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74525-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74525-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74525-124">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="74525-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74525-125">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="74525-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74525-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="74525-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="74525-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="74525-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
