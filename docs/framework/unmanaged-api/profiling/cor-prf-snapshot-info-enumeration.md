---
title: "COR_PRF_SNAPSHOT_INFO 枚举"
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
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4573ec44253b1b0f26ae62591db149f0447d3935
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="02be7-102">COR_PRF_SNAPSHOT_INFO 枚举</span><span class="sxs-lookup"><span data-stu-id="02be7-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="02be7-103">指定要传递的数据与探查器的每次调用中的堆栈快照的备份多少[StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="02be7-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02be7-104">语法</span><span class="sxs-lookup"><span data-stu-id="02be7-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="02be7-105">成员</span><span class="sxs-lookup"><span data-stu-id="02be7-105">Members</span></span>  
  
|<span data-ttu-id="02be7-106">成员</span><span class="sxs-lookup"><span data-stu-id="02be7-106">Members</span></span>|<span data-ttu-id="02be7-107">描述</span><span class="sxs-lookup"><span data-stu-id="02be7-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="02be7-108">指示值，必须为所有传递`StackSnapshotCallback`参数，除`context`参数。</span><span class="sxs-lookup"><span data-stu-id="02be7-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="02be7-109">指示值，必须为所有传递`StackSnapshotCallback`参数，包括`context`参数。</span><span class="sxs-lookup"><span data-stu-id="02be7-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="02be7-110">指示将使用更简单、 备用堆栈审核的算法。</span><span class="sxs-lookup"><span data-stu-id="02be7-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02be7-111">备注</span><span class="sxs-lookup"><span data-stu-id="02be7-111">Remarks</span></span>  
 <span data-ttu-id="02be7-112">通过提供的值`COR_PRF_SNAPSHOT_INFO`枚举作为参数传递给[DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="02be7-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02be7-113">惠?</span><span class="sxs-lookup"><span data-stu-id="02be7-113">Requirements</span></span>  
 <span data-ttu-id="02be7-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02be7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02be7-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="02be7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="02be7-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02be7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02be7-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02be7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02be7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="02be7-118">See Also</span></span>  
 [<span data-ttu-id="02be7-119">DoStackSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="02be7-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="02be7-120">分析枚举</span><span class="sxs-lookup"><span data-stu-id="02be7-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
