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
ms.openlocfilehash: c6f368f4288f8203067c1f9ff350ce0f3389f514
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617084"
---
# <a name="iappdomainbinding-interface"></a><span data-ttu-id="a36a8-102">IAppDomainBinding 接口</span><span class="sxs-lookup"><span data-stu-id="a36a8-102">IAppDomainBinding Interface</span></span>
<span data-ttu-id="a36a8-103">提供一个方法，该方法由公共语言运行时（CLR）调用，用于通知宿主应用程序已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a36a8-103">Provides a method that is called by the common language runtime (CLR) to notify the host application that an application domain has been created.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a36a8-104">方法</span><span class="sxs-lookup"><span data-stu-id="a36a8-104">Methods</span></span>  
  
|<span data-ttu-id="a36a8-105">方法</span><span class="sxs-lookup"><span data-stu-id="a36a8-105">Method</span></span>|<span data-ttu-id="a36a8-106">说明</span><span class="sxs-lookup"><span data-stu-id="a36a8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a36a8-107">OnAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="a36a8-107">OnAppDomain Method</span></span>](iappdomainbinding-onappdomain-method.md)|<span data-ttu-id="a36a8-108">由公共语言运行时（CLR）调用，用于通知主机已创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a36a8-108">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a36a8-109">要求</span><span class="sxs-lookup"><span data-stu-id="a36a8-109">Requirements</span></span>  
 <span data-ttu-id="a36a8-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a36a8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a36a8-111">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a36a8-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a36a8-112">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a36a8-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a36a8-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a36a8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36a8-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a36a8-114">See also</span></span>

- [<span data-ttu-id="a36a8-115">承载接口</span><span class="sxs-lookup"><span data-stu-id="a36a8-115">Hosting Interfaces</span></span>](hosting-interfaces.md)
