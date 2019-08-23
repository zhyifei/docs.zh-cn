---
title: ICorDebugRegisterSet 接口
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet
helpviewer_keywords:
- ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: d3d9676d-0b87-4bc3-b679-7bbc7a186c88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6419a525a8a542295751defb97e67a83220730b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965067"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="c66f4-102">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="c66f4-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="c66f4-103">表示在当前正在执行代码的计算机上可用的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="c66f4-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c66f4-104">方法</span><span class="sxs-lookup"><span data-stu-id="c66f4-104">Methods</span></span>  
  
|<span data-ttu-id="c66f4-105">方法</span><span class="sxs-lookup"><span data-stu-id="c66f4-105">Method</span></span>|<span data-ttu-id="c66f4-106">描述</span><span class="sxs-lookup"><span data-stu-id="c66f4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c66f4-107">GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="c66f4-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="c66f4-108">获取位掩码指定的每个寄存器的值 (在当前正在执行代码的计算机上)。</span><span class="sxs-lookup"><span data-stu-id="c66f4-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="c66f4-109">GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="c66f4-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="c66f4-110">获取一个位掩码, 指示此`ICorDebugRegisterSet`中的哪些寄存器当前可用。</span><span class="sxs-lookup"><span data-stu-id="c66f4-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="c66f4-111">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="c66f4-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="c66f4-112">获取当前线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="c66f4-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="c66f4-113">SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="c66f4-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="c66f4-114">未实现 .NET Framework 版本2.0。</span><span class="sxs-lookup"><span data-stu-id="c66f4-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="c66f4-115">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="c66f4-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="c66f4-116">未实现 2.0 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="c66f4-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c66f4-117">备注</span><span class="sxs-lookup"><span data-stu-id="c66f4-117">Remarks</span></span>  
 <span data-ttu-id="c66f4-118">`ICorDebugRegisterSet`接口仅支持32位寄存器。</span><span class="sxs-lookup"><span data-stu-id="c66f4-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="c66f4-119">使用需要额外注册的平台 (如 IA-64) 上的[ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c66f4-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c66f4-120">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="c66f4-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c66f4-121">要求</span><span class="sxs-lookup"><span data-stu-id="c66f4-121">Requirements</span></span>  
 <span data-ttu-id="c66f4-122">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c66f4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c66f4-123">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="c66f4-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c66f4-124">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c66f4-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c66f4-125">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c66f4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c66f4-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c66f4-126">See also</span></span>

- [<span data-ttu-id="c66f4-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="c66f4-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c66f4-128">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="c66f4-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
