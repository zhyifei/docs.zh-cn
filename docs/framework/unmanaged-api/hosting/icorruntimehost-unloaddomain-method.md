---
title: ICorRuntimeHost::UnloadDomain 方法
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4db96133315b23a2d0b4bd32b597ee03f5d697b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438111"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="e43c8-102">ICorRuntimeHost::UnloadDomain 方法</span><span class="sxs-lookup"><span data-stu-id="e43c8-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="e43c8-103">卸载指定的应用程序域中从当前进程。</span><span class="sxs-lookup"><span data-stu-id="e43c8-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="e43c8-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e43c8-105">参数</span><span class="sxs-lookup"><span data-stu-id="e43c8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e43c8-106">[in]类型的指针<xref:System._AppDomain?displayProperty=nameWithType>，它表示要卸载的域。</span><span class="sxs-lookup"><span data-stu-id="e43c8-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e43c8-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e43c8-107">Return Value</span></span>  
  
|<span data-ttu-id="e43c8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e43c8-108">HRESULT</span></span>|<span data-ttu-id="e43c8-109">描述</span><span class="sxs-lookup"><span data-stu-id="e43c8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e43c8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e43c8-110">S_OK</span></span>|<span data-ttu-id="e43c8-111">该操作成功。</span><span class="sxs-lookup"><span data-stu-id="e43c8-111">The operation was successful.</span></span>|  
|<span data-ttu-id="e43c8-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e43c8-112">S_FALSE</span></span>|<span data-ttu-id="e43c8-113">操作无法完成。</span><span class="sxs-lookup"><span data-stu-id="e43c8-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e43c8-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e43c8-114">E_FAIL</span></span>|<span data-ttu-id="e43c8-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e43c8-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e43c8-116">如果某方法返回 E_FAIL，公共语言运行时 (CLR) 不再可用进程中。</span><span class="sxs-lookup"><span data-stu-id="e43c8-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e43c8-117">对任何托管 Api 的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e43c8-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e43c8-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e43c8-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e43c8-119">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e43c8-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e43c8-120">要求</span><span class="sxs-lookup"><span data-stu-id="e43c8-120">Requirements</span></span>  
 <span data-ttu-id="e43c8-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e43c8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43c8-122">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e43c8-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e43c8-123">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e43c8-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e43c8-124">**.NET framework 版本：** 1.0、 1.1</span><span class="sxs-lookup"><span data-stu-id="e43c8-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43c8-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="e43c8-125">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="e43c8-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="e43c8-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
