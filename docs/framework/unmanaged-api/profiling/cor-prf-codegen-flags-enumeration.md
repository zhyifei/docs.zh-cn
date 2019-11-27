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
ms.openlocfilehash: c49bdcb9345960bce018cefd4443948f997c7267
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428361"
---
# <a name="cor_prf_codegen_flags-enumeration"></a><span data-ttu-id="cd43f-102">COR_PRF_CODEGEN_FLAGS 枚举</span><span class="sxs-lookup"><span data-stu-id="cd43f-102">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>
<span data-ttu-id="cd43f-103">定义可以用[ICorProfilerFunctionControl：： SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)方法设置的代码生成标志。</span><span class="sxs-lookup"><span data-stu-id="cd43f-103">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd43f-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd43f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="cd43f-105">Members</span><span class="sxs-lookup"><span data-stu-id="cd43f-105">Members</span></span>  
  
|<span data-ttu-id="cd43f-106">成员</span><span class="sxs-lookup"><span data-stu-id="cd43f-106">Member</span></span>|<span data-ttu-id="cd43f-107">说明</span><span class="sxs-lookup"><span data-stu-id="cd43f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|<span data-ttu-id="cd43f-108">不会将任何函数内联到此函数的主体中。</span><span class="sxs-lookup"><span data-stu-id="cd43f-108">No functions will be inlined into this function’s body.</span></span> <span data-ttu-id="cd43f-109">但是，函数本身可能会内联到其调用方。</span><span class="sxs-lookup"><span data-stu-id="cd43f-109">However, the function itself may be inlined into its callers.</span></span>|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|<span data-ttu-id="cd43f-110">对于此函数的主体，将禁用所有优化。</span><span class="sxs-lookup"><span data-stu-id="cd43f-110">All optimizations will be disabled for this function’s body.</span></span> <span data-ttu-id="cd43f-111">但是，该函数本身可能仍会内联到其调用方。</span><span class="sxs-lookup"><span data-stu-id="cd43f-111">However, the function itself may still be inlined into its callers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd43f-112">备注</span><span class="sxs-lookup"><span data-stu-id="cd43f-112">Remarks</span></span>  
 <span data-ttu-id="cd43f-113">[ICorProfilerFunctionControl：： SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)方法使用 `COR_PRF_CODEGEN_FLAGS` 枚举，以使探查器能够控制 JIT 重新编译函数的代码生成。</span><span class="sxs-lookup"><span data-stu-id="cd43f-113">The `COR_PRF_CODEGEN_FLAGS` enumeration is used by the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method to enable the profiler to control the code generation for the JIT-recompiled function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd43f-114">要求</span><span class="sxs-lookup"><span data-stu-id="cd43f-114">Requirements</span></span>  
 <span data-ttu-id="cd43f-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd43f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd43f-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cd43f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cd43f-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd43f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd43f-118">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd43f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd43f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd43f-119">See also</span></span>

- [<span data-ttu-id="cd43f-120">分析枚举</span><span class="sxs-lookup"><span data-stu-id="cd43f-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
