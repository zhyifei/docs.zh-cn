---
title: "CorDebugInternalFrameType 枚举"
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
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65e970563ec3958deddb0aa1d89e10b0da70f0a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="7f541-102">CorDebugInternalFrameType 枚举</span><span class="sxs-lookup"><span data-stu-id="7f541-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="7f541-103">标识堆栈帧的类型。</span><span class="sxs-lookup"><span data-stu-id="7f541-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="7f541-104">此枚举由[icordebuginternalframe:: Getframetype](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7f541-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f541-105">语法</span><span class="sxs-lookup"><span data-stu-id="7f541-105">Syntax</span></span>  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="7f541-106">成员</span><span class="sxs-lookup"><span data-stu-id="7f541-106">Members</span></span>  
  
|<span data-ttu-id="7f541-107">成员</span><span class="sxs-lookup"><span data-stu-id="7f541-107">Member</span></span>|<span data-ttu-id="7f541-108">描述</span><span class="sxs-lookup"><span data-stu-id="7f541-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="7f541-109">Null 值。</span><span class="sxs-lookup"><span data-stu-id="7f541-109">A null value.</span></span> <span data-ttu-id="7f541-110">`ICorDebugInternalFrame::GetFrameType`方法永远不会返回此值。</span><span class="sxs-lookup"><span data-stu-id="7f541-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="7f541-111">托管到非托管存根 （stub） 框架。</span><span class="sxs-lookup"><span data-stu-id="7f541-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="7f541-112">非托管到托管存根 （stub） 帧。</span><span class="sxs-lookup"><span data-stu-id="7f541-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="7f541-113">应用程序域之间的转换。</span><span class="sxs-lookup"><span data-stu-id="7f541-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="7f541-114">轻量方法调用。</span><span class="sxs-lookup"><span data-stu-id="7f541-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="7f541-115">函数计算的开始。</span><span class="sxs-lookup"><span data-stu-id="7f541-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="7f541-116">内部调入公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="7f541-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="7f541-117">类初始化的开始日期。</span><span class="sxs-lookup"><span data-stu-id="7f541-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="7f541-118">引发异常。</span><span class="sxs-lookup"><span data-stu-id="7f541-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="7f541-119">用于代码访问安全性的帧。</span><span class="sxs-lookup"><span data-stu-id="7f541-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="7f541-120">运行时 JIT 编译的方法。</span><span class="sxs-lookup"><span data-stu-id="7f541-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f541-121">惠?</span><span class="sxs-lookup"><span data-stu-id="7f541-121">Requirements</span></span>  
 <span data-ttu-id="7f541-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f541-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f541-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7f541-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7f541-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f541-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f541-125">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f541-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f541-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f541-126">See Also</span></span>  
 [<span data-ttu-id="7f541-127">调试枚举</span><span class="sxs-lookup"><span data-stu-id="7f541-127">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
