---
title: ICorDebugNativeFrame 接口
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
ms.openlocfilehash: 41ac0b29ade2f78b893df72e8a17624373f6dd78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792790"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="4e8e5-102">ICorDebugNativeFrame 接口</span><span class="sxs-lookup"><span data-stu-id="4e8e5-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="4e8e5-103">用于本机帧的 ICorDebugFrame 的专用实现。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4e8e5-104">方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-104">Methods</span></span>  
  
|<span data-ttu-id="4e8e5-105">方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-105">Method</span></span>|<span data-ttu-id="4e8e5-106">描述</span><span class="sxs-lookup"><span data-stu-id="4e8e5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4e8e5-107">CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-107">CanSetIP Method</span></span>](icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="4e8e5-108">获取一个值，该值指示是否可以安全地将指令指针设置为本机代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="4e8e5-109">GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-109">GetIP Method</span></span>](icordebugnativeframe-getip-method.md)|<span data-ttu-id="4e8e5-110">获取堆栈帧到本机代码的偏移量。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="4e8e5-111">GetLocalDoubleRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-111">GetLocalDoubleRegisterValue Method</span></span>](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="4e8e5-112">获取一个指向 ICorDebugValue 的指针，该指针表示存储在本机帧的两个内存寄存器中的参数或局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="4e8e5-113">GetLocalMemoryRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-113">GetLocalMemoryRegisterValue Method</span></span>](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="4e8e5-114">获取一个指向 `ICorDebugValue` 的指针，该指针表示本地变量的值，其中低位存储在指定的寄存器中，高位存储在指定的内存地址。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="4e8e5-115">GetLocalMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-115">GetLocalMemoryValue Method</span></span>](icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="4e8e5-116">获取一个指向 `ICorDebugValue` 的指针，该指针表示存储在指定内存地址中的局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="4e8e5-117">GetLocalRegisterMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-117">GetLocalRegisterMemoryValue Method</span></span>](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="4e8e5-118">获取一个指向 `ICorDebugValue` 的指针，该指针表示本地变量的值，其中高位存储在指定的寄存器中，低位存储在指定的内存地址</span><span class="sxs-lookup"><span data-stu-id="4e8e5-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="4e8e5-119">GetLocalRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-119">GetLocalRegisterValue Method</span></span>](icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="4e8e5-120">获取一个指向 `ICorDebugValue` 的指针，该指针表示存储在指定本机寄存器中的参数值或本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="4e8e5-121">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-121">GetRegisterSet Method</span></span>](icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="4e8e5-122">获取一个指针，该指针指向表示此 `ICorDebugNativeFrame` 的注册集的 [ICorDebugRegisterSet](icordebugregisterset-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-122">Gets a pointer to an [ICorDebugRegisterSet](icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="4e8e5-123">SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="4e8e5-123">SetIP Method</span></span>](icordebugnativeframe-setip-method.md)|<span data-ttu-id="4e8e5-124">将指令指针设置为本机代码中的指定偏移位置。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e8e5-125">备注</span><span class="sxs-lookup"><span data-stu-id="4e8e5-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4e8e5-126">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e8e5-127">需求</span><span class="sxs-lookup"><span data-stu-id="4e8e5-127">Requirements</span></span>  
 <span data-ttu-id="4e8e5-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e8e5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e8e5-129">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e8e5-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e8e5-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e8e5-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e8e5-131">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e8e5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8e5-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e8e5-132">See also</span></span>

- [<span data-ttu-id="4e8e5-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="4e8e5-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
