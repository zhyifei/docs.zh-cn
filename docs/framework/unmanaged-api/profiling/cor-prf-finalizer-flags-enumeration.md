---
title: COR_PRF_FINALIZER_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_FINALIZER_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FINALIZER_FLAGS
helpviewer_keywords:
- COR_PRF_FINALIZER_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 297d7721-3911-4f36-9e34-d9da0c33e22a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5037f335e8d66c341d70d91d955a1ac7571b823
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123755"
---
# <a name="corprffinalizerflags-enumeration"></a><span data-ttu-id="188ee-102">COR_PRF_FINALIZER_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="188ee-102">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>
<span data-ttu-id="188ee-103">描述对象的终结器。</span><span class="sxs-lookup"><span data-stu-id="188ee-103">Describes the finalizer for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="188ee-104">语法</span><span class="sxs-lookup"><span data-stu-id="188ee-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FINALIZER_CRITICAL = 0x1  
} COR_PRF_FINALIZER_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="188ee-105">成员</span><span class="sxs-lookup"><span data-stu-id="188ee-105">Members</span></span>  
  
|<span data-ttu-id="188ee-106">成员</span><span class="sxs-lookup"><span data-stu-id="188ee-106">Member</span></span>|<span data-ttu-id="188ee-107">描述</span><span class="sxs-lookup"><span data-stu-id="188ee-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FINALIZER_CRITICAL`|<span data-ttu-id="188ee-108">终结器至关重要。</span><span class="sxs-lookup"><span data-stu-id="188ee-108">The finalizer is critical.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="188ee-109">备注</span><span class="sxs-lookup"><span data-stu-id="188ee-109">Remarks</span></span>  
 <span data-ttu-id="188ee-110">`COR_PRF_FINALIZER_FLAGS`枚举由[ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)方法，用于描述一个对象的终结器。</span><span class="sxs-lookup"><span data-stu-id="188ee-110">The `COR_PRF_FINALIZER_FLAGS` enumeration is used by the [ICorProfilerCallback2::FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) method to describe the finalizer for an object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="188ee-111">要求</span><span class="sxs-lookup"><span data-stu-id="188ee-111">Requirements</span></span>  
 <span data-ttu-id="188ee-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="188ee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="188ee-113">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="188ee-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="188ee-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="188ee-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="188ee-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="188ee-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="188ee-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="188ee-116">See also</span></span>

- [<span data-ttu-id="188ee-117">分析枚举</span><span class="sxs-lookup"><span data-stu-id="188ee-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
