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
ms.openlocfilehash: 492a60d3c8d18bec4e99ae778686fec6e8724248
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140564"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="c0d74-102">ICorRuntimeHost::UnloadDomain 方法</span><span class="sxs-lookup"><span data-stu-id="c0d74-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="c0d74-103">卸载当前的过程中指定的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c0d74-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d74-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0d74-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0d74-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0d74-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c0d74-106">[in]类型的指针<xref:System._AppDomain?displayProperty=nameWithType>，表示要卸载的域。</span><span class="sxs-lookup"><span data-stu-id="c0d74-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0d74-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c0d74-107">Return Value</span></span>  
  
|<span data-ttu-id="c0d74-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c0d74-108">HRESULT</span></span>|<span data-ttu-id="c0d74-109">描述</span><span class="sxs-lookup"><span data-stu-id="c0d74-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c0d74-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0d74-110">S_OK</span></span>|<span data-ttu-id="c0d74-111">操作成功。</span><span class="sxs-lookup"><span data-stu-id="c0d74-111">The operation was successful.</span></span>|  
|<span data-ttu-id="c0d74-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c0d74-112">S_FALSE</span></span>|<span data-ttu-id="c0d74-113">该操作未能完成。</span><span class="sxs-lookup"><span data-stu-id="c0d74-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c0d74-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c0d74-114">E_FAIL</span></span>|<span data-ttu-id="c0d74-115">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c0d74-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c0d74-116">如果方法返回 E_FAIL，公共语言运行时 (CLR) 不再可在该过程中使用。</span><span class="sxs-lookup"><span data-stu-id="c0d74-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c0d74-117">对任何托管 Api 的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c0d74-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c0d74-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c0d74-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c0d74-119">CLR 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c0d74-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0d74-120">要求</span><span class="sxs-lookup"><span data-stu-id="c0d74-120">Requirements</span></span>  
 <span data-ttu-id="c0d74-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0d74-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0d74-122">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c0d74-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c0d74-123">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c0d74-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0d74-124">**.NET framework 版本：** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c0d74-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d74-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0d74-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="c0d74-126">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="c0d74-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
