---
title: ICorDebugILFrame 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c60d7685de1e9a1d4f631ad1fba53b981829f58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988580"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="887be-102">ICorDebugILFrame 接口</span><span class="sxs-lookup"><span data-stu-id="887be-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="887be-103">表示 Microsoft 中间语言 (MSIL) 代码的堆栈帧。</span><span class="sxs-lookup"><span data-stu-id="887be-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="887be-104">此接口是 ICorDebugFrame 接口子类。</span><span class="sxs-lookup"><span data-stu-id="887be-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="887be-105">方法</span><span class="sxs-lookup"><span data-stu-id="887be-105">Methods</span></span>  
  
|<span data-ttu-id="887be-106">方法</span><span class="sxs-lookup"><span data-stu-id="887be-106">Method</span></span>|<span data-ttu-id="887be-107">描述</span><span class="sxs-lookup"><span data-stu-id="887be-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="887be-108">CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="887be-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="887be-109">获取一个值，该值指示是否可以安全地将指令指针设置为指定的偏移量位置。</span><span class="sxs-lookup"><span data-stu-id="887be-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="887be-110">EnumerateArguments 方法</span><span class="sxs-lookup"><span data-stu-id="887be-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="887be-111">在此范围内的自变量中获取一个枚举器。</span><span class="sxs-lookup"><span data-stu-id="887be-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="887be-112">EnumerateLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="887be-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="887be-113">获取在此帧中局部变量的枚举数。</span><span class="sxs-lookup"><span data-stu-id="887be-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="887be-114">GetArgument 方法</span><span class="sxs-lookup"><span data-stu-id="887be-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="887be-115">获取此 MSIL 堆栈帧中的指定参数的值。</span><span class="sxs-lookup"><span data-stu-id="887be-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="887be-116">GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="887be-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="887be-117">获取指令指针的值和一个说明如何获取指令指针的值的按位组合值。</span><span class="sxs-lookup"><span data-stu-id="887be-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="887be-118">GetLocalVariable 方法</span><span class="sxs-lookup"><span data-stu-id="887be-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="887be-119">获取此 MSIL 堆栈帧中指定的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="887be-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="887be-120">GetStackDepth 方法</span><span class="sxs-lookup"><span data-stu-id="887be-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="887be-121">未实现。</span><span class="sxs-lookup"><span data-stu-id="887be-121">Not implemented.</span></span>|  
|[<span data-ttu-id="887be-122">GetStackValue 方法</span><span class="sxs-lookup"><span data-stu-id="887be-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="887be-123">未实现。</span><span class="sxs-lookup"><span data-stu-id="887be-123">Not implemented.</span></span>|  
|[<span data-ttu-id="887be-124">SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="887be-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="887be-125">将指令指针设置为 MSIL 代码中的指定偏移量位置。</span><span class="sxs-lookup"><span data-stu-id="887be-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="887be-126">备注</span><span class="sxs-lookup"><span data-stu-id="887be-126">Remarks</span></span>  
 <span data-ttu-id="887be-127">`ICorDebugILFrame`接口是专用的 ICorDebugFrame 接口。</span><span class="sxs-lookup"><span data-stu-id="887be-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="887be-128">使用 MSIL 代码帧或实时 (JIT) 编译的帧。</span><span class="sxs-lookup"><span data-stu-id="887be-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="887be-129">JIT 编译帧实现`ICorDebugILFrame`接口和 ICorDebugNativeFrame 接口。</span><span class="sxs-lookup"><span data-stu-id="887be-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="887be-130">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="887be-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="887be-131">要求</span><span class="sxs-lookup"><span data-stu-id="887be-131">Requirements</span></span>  
 <span data-ttu-id="887be-132">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="887be-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="887be-133">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="887be-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="887be-134">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="887be-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="887be-135">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="887be-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="887be-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="887be-136">See also</span></span>

- [<span data-ttu-id="887be-137">调试接口</span><span class="sxs-lookup"><span data-stu-id="887be-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
