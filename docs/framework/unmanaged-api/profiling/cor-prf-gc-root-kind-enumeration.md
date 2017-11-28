---
title: "COR_PRF_GC_ROOT_KIND 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_ROOT_KIND
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_ROOT_KIND
helpviewer_keywords: COR_PRF_GC_ROOT_KIND enumeration [.NET Framework profiling]
ms.assetid: b9fb1c03-417f-41d4-aed4-02cb4ade8def
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d60b851dc16fca825526562585fbfcec76f9d20a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcrootkind-enumeration"></a><span data-ttu-id="41615-102">COR_PRF_GC_ROOT_KIND 枚举</span><span class="sxs-lookup"><span data-stu-id="41615-102">COR_PRF_GC_ROOT_KIND Enumeration</span></span>
<span data-ttu-id="41615-103">指示由公开的垃圾回收根的种类[icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)回调。</span><span class="sxs-lookup"><span data-stu-id="41615-103">Indicates the kind of garbage collection root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41615-104">语法</span><span class="sxs-lookup"><span data-stu-id="41615-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_ROOT_STACK = 1,  
    COR_PRF_GC_ROOT_FINALIZER = 2,  
    COR_PRF_GC_ROOT_HANDLE = 3,  
    COR_PRF_GC_ROOT_OTHER = 0  
} COR_PRF_GC_ROOT_KIND;  
```  
  
## <a name="members"></a><span data-ttu-id="41615-105">成员</span><span class="sxs-lookup"><span data-stu-id="41615-105">Members</span></span>  
  
|<span data-ttu-id="41615-106">成员</span><span class="sxs-lookup"><span data-stu-id="41615-106">Member</span></span>|<span data-ttu-id="41615-107">描述</span><span class="sxs-lookup"><span data-stu-id="41615-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_ROOT_STACK`|<span data-ttu-id="41615-108">根是一个变量在堆栈上。</span><span class="sxs-lookup"><span data-stu-id="41615-108">The root is a variable on the stack.</span></span>|  
|`COR_PRF_GC_ROOT_FINALIZER`|<span data-ttu-id="41615-109">根是终结器队列中的条目。</span><span class="sxs-lookup"><span data-stu-id="41615-109">The root is an entry in the finalizer queue.</span></span>|  
|`COR_PRF_GC_ROOT_HANDLE`|<span data-ttu-id="41615-110">根是垃圾回收句柄。</span><span class="sxs-lookup"><span data-stu-id="41615-110">The root is a garbage collection handle.</span></span>|  
|`COR_PRF_GC_ROOT_OTHER`|<span data-ttu-id="41615-111">未指定的根类型。</span><span class="sxs-lookup"><span data-stu-id="41615-111">The kind of root is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="41615-112">要求</span><span class="sxs-lookup"><span data-stu-id="41615-112">Requirements</span></span>  
 <span data-ttu-id="41615-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41615-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41615-114">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41615-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41615-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41615-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41615-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41615-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41615-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41615-117">See Also</span></span>  
 [<span data-ttu-id="41615-118">分析枚举</span><span class="sxs-lookup"><span data-stu-id="41615-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
