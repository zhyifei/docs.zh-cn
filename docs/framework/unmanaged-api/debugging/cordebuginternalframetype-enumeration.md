---
title: CorDebugInternalFrameType 枚举
ms.date: 03/30/2017
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
ms.openlocfilehash: 2be827e12db765485ee889d6a4a19a982dad5d54
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778366"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="9f7d6-102">CorDebugInternalFrameType 枚举</span><span class="sxs-lookup"><span data-stu-id="9f7d6-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="9f7d6-103">标识堆栈帧的类型。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="9f7d6-104">此枚举由[ICorDebugInternalFrame：： GetFrameType](icordebuginternalframe-getframetype-method.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f7d6-105">语法</span><span class="sxs-lookup"><span data-stu-id="9f7d6-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="9f7d6-106">Members</span><span class="sxs-lookup"><span data-stu-id="9f7d6-106">Members</span></span>  
  
|<span data-ttu-id="9f7d6-107">成员</span><span class="sxs-lookup"><span data-stu-id="9f7d6-107">Member</span></span>|<span data-ttu-id="9f7d6-108">描述</span><span class="sxs-lookup"><span data-stu-id="9f7d6-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="9f7d6-109">Null 值。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-109">A null value.</span></span> <span data-ttu-id="9f7d6-110">`ICorDebugInternalFrame::GetFrameType` 方法从不返回此值。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="9f7d6-111">托管到非托管的存根帧。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="9f7d6-112">非托管到托管的存根帧。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="9f7d6-113">应用程序域之间的转换。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="9f7d6-114">轻量方法调用。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="9f7d6-115">函数计算的开头。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="9f7d6-116">公共语言运行时的内部调用。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="9f7d6-117">类初始化的开头。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="9f7d6-118">引发的异常。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="9f7d6-119">用于代码访问安全性的帧。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="9f7d6-120">运行时对方法进行 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f7d6-121">需求</span><span class="sxs-lookup"><span data-stu-id="9f7d6-121">Requirements</span></span>  
 <span data-ttu-id="9f7d6-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f7d6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f7d6-123">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f7d6-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f7d6-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f7d6-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f7d6-125">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f7d6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f7d6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f7d6-126">See also</span></span>

- [<span data-ttu-id="9f7d6-127">调试枚举</span><span class="sxs-lookup"><span data-stu-id="9f7d6-127">Debugging Enumerations</span></span>](debugging-enumerations.md)
