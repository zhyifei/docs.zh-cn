---
title: "ICorDebugNativeFrame 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame
helpviewer_keywords: ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edd49d745be9db0c4c5309cf5febc3ff651a860f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe-interface1"></a><span data-ttu-id="8f17b-102">ICorDebugNativeFrame 接口 1</span><span class="sxs-lookup"><span data-stu-id="8f17b-102">ICorDebugNativeFrame Interface1</span></span>
<span data-ttu-id="8f17b-103">ICorDebugFrame 用于本机帧的专用的实现。</span><span class="sxs-lookup"><span data-stu-id="8f17b-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f17b-104">方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-104">Methods</span></span>  
  
|<span data-ttu-id="8f17b-105">方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-105">Method</span></span>|<span data-ttu-id="8f17b-106">描述</span><span class="sxs-lookup"><span data-stu-id="8f17b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f17b-107">CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="8f17b-108">获取一个值，该值指示是否可以安全地将指令指针设置为指定的偏移量位置，本机代码中。</span><span class="sxs-lookup"><span data-stu-id="8f17b-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="8f17b-109">GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="8f17b-110">获取到本机代码的堆栈帧的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8f17b-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="8f17b-111">GetLocalDoubleRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="8f17b-112">获取一个指针指向 ICorDebugValue 表示自变量或存储在两个内存寄存器中的本机框架的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="8f17b-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="8f17b-113">GetLocalMemoryRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="8f17b-114">获取一个指向`ICorDebugValue`，表示本地变量，其中的低位存储在指定的寄存器，高位存储在指定的内存地址的值。</span><span class="sxs-lookup"><span data-stu-id="8f17b-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="8f17b-115">GetLocalMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="8f17b-116">获取一个指向`ICorDebugValue`，表示存储在指定的内存地址的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="8f17b-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="8f17b-117">GetLocalRegisterMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="8f17b-118">获取一个指向`ICorDebugValue`，表示本地变量，其中的高位存储在指定的寄存器，存储在指定的内存地址的低位的值</span><span class="sxs-lookup"><span data-stu-id="8f17b-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="8f17b-119">GetLocalRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="8f17b-120">获取一个指向`ICorDebugValue`，表示的自变量或局部变量存储在指定的本机寄存器的值。</span><span class="sxs-lookup"><span data-stu-id="8f17b-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="8f17b-121">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="8f17b-122">获取一个指向[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)表示为此参数设置的寄存器`ICorDebugNativeFrame`。</span><span class="sxs-lookup"><span data-stu-id="8f17b-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="8f17b-123">SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="8f17b-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="8f17b-124">将指令指针设置为指定的偏移量位置，在本机代码中。</span><span class="sxs-lookup"><span data-stu-id="8f17b-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f17b-125">备注</span><span class="sxs-lookup"><span data-stu-id="8f17b-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f17b-126">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8f17b-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f17b-127">惠?</span><span class="sxs-lookup"><span data-stu-id="8f17b-127">Requirements</span></span>  
 <span data-ttu-id="8f17b-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f17b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f17b-129">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f17b-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f17b-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f17b-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f17b-131">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f17b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f17b-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f17b-132">See Also</span></span>  
 [<span data-ttu-id="8f17b-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="8f17b-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
