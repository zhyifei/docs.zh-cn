---
title: COR_GC_STAT_TYPES 枚举
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd12feb47352d9bb78aa8ef056072f9bdc6fba3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710318"
---
# <a name="corgcstattypes-enumeration"></a><span data-ttu-id="5da6b-102">COR_GC_STAT_TYPES 枚举</span><span class="sxs-lookup"><span data-stu-id="5da6b-102">COR_GC_STAT_TYPES Enumeration</span></span>
<span data-ttu-id="5da6b-103">指定要为垃圾收集记录的统计信息。</span><span class="sxs-lookup"><span data-stu-id="5da6b-103">Specifies the statistics to be recorded for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5da6b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5da6b-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a><span data-ttu-id="5da6b-105">备注</span><span class="sxs-lookup"><span data-stu-id="5da6b-105">Remarks</span></span>  
 <span data-ttu-id="5da6b-106">此枚举指定在哪些统计信息[COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)结构是由设置[iclrgcmanager:: Getstats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5da6b-106">This enumeration specifies which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set by [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) method.</span></span>  
  
## <a name="members"></a><span data-ttu-id="5da6b-107">成员</span><span class="sxs-lookup"><span data-stu-id="5da6b-107">Members</span></span>  
  
|<span data-ttu-id="5da6b-108">成员</span><span class="sxs-lookup"><span data-stu-id="5da6b-108">Member</span></span>|<span data-ttu-id="5da6b-109">描述</span><span class="sxs-lookup"><span data-stu-id="5da6b-109">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_COUNTS`|<span data-ttu-id="5da6b-110">记录为每一代执行垃圾回收次数。</span><span class="sxs-lookup"><span data-stu-id="5da6b-110">Records the number of garbage collections performed for each generation.</span></span>|  
|`COR_GC_MEMORYUSAGE`|<span data-ttu-id="5da6b-111">记录内存使用情况和垃圾回收量统计信息。</span><span class="sxs-lookup"><span data-stu-id="5da6b-111">Records memory usage and garbage collection size statistics.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5da6b-112">要求</span><span class="sxs-lookup"><span data-stu-id="5da6b-112">Requirements</span></span>  
 <span data-ttu-id="5da6b-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5da6b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5da6b-114">**标头：** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="5da6b-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5da6b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5da6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5da6b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5da6b-116">See also</span></span>
- [<span data-ttu-id="5da6b-117">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="5da6b-117">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="5da6b-118">承载枚举</span><span class="sxs-lookup"><span data-stu-id="5da6b-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
