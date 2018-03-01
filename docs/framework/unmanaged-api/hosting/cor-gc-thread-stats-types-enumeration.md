---
title: "COR_GC_THREAD_STATS_TYPES 枚举"
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
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1967f13037be597288b48cbbdf001cad5d6b8e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="71f7c-102">COR_GC_THREAD_STATS_TYPES 枚举</span><span class="sxs-lookup"><span data-stu-id="71f7c-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="71f7c-103">指示线程垃圾回收统计信息。</span><span class="sxs-lookup"><span data-stu-id="71f7c-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="71f7c-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="71f7c-105">成员</span><span class="sxs-lookup"><span data-stu-id="71f7c-105">Members</span></span>  
  
|<span data-ttu-id="71f7c-106">成员</span><span class="sxs-lookup"><span data-stu-id="71f7c-106">Member</span></span>|<span data-ttu-id="71f7c-107">描述</span><span class="sxs-lookup"><span data-stu-id="71f7c-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="71f7c-108">线程有在最新的垃圾回收提升的字节。</span><span class="sxs-lookup"><span data-stu-id="71f7c-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71f7c-109">惠?</span><span class="sxs-lookup"><span data-stu-id="71f7c-109">Requirements</span></span>  
 <span data-ttu-id="71f7c-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71f7c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71f7c-111">**标头：** GCHost.idl、 GCHost.h</span><span class="sxs-lookup"><span data-stu-id="71f7c-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="71f7c-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71f7c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f7c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="71f7c-113">See Also</span></span>  
 [<span data-ttu-id="71f7c-114">承载枚举</span><span class="sxs-lookup"><span data-stu-id="71f7c-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
