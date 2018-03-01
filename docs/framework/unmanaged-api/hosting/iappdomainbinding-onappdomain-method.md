---
title: "IAppDomainBinding::OnAppDomain 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 131e4af5d8c410f625d2c119097f07f5facd4300
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="8b689-102">IAppDomainBinding::OnAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="8b689-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="8b689-103">由公共语言运行时 (CLR)，用于通知宿主已创建应用程序域调用。</span><span class="sxs-lookup"><span data-stu-id="8b689-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b689-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b689-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b689-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b689-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="8b689-106">[in]指向的指针[IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx)接口对象，表示新的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="8b689-106">[in] A pointer to an [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b689-107">惠?</span><span class="sxs-lookup"><span data-stu-id="8b689-107">Requirements</span></span>  
 <span data-ttu-id="8b689-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b689-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b689-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b689-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b689-110">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8b689-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b689-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b689-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b689-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b689-112">See Also</span></span>  
 [<span data-ttu-id="8b689-113">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="8b689-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
