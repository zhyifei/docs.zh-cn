---
title: "IApartmentCallback 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IApartmentCallback
helpviewer_keywords: IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d2f2ea73da2273ff6f0abb725ec3e3fb8ca79ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="a40fd-102">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="a40fd-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="a40fd-103">提供用于在单元内进行回调方法。</span><span class="sxs-lookup"><span data-stu-id="a40fd-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="a40fd-104">*单元*是共享相同的线程访问要求的对象的进程中的逻辑容器。</span><span class="sxs-lookup"><span data-stu-id="a40fd-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a40fd-105">方法</span><span class="sxs-lookup"><span data-stu-id="a40fd-105">Methods</span></span>  
  
|<span data-ttu-id="a40fd-106">方法</span><span class="sxs-lookup"><span data-stu-id="a40fd-106">Method</span></span>|<span data-ttu-id="a40fd-107">描述</span><span class="sxs-lookup"><span data-stu-id="a40fd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a40fd-108">DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="a40fd-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="a40fd-109">执行的单元内的指定的函数。</span><span class="sxs-lookup"><span data-stu-id="a40fd-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a40fd-110">要求</span><span class="sxs-lookup"><span data-stu-id="a40fd-110">Requirements</span></span>  
 <span data-ttu-id="a40fd-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a40fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a40fd-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a40fd-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a40fd-113">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a40fd-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a40fd-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a40fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a40fd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a40fd-115">See Also</span></span>  
 [<span data-ttu-id="a40fd-116">承载接口</span><span class="sxs-lookup"><span data-stu-id="a40fd-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
