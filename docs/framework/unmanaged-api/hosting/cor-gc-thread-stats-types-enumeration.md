---
title: COR_GC_THREAD_STATS_TYPES 枚举
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c631a0a3abb3cb2a342dfd44fdffb147b742ae3c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212461"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="3f8c4-102">COR_GC_THREAD_STATS_TYPES 枚举</span><span class="sxs-lookup"><span data-stu-id="3f8c4-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="3f8c4-103">指示线程的垃圾收集统计信息。</span><span class="sxs-lookup"><span data-stu-id="3f8c4-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f8c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f8c4-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="3f8c4-105">成员</span><span class="sxs-lookup"><span data-stu-id="3f8c4-105">Members</span></span>  
  
|<span data-ttu-id="3f8c4-106">成员</span><span class="sxs-lookup"><span data-stu-id="3f8c4-106">Member</span></span>|<span data-ttu-id="3f8c4-107">描述</span><span class="sxs-lookup"><span data-stu-id="3f8c4-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="3f8c4-108">线程已在最近的垃圾回收提升的字节。</span><span class="sxs-lookup"><span data-stu-id="3f8c4-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f8c4-109">要求</span><span class="sxs-lookup"><span data-stu-id="3f8c4-109">Requirements</span></span>  
 <span data-ttu-id="3f8c4-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f8c4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f8c4-111">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="3f8c4-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 **<span data-ttu-id="3f8c4-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3f8c4-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3f8c4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f8c4-113">See also</span></span>

- [<span data-ttu-id="3f8c4-114">承载枚举</span><span class="sxs-lookup"><span data-stu-id="3f8c4-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
