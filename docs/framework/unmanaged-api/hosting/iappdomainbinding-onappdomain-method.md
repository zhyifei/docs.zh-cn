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
ms.openlocfilehash: 8dfd396568424c3a2300ed5d982e766afd5f925f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725488"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="e5459-102">IAppDomainBinding::OnAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="e5459-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="e5459-103">由公共语言运行时 (CLR)，用于通知宿主已创建的应用程序域调用。</span><span class="sxs-lookup"><span data-stu-id="e5459-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5459-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5459-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5459-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5459-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="e5459-106">[in]一个指向[IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx)接口对象，表示新的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e5459-106">[in] A pointer to an [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5459-107">要求</span><span class="sxs-lookup"><span data-stu-id="e5459-107">Requirements</span></span>  
 <span data-ttu-id="e5459-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5459-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5459-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5459-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5459-110">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e5459-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5459-111">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5459-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5459-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5459-112">See also</span></span>
- [<span data-ttu-id="e5459-113">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="e5459-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
