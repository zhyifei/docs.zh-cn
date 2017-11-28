---
title: "“Cor调试代码调用类型”枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCodeInvokeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d46a47c7c655a960224bb836be0ea37cd07c8038
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="8e43b-102">“Cor调试代码调用类型”枚举</span><span class="sxs-lookup"><span data-stu-id="8e43b-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="8e43b-103">描述导出函数如何调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="8e43b-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e43b-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e43b-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="8e43b-105">成员</span><span class="sxs-lookup"><span data-stu-id="8e43b-105">Members</span></span>  
  
|<span data-ttu-id="8e43b-106">成员</span><span class="sxs-lookup"><span data-stu-id="8e43b-106">Member</span></span>|<span data-ttu-id="8e43b-107">描述</span><span class="sxs-lookup"><span data-stu-id="8e43b-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="8e43b-108">如果任何托管代码遭该方法调用，稍后将必须接受显式事件或断点定位。</span><span class="sxs-lookup"><span data-stu-id="8e43b-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="8e43b-109">--或者--</span><span class="sxs-lookup"><span data-stu-id="8e43b-109">--or--</span></span><br /><br /> <span data-ttu-id="8e43b-110">我们或许只能错过该方法调用的一些托管代码，因为很难停在上面。</span><span class="sxs-lookup"><span data-stu-id="8e43b-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="8e43b-111">--或者--</span><span class="sxs-lookup"><span data-stu-id="8e43b-111">--or--</span></span><br /><br /> <span data-ttu-id="8e43b-112">该方法可能无法调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="8e43b-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="8e43b-113">该方法可通过返回指令调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="8e43b-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="8e43b-114">在下一个托管代码处应跳出。</span><span class="sxs-lookup"><span data-stu-id="8e43b-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="8e43b-115">该方法可通过尾调调用托管代码。</span><span class="sxs-lookup"><span data-stu-id="8e43b-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="8e43b-116">在托管代码处应单步执行所有调用指令。</span><span class="sxs-lookup"><span data-stu-id="8e43b-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e43b-117">备注</span><span class="sxs-lookup"><span data-stu-id="8e43b-117">Remarks</span></span>  
 <span data-ttu-id="8e43b-118">此枚举由[icordebugprocess6:: Getexportstepinfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md)方法以提供信息单步执行托管代码。</span><span class="sxs-lookup"><span data-stu-id="8e43b-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e43b-119">此枚举仅用于 .NET Native 调试方案。</span><span class="sxs-lookup"><span data-stu-id="8e43b-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e43b-120">要求</span><span class="sxs-lookup"><span data-stu-id="8e43b-120">Requirements</span></span>  
 <span data-ttu-id="8e43b-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e43b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e43b-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e43b-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e43b-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e43b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e43b-124">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e43b-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e43b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e43b-125">See Also</span></span>  
 [<span data-ttu-id="8e43b-126">调试枚举</span><span class="sxs-lookup"><span data-stu-id="8e43b-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="8e43b-127">调试</span><span class="sxs-lookup"><span data-stu-id="8e43b-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
