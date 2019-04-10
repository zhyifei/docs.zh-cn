---
title: COR_PRF_CODEGEN_FLAGS 枚举
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 321318b63368ed6e57d235cf97d94485352f8686
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211356"
---
# <a name="corprfcodegenflags-enumeration"></a><span data-ttu-id="7a72f-102">COR_PRF_CODEGEN_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="7a72f-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="7a72f-103">定义可以使用设置的代码生成标志[icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7a72f-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a72f-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a72f-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="7a72f-105">成员</span><span class="sxs-lookup"><span data-stu-id="7a72f-105">Members</span></span>  
  
|<span data-ttu-id="7a72f-106">成员</span><span class="sxs-lookup"><span data-stu-id="7a72f-106">Member</span></span>|<span data-ttu-id="7a72f-107">描述</span><span class="sxs-lookup"><span data-stu-id="7a72f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="7a72f-108">没有函数将内联到此函数的正文。</span><span class="sxs-lookup"><span data-stu-id="7a72f-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="7a72f-109">但是，该函数本身可能内嵌到其调用方。</span><span class="sxs-lookup"><span data-stu-id="7a72f-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="7a72f-110">将此函数的正文的禁用所有优化。</span><span class="sxs-lookup"><span data-stu-id="7a72f-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="7a72f-111">但是，该函数本身仍可能内嵌到其调用方。</span><span class="sxs-lookup"><span data-stu-id="7a72f-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a72f-112">备注</span><span class="sxs-lookup"><span data-stu-id="7a72f-112">Remarks</span></span>  
 <span data-ttu-id="7a72f-113">`COR_PRF_CODEGEN_FLAGS`枚举由[icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)方法，以使探查器来控制 JIT 重新编译函数的代码生成。</span><span class="sxs-lookup"><span data-stu-id="7a72f-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a72f-114">要求</span><span class="sxs-lookup"><span data-stu-id="7a72f-114">Requirements</span></span>  
 <span data-ttu-id="7a72f-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a72f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a72f-116">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a72f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a72f-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a72f-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7a72f-118">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="7a72f-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7a72f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a72f-119">See also</span></span>

- [<span data-ttu-id="7a72f-120">分析枚举</span><span class="sxs-lookup"><span data-stu-id="7a72f-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
