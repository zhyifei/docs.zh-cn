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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4744ea67d0ce0d9ad2b13c45bdef65f884ef925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937006"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="90a99-102">ICorDebugFrame 接口</span><span class="sxs-lookup"><span data-stu-id="90a99-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="90a99-103">表示当前堆栈上的帧。</span><span class="sxs-lookup"><span data-stu-id="90a99-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90a99-104">方法</span><span class="sxs-lookup"><span data-stu-id="90a99-104">Methods</span></span>  
  
|<span data-ttu-id="90a99-105">方法</span><span class="sxs-lookup"><span data-stu-id="90a99-105">Method</span></span>|<span data-ttu-id="90a99-106">描述</span><span class="sxs-lookup"><span data-stu-id="90a99-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90a99-107">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="90a99-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="90a99-108">获取用于执行与此`ICorDebugFrame`相关的单步执行操作的 ICorDebugStepper。</span><span class="sxs-lookup"><span data-stu-id="90a99-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="90a99-109">GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="90a99-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="90a99-110">获取一个指针, 该`ICorDebugFrame`指针指向此框架调用的当前链中的, 如果这是链中的最内层帧, 则返回 null。</span><span class="sxs-lookup"><span data-stu-id="90a99-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="90a99-111">GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="90a99-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="90a99-112">获取指向当前链中`ICorDebugFrame`调用此帧的的指针, 如果这是链中最外层的帧, 则返回 null。</span><span class="sxs-lookup"><span data-stu-id="90a99-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="90a99-113">GetChain 方法</span><span class="sxs-lookup"><span data-stu-id="90a99-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="90a99-114">获取一个指针, 该指针指向`ICorDebugFrame`作为的一部分的 ICorDebugChain。</span><span class="sxs-lookup"><span data-stu-id="90a99-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="90a99-115">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="90a99-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="90a99-116">获取一个指针, 该指针指向与此堆栈帧关联的 ICorDebugCode。</span><span class="sxs-lookup"><span data-stu-id="90a99-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="90a99-117">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="90a99-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="90a99-118">获取一个指向 ICorDebugFunction 的指针, 该指针包含与此堆栈帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="90a99-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="90a99-119">GetFunctionToken 方法</span><span class="sxs-lookup"><span data-stu-id="90a99-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="90a99-120">获取包含与此堆栈帧关联的代码的函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="90a99-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="90a99-121">GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="90a99-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="90a99-122">获取此`ICorDebugFrame`所表示的堆栈帧的绝对地址范围。</span><span class="sxs-lookup"><span data-stu-id="90a99-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90a99-123">备注</span><span class="sxs-lookup"><span data-stu-id="90a99-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90a99-124">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="90a99-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90a99-125">要求</span><span class="sxs-lookup"><span data-stu-id="90a99-125">Requirements</span></span>  
 <span data-ttu-id="90a99-126">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90a99-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90a99-127">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="90a99-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90a99-128">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90a99-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90a99-129">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90a99-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a99-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="90a99-130">See also</span></span>

- [<span data-ttu-id="90a99-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="90a99-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
