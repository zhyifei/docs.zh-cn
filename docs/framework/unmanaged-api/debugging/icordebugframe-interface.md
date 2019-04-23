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
ms.openlocfilehash: a15d7f16676b8b9d66f8d1ba7484f3fec5735a44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222557"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="aa621-102">ICorDebugFrame 接口</span><span class="sxs-lookup"><span data-stu-id="aa621-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="aa621-103">表示当前堆栈上的帧。</span><span class="sxs-lookup"><span data-stu-id="aa621-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa621-104">方法</span><span class="sxs-lookup"><span data-stu-id="aa621-104">Methods</span></span>  
  
|<span data-ttu-id="aa621-105">方法</span><span class="sxs-lookup"><span data-stu-id="aa621-105">Method</span></span>|<span data-ttu-id="aa621-106">描述</span><span class="sxs-lookup"><span data-stu-id="aa621-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aa621-107">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="aa621-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="aa621-108">获取执行单步执行操作相对于此 ICorDebugStepper `ICorDebugFrame`。</span><span class="sxs-lookup"><span data-stu-id="aa621-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="aa621-109">GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="aa621-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="aa621-110">获取一个指向`ICorDebugFrame`此帧调用，或如果此将返回 null 是链中的最内部帧的当前链中。</span><span class="sxs-lookup"><span data-stu-id="aa621-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="aa621-111">GetCaller 方法</span><span class="sxs-lookup"><span data-stu-id="aa621-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="aa621-112">获取一个指向`ICorDebugFrame`当前链中调用此帧，或如果此将返回 null 是链中的最外面的帧。</span><span class="sxs-lookup"><span data-stu-id="aa621-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="aa621-113">GetChain 方法</span><span class="sxs-lookup"><span data-stu-id="aa621-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="aa621-114">获取一个指向 ICorDebugChain 此`ICorDebugFrame`是的一部分。</span><span class="sxs-lookup"><span data-stu-id="aa621-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="aa621-115">GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="aa621-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="aa621-116">获取一个指向与此堆栈帧关联 ICorDebugCode。</span><span class="sxs-lookup"><span data-stu-id="aa621-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="aa621-117">GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="aa621-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="aa621-118">获取一个指针指向包含与此堆栈帧关联的代码 ICorDebugFunction。</span><span class="sxs-lookup"><span data-stu-id="aa621-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="aa621-119">GetFunctionToken 方法</span><span class="sxs-lookup"><span data-stu-id="aa621-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="aa621-120">获取包含与此堆栈帧关联的代码的函数的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="aa621-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="aa621-121">GetStackRange 方法</span><span class="sxs-lookup"><span data-stu-id="aa621-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="aa621-122">获取表示此堆栈帧的绝对地址范围`ICorDebugFrame`。</span><span class="sxs-lookup"><span data-stu-id="aa621-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa621-123">备注</span><span class="sxs-lookup"><span data-stu-id="aa621-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa621-124">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="aa621-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa621-125">要求</span><span class="sxs-lookup"><span data-stu-id="aa621-125">Requirements</span></span>  
 <span data-ttu-id="aa621-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aa621-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa621-127">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa621-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa621-128">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa621-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa621-129">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa621-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa621-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa621-130">See also</span></span>

- [<span data-ttu-id="aa621-131">调试接口</span><span class="sxs-lookup"><span data-stu-id="aa621-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
