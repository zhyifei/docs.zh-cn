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
ms.openlocfilehash: 2d5dbd003d0ea5decae0025d47e6bd5c1fb1ed4a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617069"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="e8e64-102">IAppDomainBinding::OnAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="e8e64-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="e8e64-103">由公共语言运行时（CLR）调用，用于通知主机已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e8e64-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8e64-104">语法</span><span class="sxs-lookup"><span data-stu-id="e8e64-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8e64-105">参数</span><span class="sxs-lookup"><span data-stu-id="e8e64-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="e8e64-106">中指向[IUnknown](/cpp/atl/iunknown)接口对象的指针，该对象表示新的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e8e64-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8e64-107">要求</span><span class="sxs-lookup"><span data-stu-id="e8e64-107">Requirements</span></span>  
 <span data-ttu-id="e8e64-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e8e64-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8e64-109">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e8e64-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8e64-110">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e8e64-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8e64-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8e64-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8e64-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8e64-112">See also</span></span>

- [<span data-ttu-id="e8e64-113">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="e8e64-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
