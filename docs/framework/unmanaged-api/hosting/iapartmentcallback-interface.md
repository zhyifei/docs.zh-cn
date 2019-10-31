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
ms.openlocfilehash: 4424509c16dd1d9f83db117ae7343fa03995297e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126910"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="44442-102">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="44442-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="44442-103">提供用于在单元中进行回调的方法。</span><span class="sxs-lookup"><span data-stu-id="44442-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="44442-104">*单元*是进程内共享相同线程访问要求的对象的逻辑容器。</span><span class="sxs-lookup"><span data-stu-id="44442-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44442-105">方法</span><span class="sxs-lookup"><span data-stu-id="44442-105">Methods</span></span>  
  
|<span data-ttu-id="44442-106">方法</span><span class="sxs-lookup"><span data-stu-id="44442-106">Method</span></span>|<span data-ttu-id="44442-107">描述</span><span class="sxs-lookup"><span data-stu-id="44442-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44442-108">DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="44442-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="44442-109">在单元内执行指定的函数。</span><span class="sxs-lookup"><span data-stu-id="44442-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44442-110">要求</span><span class="sxs-lookup"><span data-stu-id="44442-110">Requirements</span></span>  
 <span data-ttu-id="44442-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44442-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44442-112">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="44442-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44442-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="44442-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44442-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44442-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44442-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="44442-115">See also</span></span>

- [<span data-ttu-id="44442-116">承载接口</span><span class="sxs-lookup"><span data-stu-id="44442-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
