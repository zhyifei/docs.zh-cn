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
ms.openlocfilehash: 9c2771d1338943406921447d96dd9a8748153a36
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209612"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="688fe-102">ICorDebugFrame 接口</span><span class="sxs-lookup"><span data-stu-id="688fe-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="688fe-103">表示当前堆栈上的帧。</span><span class="sxs-lookup"><span data-stu-id="688fe-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="688fe-104">方法</span><span class="sxs-lookup"><span data-stu-id="688fe-104">Methods</span></span>  
  
|<span data-ttu-id="688fe-105">方法</span><span class="sxs-lookup"><span data-stu-id="688fe-105">Method</span></span>|<span data-ttu-id="688fe-106">描述</span><span class="sxs-lookup"><span data-stu-id="688fe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="688fe-107">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="688fe-107">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="688fe-108">获取用于执行与此相关的单步执行操作的 ICorDebugStepper `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="688fe-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="688fe-109">GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="688fe-109">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="688fe-110">获取一个指针，该指针指向 `ICorDebugFrame` 此框架调用的当前链中的，如果这是链中的最内层帧，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="688fe-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="688fe-111">GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="688fe-111">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="688fe-112">获取指向 `ICorDebugFrame` 当前链中调用此帧的的指针，如果这是链中最外层的帧，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="688fe-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="688fe-113">GetChain 方法</span><span class="sxs-lookup"><span data-stu-id="688fe-113">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="688fe-114">获取一个指针，该指针指向作为的一部分的 ICorDebugChain `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="688fe-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="688fe-115">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="688fe-115">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="688fe-116">获取一个指针，该指针指向与此堆栈帧关联的 ICorDebugCode。</span><span class="sxs-lookup"><span data-stu-id="688fe-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="688fe-117">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="688fe-117">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="688fe-118">获取一个指向 ICorDebugFunction 的指针，该指针包含与此堆栈帧关联的代码。</span><span class="sxs-lookup"><span data-stu-id="688fe-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="688fe-119">GetFunctionToken 方法</span><span class="sxs-lookup"><span data-stu-id="688fe-119">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="688fe-120">获取包含与此堆栈帧关联的代码的函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="688fe-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="688fe-121">GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="688fe-121">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="688fe-122">获取此所表示的堆栈帧的绝对地址范围 `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="688fe-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="688fe-123">备注</span><span class="sxs-lookup"><span data-stu-id="688fe-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="688fe-124">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="688fe-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="688fe-125">要求</span><span class="sxs-lookup"><span data-stu-id="688fe-125">Requirements</span></span>  
 <span data-ttu-id="688fe-126">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="688fe-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="688fe-127">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="688fe-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="688fe-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="688fe-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="688fe-129">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="688fe-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="688fe-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="688fe-130">See also</span></span>

- [<span data-ttu-id="688fe-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="688fe-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
