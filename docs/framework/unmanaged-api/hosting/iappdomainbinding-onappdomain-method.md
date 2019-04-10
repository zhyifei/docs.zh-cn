---
title: IAppDomainBinding::OnAppDomain 方法
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2903395f5f834f2435b14d0b3f3e8bfe24af2867
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183048"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="5d087-102">IAppDomainBinding::OnAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="5d087-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="5d087-103">由公共语言运行时 (CLR)，用于通知宿主已创建的应用程序域调用。</span><span class="sxs-lookup"><span data-stu-id="5d087-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d087-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d087-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d087-105">参数</span><span class="sxs-lookup"><span data-stu-id="5d087-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="5d087-106">[in]一个指向[IUnknown](/cpp/atl/iunknown)接口对象，表示新的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="5d087-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d087-107">要求</span><span class="sxs-lookup"><span data-stu-id="5d087-107">Requirements</span></span>  
 <span data-ttu-id="5d087-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d087-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d087-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d087-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d087-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5d087-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5d087-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5d087-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d087-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d087-112">See also</span></span>

- [<span data-ttu-id="5d087-113">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="5d087-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
