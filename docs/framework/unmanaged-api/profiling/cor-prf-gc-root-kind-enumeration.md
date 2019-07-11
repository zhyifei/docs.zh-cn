---
title: COR_PRF_GC_ROOT_KIND 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_ROOT_KIND
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_ROOT_KIND
helpviewer_keywords:
- COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b7a4c8dfc9e082b29d462b835886d6bf252bb39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753663"
---
# <a name="corprfgcrootkind-enumeration"></a><span data-ttu-id="f2e53-102">COR_PRF_GC_ROOT_KIND 枚举</span><span class="sxs-lookup"><span data-stu-id="f2e53-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="f2e53-103">指示由公开的垃圾回收根的种类[ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="f2e53-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2e53-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2e53-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="f2e53-105">成员</span><span class="sxs-lookup"><span data-stu-id="f2e53-105">Members</span></span>  
  
|<span data-ttu-id="f2e53-106">成员</span><span class="sxs-lookup"><span data-stu-id="f2e53-106">Member</span></span>|<span data-ttu-id="f2e53-107">描述</span><span class="sxs-lookup"><span data-stu-id="f2e53-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="f2e53-108">根是一个变量在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="f2e53-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="f2e53-109">根是终结器队列中的条目。</span><span class="sxs-lookup"><span data-stu-id="f2e53-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="f2e53-110">根是垃圾回收句柄。</span><span class="sxs-lookup"><span data-stu-id="f2e53-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="f2e53-111">未指定根类型。</span><span class="sxs-lookup"><span data-stu-id="f2e53-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2e53-112">要求</span><span class="sxs-lookup"><span data-stu-id="f2e53-112">Requirements</span></span>  
 <span data-ttu-id="f2e53-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f2e53-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2e53-114">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2e53-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2e53-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2e53-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2e53-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2e53-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e53-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2e53-117">See also</span></span>

- [<span data-ttu-id="f2e53-118">分析枚举</span><span class="sxs-lookup"><span data-stu-id="f2e53-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
