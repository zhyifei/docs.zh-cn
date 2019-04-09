---
title: IAppDomainBinding 接口
ms.date: 03/30/2017
api_name:
- IAppDomainBinding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainBinding
helpviewer_keywords:
- IAppDomainBinding interface [.NET Framework hosting]
ms.assetid: 368881ab-c4ea-4731-bf22-c596aac7c66c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2c3a3057003d0035bfcb096a94c84d610e3056f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134181"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="8e2a1-102">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="8e2a1-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="8e2a1-103">提供由公共语言运行时 (CLR) 以通知主机应用程序已创建的应用程序域调用的方法。</span><span class="sxs-lookup"><span data-stu-id="8e2a1-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e2a1-104">方法</span><span class="sxs-lookup"><span data-stu-id="8e2a1-104">Methods</span></span>  
  
|<span data-ttu-id="8e2a1-105">方法</span><span class="sxs-lookup"><span data-stu-id="8e2a1-105">Method</span></span>|<span data-ttu-id="8e2a1-106">描述</span><span class="sxs-lookup"><span data-stu-id="8e2a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e2a1-107">OnAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="8e2a1-107">OnAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="8e2a1-108">由公共语言运行时 (CLR)，用于通知宿主已创建的应用程序域调用。</span><span class="sxs-lookup"><span data-stu-id="8e2a1-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8e2a1-109">要求</span><span class="sxs-lookup"><span data-stu-id="8e2a1-109">Requirements</span></span>  
 <span data-ttu-id="8e2a1-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e2a1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e2a1-111">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e2a1-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e2a1-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8e2a1-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8e2a1-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="8e2a1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8e2a1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e2a1-114">See also</span></span>

- [<span data-ttu-id="8e2a1-115">承载接口</span><span class="sxs-lookup"><span data-stu-id="8e2a1-115">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
