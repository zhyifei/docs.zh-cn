---
title: ICorDebugRegisterSet2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: 47beba867cd2246c98cb02c3a563b948c15f5154
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131317"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="746a7-102">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="746a7-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="746a7-103">为包含64个以上注册的硬件平台扩展了[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)接口的功能。</span><span class="sxs-lookup"><span data-stu-id="746a7-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="746a7-104">方法</span><span class="sxs-lookup"><span data-stu-id="746a7-104">Methods</span></span>  
  
|<span data-ttu-id="746a7-105">方法</span><span class="sxs-lookup"><span data-stu-id="746a7-105">Method</span></span>|<span data-ttu-id="746a7-106">描述</span><span class="sxs-lookup"><span data-stu-id="746a7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="746a7-107">GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="746a7-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="746a7-108">获取位掩码指定的每个寄存器的值（在当前正在执行代码的计算机上）。</span><span class="sxs-lookup"><span data-stu-id="746a7-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="746a7-109">GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="746a7-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="746a7-110">获取提供可用寄存器的位图的字节数组。</span><span class="sxs-lookup"><span data-stu-id="746a7-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="746a7-111">SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="746a7-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="746a7-112">在 .NET Framework 版本2.0 中未实现。</span><span class="sxs-lookup"><span data-stu-id="746a7-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="746a7-113">备注</span><span class="sxs-lookup"><span data-stu-id="746a7-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="746a7-114">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="746a7-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="746a7-115">要求</span><span class="sxs-lookup"><span data-stu-id="746a7-115">Requirements</span></span>  
 <span data-ttu-id="746a7-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="746a7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="746a7-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="746a7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="746a7-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="746a7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="746a7-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="746a7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746a7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="746a7-120">See also</span></span>

- [<span data-ttu-id="746a7-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="746a7-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="746a7-122">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="746a7-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
