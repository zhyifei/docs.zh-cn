---
title: ICorDebugFrame 接口
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: 5aeea11b7e61869968aafe3425e27d6004f495ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124063"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="8f055-102">ICorDebugFrame 接口</span><span class="sxs-lookup"><span data-stu-id="8f055-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="8f055-103">表示当前堆栈上的帧。</span><span class="sxs-lookup"><span data-stu-id="8f055-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f055-104">方法</span><span class="sxs-lookup"><span data-stu-id="8f055-104">Methods</span></span>  
  
|<span data-ttu-id="8f055-105">方法</span><span class="sxs-lookup"><span data-stu-id="8f055-105">Method</span></span>|<span data-ttu-id="8f055-106">描述</span><span class="sxs-lookup"><span data-stu-id="8f055-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f055-107">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="8f055-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="8f055-108">获取一个 ICorDebugStepper，以执行与此 `ICorDebugFrame`相关的单步执行操作。</span><span class="sxs-lookup"><span data-stu-id="8f055-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="8f055-109">GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="8f055-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="8f055-110">获取一个指针，该指针指向此框架调用的当前链中的 `ICorDebugFrame`，如果这是链中的最内层帧，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="8f055-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="8f055-111">GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="8f055-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="8f055-112">获取指向当前链中调用此帧的 `ICorDebugFrame` 的指针，如果这是链中最外层的帧，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="8f055-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="8f055-113">GetChain 方法</span><span class="sxs-lookup"><span data-stu-id="8f055-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="8f055-114">获取一个指针，该指针指向 `ICorDebugFrame` 所属的 ICorDebugChain。</span><span class="sxs-lookup"><span data-stu-id="8f055-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="8f055-115">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="8f055-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="8f055-116">获取一个指针，该指针指向与此堆栈帧关联的 ICorDebugCode。</span><span class="sxs-lookup"><span data-stu-id="8f055-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8f055-117">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="8f055-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="8f055-118">获取一个指向 ICorDebugFunction 的指针，该指针包含与此堆栈帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="8f055-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8f055-119">GetFunctionToken 方法</span><span class="sxs-lookup"><span data-stu-id="8f055-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="8f055-120">获取包含与此堆栈帧关联的代码的函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="8f055-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="8f055-121">GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="8f055-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="8f055-122">获取此 `ICorDebugFrame`所表示的堆栈帧的绝对地址范围。</span><span class="sxs-lookup"><span data-stu-id="8f055-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f055-123">备注</span><span class="sxs-lookup"><span data-stu-id="8f055-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f055-124">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8f055-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f055-125">要求</span><span class="sxs-lookup"><span data-stu-id="8f055-125">Requirements</span></span>  
 <span data-ttu-id="8f055-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f055-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f055-127">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f055-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f055-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f055-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f055-129">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f055-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f055-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f055-130">See also</span></span>

- [<span data-ttu-id="8f055-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="8f055-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
