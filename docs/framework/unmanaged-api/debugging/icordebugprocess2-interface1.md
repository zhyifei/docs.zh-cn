---
title: "ICorDebugProcess2 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2
helpviewer_keywords: ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca1a73874f6ca2f839639cbaf731a59721b2aede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="346ba-102">ICorDebugProcess2 接口 1</span><span class="sxs-lookup"><span data-stu-id="346ba-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="346ba-103">ICorDebugProcess 接口，它表示进程正在运行托管的代码的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="346ba-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="346ba-104">方法</span><span class="sxs-lookup"><span data-stu-id="346ba-104">Methods</span></span>  
  
|<span data-ttu-id="346ba-105">方法</span><span class="sxs-lookup"><span data-stu-id="346ba-105">Method</span></span>|<span data-ttu-id="346ba-106">描述</span><span class="sxs-lookup"><span data-stu-id="346ba-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="346ba-107">ClearUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="346ba-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="346ba-108">删除以前调用所设置的指定偏移量处的断点`ICorDebugProcess2::SetUnmanagedBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="346ba-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="346ba-109">GetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="346ba-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="346ba-110">获取必须设置为公共语言运行时 (CLR) 将映像加载到此引用的进程的标志`ICorDebugProcess2`。</span><span class="sxs-lookup"><span data-stu-id="346ba-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="346ba-111">GetReferenceValueFromGCHandle 方法</span><span class="sxs-lookup"><span data-stu-id="346ba-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="346ba-112">获取指定的托管对象具有垃圾回收句柄引用指针。</span><span class="sxs-lookup"><span data-stu-id="346ba-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="346ba-113">GetThreadForTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="346ba-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="346ba-114">获取在其执行具有指定标识符的任务的线程。</span><span class="sxs-lookup"><span data-stu-id="346ba-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="346ba-115">GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="346ba-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="346ba-116">获取在其运行正在调试的进程的 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="346ba-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="346ba-117">SetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="346ba-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="346ba-118">设置所需的映像加载到正在调试的进程在实时 (JIT) 编译器的标志。</span><span class="sxs-lookup"><span data-stu-id="346ba-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="346ba-119">SetUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="346ba-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="346ba-120">指定的本机映像的偏移量处设置非托管的断点。</span><span class="sxs-lookup"><span data-stu-id="346ba-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="346ba-121">备注</span><span class="sxs-lookup"><span data-stu-id="346ba-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="346ba-122">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="346ba-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="346ba-123">要求</span><span class="sxs-lookup"><span data-stu-id="346ba-123">Requirements</span></span>  
 <span data-ttu-id="346ba-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="346ba-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="346ba-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="346ba-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="346ba-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="346ba-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="346ba-127">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="346ba-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="346ba-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="346ba-128">See Also</span></span>  
 [<span data-ttu-id="346ba-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="346ba-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
