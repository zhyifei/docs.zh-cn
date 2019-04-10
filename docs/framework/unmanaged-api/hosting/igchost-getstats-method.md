---
title: IGCHost::GetStats 方法
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14751b41809eeda5e6bd990fae368879d0f30492
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227829"
---
# <a name="igchostgetstats-method"></a><span data-ttu-id="739f3-102">IGCHost::GetStats 方法</span><span class="sxs-lookup"><span data-stu-id="739f3-102">IGCHost::GetStats Method</span></span>
<span data-ttu-id="739f3-103">获取垃圾回收系统的当前状态的统计信息。</span><span class="sxs-lookup"><span data-stu-id="739f3-103">Gets the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="739f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="739f3-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="739f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="739f3-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="739f3-106">[in、 out]一个指向[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)结构，其中包含垃圾回收系统的当前状态的统计信息。</span><span class="sxs-lookup"><span data-stu-id="739f3-106">[in, out] A pointer to a [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure that contains the statistics for the current state of the garbage collection system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="739f3-107">备注</span><span class="sxs-lookup"><span data-stu-id="739f3-107">Remarks</span></span>  
 <span data-ttu-id="739f3-108">统计信息可以由智能分配系统，用于帮助垃圾回收系统进行操作。</span><span class="sxs-lookup"><span data-stu-id="739f3-108">The statistics can be used by a smart allocation system to help the garbage collection system operate.</span></span> <span data-ttu-id="739f3-109">例如，分配系统可能会确定，请查看统计信息，它需要添加更多内存或强制回收后。</span><span class="sxs-lookup"><span data-stu-id="739f3-109">For example, the allocation system may determine, after reviewing the statistics, that it needs to add more memory or force a collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="739f3-110">要求</span><span class="sxs-lookup"><span data-stu-id="739f3-110">Requirements</span></span>  
 <span data-ttu-id="739f3-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="739f3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="739f3-112">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="739f3-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="739f3-113">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="739f3-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="739f3-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="739f3-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="739f3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="739f3-115">See also</span></span>

- [<span data-ttu-id="739f3-116">IGCHost 接口</span><span class="sxs-lookup"><span data-stu-id="739f3-116">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
