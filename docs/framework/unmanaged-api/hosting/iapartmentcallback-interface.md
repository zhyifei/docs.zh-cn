---
title: "IApartmentCallback 接口"
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
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 821e19f9078f65941c1826c55abcfafb730fe0da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="15d6f-102">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="15d6f-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="15d6f-103">提供用于在单元内进行回调方法。</span><span class="sxs-lookup"><span data-stu-id="15d6f-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="15d6f-104">*单元*是共享相同的线程访问要求的对象的进程中的逻辑容器。</span><span class="sxs-lookup"><span data-stu-id="15d6f-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15d6f-105">方法</span><span class="sxs-lookup"><span data-stu-id="15d6f-105">Methods</span></span>  
  
|<span data-ttu-id="15d6f-106">方法</span><span class="sxs-lookup"><span data-stu-id="15d6f-106">Method</span></span>|<span data-ttu-id="15d6f-107">描述</span><span class="sxs-lookup"><span data-stu-id="15d6f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15d6f-108">DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="15d6f-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="15d6f-109">执行的单元内的指定的函数。</span><span class="sxs-lookup"><span data-stu-id="15d6f-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15d6f-110">惠?</span><span class="sxs-lookup"><span data-stu-id="15d6f-110">Requirements</span></span>  
 <span data-ttu-id="15d6f-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="15d6f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15d6f-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15d6f-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15d6f-113">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="15d6f-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15d6f-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15d6f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d6f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="15d6f-115">See Also</span></span>  
 [<span data-ttu-id="15d6f-116">承载接口</span><span class="sxs-lookup"><span data-stu-id="15d6f-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
