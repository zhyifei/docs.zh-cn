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
ms.openlocfilehash: f989f1c1f29c63af54ff125f4ad1aaa2bcee6757
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378201"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="a00d3-102">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="a00d3-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="a00d3-103">为包含64个以上注册的硬件平台扩展了[ICorDebugRegisterSet](icordebugregisterset-interface.md)接口的功能。</span><span class="sxs-lookup"><span data-stu-id="a00d3-103">Extends the capabilities of the [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a00d3-104">方法</span><span class="sxs-lookup"><span data-stu-id="a00d3-104">Methods</span></span>  
  
|<span data-ttu-id="a00d3-105">方法</span><span class="sxs-lookup"><span data-stu-id="a00d3-105">Method</span></span>|<span data-ttu-id="a00d3-106">描述</span><span class="sxs-lookup"><span data-stu-id="a00d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a00d3-107">GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="a00d3-107">GetRegisters Method</span></span>](icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="a00d3-108">获取位掩码指定的每个寄存器的值（在当前正在执行代码的计算机上）。</span><span class="sxs-lookup"><span data-stu-id="a00d3-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="a00d3-109">GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="a00d3-109">GetRegistersAvailable Method</span></span>](icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="a00d3-110">获取提供可用寄存器的位图的字节数组。</span><span class="sxs-lookup"><span data-stu-id="a00d3-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="a00d3-111">SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="a00d3-111">SetRegisters Method</span></span>](icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="a00d3-112">在 .NET Framework 版本2.0 中未实现。</span><span class="sxs-lookup"><span data-stu-id="a00d3-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a00d3-113">备注</span><span class="sxs-lookup"><span data-stu-id="a00d3-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a00d3-114">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a00d3-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a00d3-115">要求</span><span class="sxs-lookup"><span data-stu-id="a00d3-115">Requirements</span></span>  
 <span data-ttu-id="a00d3-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a00d3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a00d3-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a00d3-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a00d3-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a00d3-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a00d3-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a00d3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00d3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a00d3-120">See also</span></span>

- [<span data-ttu-id="a00d3-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="a00d3-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a00d3-122">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="a00d3-122">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
