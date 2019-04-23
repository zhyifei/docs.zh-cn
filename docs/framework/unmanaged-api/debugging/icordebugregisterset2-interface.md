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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da2759219901a4f49808300ea3b038b10ce2d032
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101167"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="0e540-102">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="0e540-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="0e540-103">扩展的功能[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)接口具有 64 个以上寄存器的硬件平台。</span><span class="sxs-lookup"><span data-stu-id="0e540-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e540-104">方法</span><span class="sxs-lookup"><span data-stu-id="0e540-104">Methods</span></span>  
  
|<span data-ttu-id="0e540-105">方法</span><span class="sxs-lookup"><span data-stu-id="0e540-105">Method</span></span>|<span data-ttu-id="0e540-106">描述</span><span class="sxs-lookup"><span data-stu-id="0e540-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e540-107">GetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="0e540-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="0e540-108">获取每个寄存器的值 （上当前正在执行代码的计算机） 指定的位掩码。</span><span class="sxs-lookup"><span data-stu-id="0e540-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="0e540-109">GetRegistersAvailable 方法</span><span class="sxs-lookup"><span data-stu-id="0e540-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="0e540-110">获取提供的可用寄存器位图的字节数组。</span><span class="sxs-lookup"><span data-stu-id="0e540-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="0e540-111">SetRegisters 方法</span><span class="sxs-lookup"><span data-stu-id="0e540-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="0e540-112">.NET Framework 2.0 版中未实现。</span><span class="sxs-lookup"><span data-stu-id="0e540-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e540-113">备注</span><span class="sxs-lookup"><span data-stu-id="0e540-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e540-114">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="0e540-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e540-115">要求</span><span class="sxs-lookup"><span data-stu-id="0e540-115">Requirements</span></span>  
 <span data-ttu-id="0e540-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e540-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e540-117">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e540-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e540-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e540-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e540-119">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e540-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e540-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e540-120">See also</span></span>

- [<span data-ttu-id="0e540-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="0e540-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0e540-122">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="0e540-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
