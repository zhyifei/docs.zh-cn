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
ms.openlocfilehash: fbf501d906ecc0bf55719fa33d1af2d4db1cc2ef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617082"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="31439-102">IApartmentCallback 接口</span><span class="sxs-lookup"><span data-stu-id="31439-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="31439-103">提供用于在单元中进行回调的方法。</span><span class="sxs-lookup"><span data-stu-id="31439-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="31439-104">*单元*是进程内共享相同线程访问要求的对象的逻辑容器。</span><span class="sxs-lookup"><span data-stu-id="31439-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31439-105">方法</span><span class="sxs-lookup"><span data-stu-id="31439-105">Methods</span></span>  
  
|<span data-ttu-id="31439-106">方法</span><span class="sxs-lookup"><span data-stu-id="31439-106">Method</span></span>|<span data-ttu-id="31439-107">说明</span><span class="sxs-lookup"><span data-stu-id="31439-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31439-108">DoCallback 方法</span><span class="sxs-lookup"><span data-stu-id="31439-108">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="31439-109">在单元内执行指定的函数。</span><span class="sxs-lookup"><span data-stu-id="31439-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31439-110">要求</span><span class="sxs-lookup"><span data-stu-id="31439-110">Requirements</span></span>  
 <span data-ttu-id="31439-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31439-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31439-112">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="31439-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31439-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="31439-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31439-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31439-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31439-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31439-115">See also</span></span>

- [<span data-ttu-id="31439-116">承载接口</span><span class="sxs-lookup"><span data-stu-id="31439-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
