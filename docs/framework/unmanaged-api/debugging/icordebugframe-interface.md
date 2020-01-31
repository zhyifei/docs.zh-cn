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
ms.openlocfilehash: ba138e79e0d6fb6f9c5e9c3efe3466f3c88cccae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782622"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="d53d4-102">ICorDebugFrame 接口</span><span class="sxs-lookup"><span data-stu-id="d53d4-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="d53d4-103">表示当前堆栈上的帧。</span><span class="sxs-lookup"><span data-stu-id="d53d4-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d53d4-104">方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-104">Methods</span></span>  
  
|<span data-ttu-id="d53d4-105">方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-105">Method</span></span>|<span data-ttu-id="d53d4-106">描述</span><span class="sxs-lookup"><span data-stu-id="d53d4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d53d4-107">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-107">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="d53d4-108">获取一个 ICorDebugStepper，以执行与此 `ICorDebugFrame`相关的单步执行操作。</span><span class="sxs-lookup"><span data-stu-id="d53d4-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="d53d4-109">GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-109">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="d53d4-110">获取一个指针，该指针指向此框架调用的当前链中的 `ICorDebugFrame`，如果这是链中的最内层帧，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="d53d4-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="d53d4-111">GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-111">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="d53d4-112">获取指向当前链中调用此帧的 `ICorDebugFrame` 的指针，如果这是链中最外层的帧，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="d53d4-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="d53d4-113">GetChain 方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-113">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="d53d4-114">获取一个指针，该指针指向 `ICorDebugFrame` 所属的 ICorDebugChain。</span><span class="sxs-lookup"><span data-stu-id="d53d4-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="d53d4-115">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-115">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="d53d4-116">获取一个指针，该指针指向与此堆栈帧关联的 ICorDebugCode。</span><span class="sxs-lookup"><span data-stu-id="d53d4-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="d53d4-117">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-117">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="d53d4-118">获取一个指向 ICorDebugFunction 的指针，该指针包含与此堆栈帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="d53d4-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="d53d4-119">GetFunctionToken 方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-119">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="d53d4-120">获取包含与此堆栈帧关联的代码的函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d53d4-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="d53d4-121">GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="d53d4-121">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="d53d4-122">获取此 `ICorDebugFrame`所表示的堆栈帧的绝对地址范围。</span><span class="sxs-lookup"><span data-stu-id="d53d4-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d53d4-123">备注</span><span class="sxs-lookup"><span data-stu-id="d53d4-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d53d4-124">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d53d4-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d53d4-125">需求</span><span class="sxs-lookup"><span data-stu-id="d53d4-125">Requirements</span></span>  
 <span data-ttu-id="d53d4-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d53d4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d53d4-127">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d53d4-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d53d4-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d53d4-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d53d4-129">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d53d4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53d4-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d53d4-130">See also</span></span>

- [<span data-ttu-id="d53d4-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="d53d4-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
