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
ms.openlocfilehash: 161358fab9a4601e7b718321273d493bd84a3228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792015"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="8f998-102">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="8f998-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="8f998-103">为包含64个以上注册的硬件平台扩展了[ICorDebugRegisterSet](icordebugregisterset-interface.md)接口的功能。</span><span class="sxs-lookup"><span data-stu-id="8f998-103">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f998-104">方法</span><span class="sxs-lookup"><span data-stu-id="8f998-104">Methods</span></span>  
  
|<span data-ttu-id="8f998-105">方法</span><span class="sxs-lookup"><span data-stu-id="8f998-105">Method</span></span>|<span data-ttu-id="8f998-106">描述</span><span class="sxs-lookup"><span data-stu-id="8f998-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f998-107">GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="8f998-107">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="8f998-108">获取位掩码指定的每个寄存器的值（在当前正在执行代码的计算机上）。</span><span class="sxs-lookup"><span data-stu-id="8f998-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="8f998-109">GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="8f998-109">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="8f998-110">获取提供可用寄存器的位图的字节数组。</span><span class="sxs-lookup"><span data-stu-id="8f998-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="8f998-111">SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="8f998-111">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="8f998-112">在 .NET Framework 版本2.0 中未实现。</span><span class="sxs-lookup"><span data-stu-id="8f998-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f998-113">备注</span><span class="sxs-lookup"><span data-stu-id="8f998-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f998-114">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8f998-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f998-115">需求</span><span class="sxs-lookup"><span data-stu-id="8f998-115">Requirements</span></span>  
 <span data-ttu-id="8f998-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f998-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f998-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f998-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f998-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f998-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f998-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f998-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f998-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f998-120">See also</span></span>

- [<span data-ttu-id="8f998-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="8f998-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8f998-122">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="8f998-122">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
