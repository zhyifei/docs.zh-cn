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
ms.openlocfilehash: 37c02b878cd52034603ab6cafe4d8aaca594cbe9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126886"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="47db6-102">IAppDomainBinding::OnAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="47db6-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="47db6-103">由公共语言运行时（CLR）调用，用于通知主机已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="47db6-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47db6-104">语法</span><span class="sxs-lookup"><span data-stu-id="47db6-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47db6-105">参数</span><span class="sxs-lookup"><span data-stu-id="47db6-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="47db6-106">中指向[IUnknown](/cpp/atl/iunknown)接口对象的指针，该对象表示新的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="47db6-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47db6-107">要求</span><span class="sxs-lookup"><span data-stu-id="47db6-107">Requirements</span></span>  
 <span data-ttu-id="47db6-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47db6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47db6-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="47db6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47db6-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="47db6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47db6-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47db6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47db6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="47db6-112">See also</span></span>

- [<span data-ttu-id="47db6-113">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="47db6-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
