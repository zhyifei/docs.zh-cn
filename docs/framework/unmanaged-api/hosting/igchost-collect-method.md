---
title: IGCHost::Collect 方法
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
ms.openlocfilehash: ac73c462aa210927f0665cae161fd7f3e17a0cdb
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805312"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="e10ab-102">IGCHost::Collect 方法</span><span class="sxs-lookup"><span data-stu-id="e10ab-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="e10ab-103">为给定的生成强制执行回收，而不考虑当前垃圾回收的状态。</span><span class="sxs-lookup"><span data-stu-id="e10ab-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e10ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="e10ab-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e10ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="e10ab-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="e10ab-106">中要对其执行垃圾回收的代。</span><span class="sxs-lookup"><span data-stu-id="e10ab-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="e10ab-107">如果值为-1，则表示所有代将进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="e10ab-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e10ab-108">要求</span><span class="sxs-lookup"><span data-stu-id="e10ab-108">Requirements</span></span>  
 <span data-ttu-id="e10ab-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e10ab-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e10ab-110">**标头：** GCHost，GCHost</span><span class="sxs-lookup"><span data-stu-id="e10ab-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e10ab-111">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e10ab-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e10ab-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e10ab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10ab-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e10ab-113">See also</span></span>

- [<span data-ttu-id="e10ab-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="e10ab-114">IGCHost Interface</span></span>](igchost-interface.md)
