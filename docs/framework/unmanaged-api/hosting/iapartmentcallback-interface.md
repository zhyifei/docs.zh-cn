---
title: IApartmentCallback 接口
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db933716cc0602ecda5da8a72726408ae4910179
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129800"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="afa8e-102">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="afa8e-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="afa8e-103">提供用于在单元内使回调方法。</span><span class="sxs-lookup"><span data-stu-id="afa8e-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="afa8e-104">*单元*是个对象共享相同的线程访问要求进程内的逻辑容器。</span><span class="sxs-lookup"><span data-stu-id="afa8e-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afa8e-105">方法</span><span class="sxs-lookup"><span data-stu-id="afa8e-105">Methods</span></span>  
  
|<span data-ttu-id="afa8e-106">方法</span><span class="sxs-lookup"><span data-stu-id="afa8e-106">Method</span></span>|<span data-ttu-id="afa8e-107">描述</span><span class="sxs-lookup"><span data-stu-id="afa8e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afa8e-108">DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="afa8e-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="afa8e-109">执行单元内的指定的函数。</span><span class="sxs-lookup"><span data-stu-id="afa8e-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="afa8e-110">要求</span><span class="sxs-lookup"><span data-stu-id="afa8e-110">Requirements</span></span>  
 <span data-ttu-id="afa8e-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="afa8e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afa8e-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="afa8e-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afa8e-113">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="afa8e-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afa8e-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afa8e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa8e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="afa8e-115">See also</span></span>

- [<span data-ttu-id="afa8e-116">承载接口</span><span class="sxs-lookup"><span data-stu-id="afa8e-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
