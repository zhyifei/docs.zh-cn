---
title: ICorDebugNativeFrame Interface1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c923b54f791cd8ff794538d4687ca0329e62c87e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547022"
---
# <a name="icordebugnativeframe-interface1"></a><span data-ttu-id="be534-102">ICorDebugNativeFrame Interface1</span><span class="sxs-lookup"><span data-stu-id="be534-102">ICorDebugNativeFrame Interface1</span></span>
<span data-ttu-id="be534-103">ICorDebugFrame 用于本机帧的专用的实现。</span><span class="sxs-lookup"><span data-stu-id="be534-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be534-104">方法</span><span class="sxs-lookup"><span data-stu-id="be534-104">Methods</span></span>  
  
|<span data-ttu-id="be534-105">方法</span><span class="sxs-lookup"><span data-stu-id="be534-105">Method</span></span>|<span data-ttu-id="be534-106">描述</span><span class="sxs-lookup"><span data-stu-id="be534-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be534-107">CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="be534-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="be534-108">获取一个值，该值指示是否可以安全地在本机代码中设置为指定的偏移量位置的指令指针。</span><span class="sxs-lookup"><span data-stu-id="be534-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="be534-109">GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="be534-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="be534-110">获取堆栈帧的偏移量到本机代码。</span><span class="sxs-lookup"><span data-stu-id="be534-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="be534-111">GetLocalDoubleRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="be534-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="be534-112">获取一个指针指向 ICorDebugValue 表示参数或存储在两个内存寄存器中的本机框架的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="be534-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="be534-113">GetLocalMemoryRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="be534-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="be534-114">获取一个指向`ICorDebugValue`，表示本地变量，其中指定寄存器中存储的低位，在指定的内存地址上存储的高位的值。</span><span class="sxs-lookup"><span data-stu-id="be534-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="be534-115">GetLocalMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="be534-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="be534-116">获取一个指向`ICorDebugValue`，表示存储在指定的内存地址将本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="be534-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="be534-117">GetLocalRegisterMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="be534-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="be534-118">获取一个指向`ICorDebugValue`，表示本地变量，其中指定寄存器中存储的高位，在指定的内存地址上存储的低位的值</span><span class="sxs-lookup"><span data-stu-id="be534-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="be534-119">GetLocalRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="be534-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="be534-120">获取一个指向`ICorDebugValue`，表示参数或本地存储在指定的本机寄存器变量的值。</span><span class="sxs-lookup"><span data-stu-id="be534-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="be534-121">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="be534-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="be534-122">获取一个指向[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) ，表示为此参数设置的寄存器`ICorDebugNativeFrame`。</span><span class="sxs-lookup"><span data-stu-id="be534-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="be534-123">SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="be534-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="be534-124">在本机代码中，指令指针设置为指定的偏移量位置。</span><span class="sxs-lookup"><span data-stu-id="be534-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be534-125">备注</span><span class="sxs-lookup"><span data-stu-id="be534-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be534-126">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="be534-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be534-127">要求</span><span class="sxs-lookup"><span data-stu-id="be534-127">Requirements</span></span>  
 <span data-ttu-id="be534-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be534-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be534-129">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be534-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be534-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be534-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be534-131">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be534-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be534-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="be534-132">See also</span></span>
- [<span data-ttu-id="be534-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="be534-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
