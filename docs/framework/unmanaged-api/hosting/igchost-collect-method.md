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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f911d99470b9870f5c42d4170a4024123c10e7f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511116"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="f7c20-102">IGCHost::Collect 方法</span><span class="sxs-lookup"><span data-stu-id="f7c20-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="f7c20-103">强制给定生成，而不考虑当前的垃圾回收状态发生的集合。</span><span class="sxs-lookup"><span data-stu-id="f7c20-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c20-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7c20-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7c20-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7c20-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="f7c20-106">[in]要对其执行垃圾回收生成。</span><span class="sxs-lookup"><span data-stu-id="f7c20-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="f7c20-107">值为-1 指示所有代将都进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="f7c20-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c20-108">要求</span><span class="sxs-lookup"><span data-stu-id="f7c20-108">Requirements</span></span>  
 <span data-ttu-id="f7c20-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7c20-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c20-110">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="f7c20-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="f7c20-111">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f7c20-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7c20-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7c20-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c20-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7c20-113">See also</span></span>
- [<span data-ttu-id="f7c20-114">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="f7c20-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
