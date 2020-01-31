---
title: COR_PRF_SNAPSHOT_INFO 枚举
ms.date: 03/30/2017
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
ms.openlocfilehash: 97bf3e69a8ea155d53479ba6f61988e56e3bd396
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867017"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="0f084-102">COR_PRF_SNAPSHOT_INFO 枚举</span><span class="sxs-lookup"><span data-stu-id="0f084-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="0f084-103">指定在每次调用探查器的[StackSnapshotCallback](stacksnapshotcallback-function.md)函数时要通过堆栈快照传递回多少数据。</span><span class="sxs-lookup"><span data-stu-id="0f084-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f084-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f084-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="0f084-105">Members</span><span class="sxs-lookup"><span data-stu-id="0f084-105">Members</span></span>  
  
|<span data-ttu-id="0f084-106">Members</span><span class="sxs-lookup"><span data-stu-id="0f084-106">Members</span></span>|<span data-ttu-id="0f084-107">描述</span><span class="sxs-lookup"><span data-stu-id="0f084-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="0f084-108">指示必须为除 `context` 参数之外的所有 `StackSnapshotCallback` 参数传递值。</span><span class="sxs-lookup"><span data-stu-id="0f084-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="0f084-109">指示必须为所有 `StackSnapshotCallback` 参数（包括 `context` 参数）传递值。</span><span class="sxs-lookup"><span data-stu-id="0f084-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="0f084-110">指示将使用更简单的替代堆栈遍历算法。</span><span class="sxs-lookup"><span data-stu-id="0f084-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f084-111">备注</span><span class="sxs-lookup"><span data-stu-id="0f084-111">Remarks</span></span>  
 <span data-ttu-id="0f084-112">`COR_PRF_SNAPSHOT_INFO` 枚举提供的值将作为参数传递给[DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0f084-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f084-113">需求</span><span class="sxs-lookup"><span data-stu-id="0f084-113">Requirements</span></span>  
 <span data-ttu-id="0f084-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f084-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f084-115">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f084-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f084-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f084-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f084-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f084-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f084-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f084-118">See also</span></span>

- [<span data-ttu-id="0f084-119">DoStackSnapshot 方法</span><span class="sxs-lookup"><span data-stu-id="0f084-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="0f084-120">分析枚举</span><span class="sxs-lookup"><span data-stu-id="0f084-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
