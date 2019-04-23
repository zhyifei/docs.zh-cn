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
ms.openlocfilehash: 7b0a5d80d984a3c696b178c4d8c936bd47354945
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135234"
---
# <a name="icordebugregisterset-interface"></a><span data-ttu-id="cd267-102">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="cd267-102">ICorDebugRegisterSet Interface</span></span>
<span data-ttu-id="cd267-103">表示当前正在执行代码的计算机上可用的寄存器组。</span><span class="sxs-lookup"><span data-stu-id="cd267-103">Represents the set of registers available on the computer that is currently executing code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd267-104">方法</span><span class="sxs-lookup"><span data-stu-id="cd267-104">Methods</span></span>  
  
|<span data-ttu-id="cd267-105">方法</span><span class="sxs-lookup"><span data-stu-id="cd267-105">Method</span></span>|<span data-ttu-id="cd267-106">描述</span><span class="sxs-lookup"><span data-stu-id="cd267-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd267-107">GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="cd267-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)|<span data-ttu-id="cd267-108">获取每个寄存器的值 （上当前正在执行代码的计算机） 指定的位掩码。</span><span class="sxs-lookup"><span data-stu-id="cd267-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="cd267-109">GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="cd267-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)|<span data-ttu-id="cd267-110">获取的位掩码，指示用于在此注册`ICorDebugRegisterSet`当前可用。</span><span class="sxs-lookup"><span data-stu-id="cd267-110">Gets a bit mask indicating which registers in this `ICorDebugRegisterSet` are currently available.</span></span>|  
|[<span data-ttu-id="cd267-111">GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="cd267-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getthreadcontext-method.md)|<span data-ttu-id="cd267-112">获取当前线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="cd267-112">Gets the context of the current thread.</span></span>|  
|[<span data-ttu-id="cd267-113">SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="cd267-113">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setregisters-method.md)|<span data-ttu-id="cd267-114">尚未实现对.NET Framework 2.0 版。</span><span class="sxs-lookup"><span data-stu-id="cd267-114">Not implemented for the .NET Framework version 2.0.</span></span>|  
|[<span data-ttu-id="cd267-115">SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="cd267-115">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-setthreadcontext-method.md)|<span data-ttu-id="cd267-116">尚未实现对.NET Framework 2.0。</span><span class="sxs-lookup"><span data-stu-id="cd267-116">Not implemented for the .NET Framework 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd267-117">备注</span><span class="sxs-lookup"><span data-stu-id="cd267-117">Remarks</span></span>  
 <span data-ttu-id="cd267-118">`ICorDebugRegisterSet`接口支持仅 32 位寄存器。</span><span class="sxs-lookup"><span data-stu-id="cd267-118">The `ICorDebugRegisterSet` interface supports only 32-bit registers.</span></span> <span data-ttu-id="cd267-119">使用[ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)需要其他寄存器例如 IA-64 的平台上的接口。</span><span class="sxs-lookup"><span data-stu-id="cd267-119">Use the [ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md) interface on platforms such as IA-64 that require additional registers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd267-120">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="cd267-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd267-121">要求</span><span class="sxs-lookup"><span data-stu-id="cd267-121">Requirements</span></span>  
 <span data-ttu-id="cd267-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd267-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd267-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd267-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd267-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd267-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd267-125">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd267-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd267-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd267-126">See also</span></span>

- [<span data-ttu-id="cd267-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="cd267-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cd267-128">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="cd267-128">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
