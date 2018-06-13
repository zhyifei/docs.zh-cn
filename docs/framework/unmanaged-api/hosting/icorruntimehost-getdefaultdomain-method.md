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
ms.openlocfilehash: f2351fbb26a38f408d330db3f7600120bd57d6e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437877"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="2b26f-102">ICorRuntimeHost::GetDefaultDomain 方法</span><span class="sxs-lookup"><span data-stu-id="2b26f-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="2b26f-103">获取类型的接口指针<xref:System._AppDomain?displayProperty=nameWithType>，它表示当前进程的默认域。</span><span class="sxs-lookup"><span data-stu-id="2b26f-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b26f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b26f-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b26f-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b26f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2b26f-106">[out]类型的接口指针<xref:System._AppDomain?displayProperty=nameWithType>到<xref:System.AppDomain>表示进程的默认应用程序域的实例。</span><span class="sxs-lookup"><span data-stu-id="2b26f-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="2b26f-107">此指针被类型化为`IUnknown`，因此通常应调用的调用方`QueryInterface`若要获取类型的接口指针<xref:System._AppDomain?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2b26f-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b26f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2b26f-108">Return Value</span></span>  
  
|<span data-ttu-id="2b26f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b26f-109">HRESULT</span></span>|<span data-ttu-id="2b26f-110">描述</span><span class="sxs-lookup"><span data-stu-id="2b26f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b26f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b26f-111">S_OK</span></span>|<span data-ttu-id="2b26f-112">该操作成功。</span><span class="sxs-lookup"><span data-stu-id="2b26f-112">The operation was successful.</span></span>|  
|<span data-ttu-id="2b26f-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2b26f-113">S_FALSE</span></span>|<span data-ttu-id="2b26f-114">操作无法完成。</span><span class="sxs-lookup"><span data-stu-id="2b26f-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2b26f-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b26f-115">E_FAIL</span></span>|<span data-ttu-id="2b26f-116">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2b26f-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2b26f-117">如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。</span><span class="sxs-lookup"><span data-stu-id="2b26f-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="2b26f-118">对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2b26f-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2b26f-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b26f-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b26f-120">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2b26f-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b26f-121">要求</span><span class="sxs-lookup"><span data-stu-id="2b26f-121">Requirements</span></span>  
 <span data-ttu-id="2b26f-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b26f-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b26f-123">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2b26f-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b26f-124">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2b26f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b26f-125">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="2b26f-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b26f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b26f-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="2b26f-127">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="2b26f-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
