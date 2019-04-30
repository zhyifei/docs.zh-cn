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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d59450540b680d6004c47fd646769e38c806024
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994612"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="0bdad-102">ICorDebugNativeFrame 接口</span><span class="sxs-lookup"><span data-stu-id="0bdad-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="0bdad-103">ICorDebugFrame 用于本机帧的专用的实现。</span><span class="sxs-lookup"><span data-stu-id="0bdad-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0bdad-104">方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-104">Methods</span></span>  
  
|<span data-ttu-id="0bdad-105">方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-105">Method</span></span>|<span data-ttu-id="0bdad-106">描述</span><span class="sxs-lookup"><span data-stu-id="0bdad-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0bdad-107">CanSetIP 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="0bdad-108">获取一个值，该值指示是否可以安全地在本机代码中设置为指定的偏移量位置的指令指针。</span><span class="sxs-lookup"><span data-stu-id="0bdad-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="0bdad-109">GetIP 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="0bdad-110">获取堆栈帧的偏移量到本机代码。</span><span class="sxs-lookup"><span data-stu-id="0bdad-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="0bdad-111">GetLocalDoubleRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="0bdad-112">获取一个指针指向 ICorDebugValue 表示参数或存储在两个内存寄存器中的本机框架的本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="0bdad-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="0bdad-113">GetLocalMemoryRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="0bdad-114">获取一个指向`ICorDebugValue`，表示本地变量，其中指定寄存器中存储的低位，在指定的内存地址上存储的高位的值。</span><span class="sxs-lookup"><span data-stu-id="0bdad-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="0bdad-115">GetLocalMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="0bdad-116">获取一个指向`ICorDebugValue`，表示存储在指定的内存地址将本地变量的值。</span><span class="sxs-lookup"><span data-stu-id="0bdad-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="0bdad-117">GetLocalRegisterMemoryValue 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="0bdad-118">获取一个指向`ICorDebugValue`，表示本地变量，其中指定寄存器中存储的高位，在指定的内存地址上存储的低位的值</span><span class="sxs-lookup"><span data-stu-id="0bdad-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="0bdad-119">GetLocalRegisterValue 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="0bdad-120">获取一个指向`ICorDebugValue`，表示参数或本地存储在指定的本机寄存器变量的值。</span><span class="sxs-lookup"><span data-stu-id="0bdad-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="0bdad-121">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="0bdad-122">获取一个指向[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) ，表示为此参数设置的寄存器`ICorDebugNativeFrame`。</span><span class="sxs-lookup"><span data-stu-id="0bdad-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="0bdad-123">SetIP 方法</span><span class="sxs-lookup"><span data-stu-id="0bdad-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="0bdad-124">在本机代码中，指令指针设置为指定的偏移量位置。</span><span class="sxs-lookup"><span data-stu-id="0bdad-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bdad-125">备注</span><span class="sxs-lookup"><span data-stu-id="0bdad-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bdad-126">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="0bdad-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bdad-127">要求</span><span class="sxs-lookup"><span data-stu-id="0bdad-127">Requirements</span></span>  
 <span data-ttu-id="0bdad-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bdad-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bdad-129">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bdad-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bdad-130">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bdad-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bdad-131">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bdad-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdad-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bdad-132">See also</span></span>

- [<span data-ttu-id="0bdad-133">调试接口</span><span class="sxs-lookup"><span data-stu-id="0bdad-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
