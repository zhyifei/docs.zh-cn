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
ms.openlocfilehash: 60cbc6f6649db28d06321b59c26c45668628d9ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712215"
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="a221c-102">COR_GC_THREAD_STATS_TYPES 枚举</span><span class="sxs-lookup"><span data-stu-id="a221c-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="a221c-103">指示线程的垃圾收集统计信息。</span><span class="sxs-lookup"><span data-stu-id="a221c-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a221c-104">语法</span><span class="sxs-lookup"><span data-stu-id="a221c-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="a221c-105">成员</span><span class="sxs-lookup"><span data-stu-id="a221c-105">Members</span></span>  
  
|<span data-ttu-id="a221c-106">成员</span><span class="sxs-lookup"><span data-stu-id="a221c-106">Member</span></span>|<span data-ttu-id="a221c-107">描述</span><span class="sxs-lookup"><span data-stu-id="a221c-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="a221c-108">线程已在最近的垃圾回收提升的字节。</span><span class="sxs-lookup"><span data-stu-id="a221c-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a221c-109">要求</span><span class="sxs-lookup"><span data-stu-id="a221c-109">Requirements</span></span>  
 <span data-ttu-id="a221c-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a221c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a221c-111">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="a221c-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="a221c-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a221c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a221c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a221c-113">See also</span></span>
- [<span data-ttu-id="a221c-114">承载枚举</span><span class="sxs-lookup"><span data-stu-id="a221c-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
