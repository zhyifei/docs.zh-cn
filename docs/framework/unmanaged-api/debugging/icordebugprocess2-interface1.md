---
title: ICorDebugProcess2 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2
helpviewer_keywords:
- ICorDebugProcess2 interface [.NET Framework debugging]
ms.assetid: 73332138-5fea-441f-b893-61af87d45a42
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a1588a37891d6a73c49cb1b9ccbc81d9dcdb7e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420412"
---
# <a name="icordebugprocess2-interface1"></a><span data-ttu-id="bbaf4-102">ICorDebugProcess2 接口 1</span><span class="sxs-lookup"><span data-stu-id="bbaf4-102">ICorDebugProcess2 Interface1</span></span>
<span data-ttu-id="bbaf4-103">ICorDebugProcess 接口，它表示进程正在运行托管的代码的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bbaf4-104">方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-104">Methods</span></span>  
  
|<span data-ttu-id="bbaf4-105">方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-105">Method</span></span>|<span data-ttu-id="bbaf4-106">描述</span><span class="sxs-lookup"><span data-stu-id="bbaf4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bbaf4-107">ClearUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="bbaf4-108">删除以前调用所设置的指定偏移量处的断点`ICorDebugProcess2::SetUnmanagedBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="bbaf4-109">GetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="bbaf4-110">获取必须设置为公共语言运行时 (CLR) 将映像加载到此引用的进程的标志`ICorDebugProcess2`。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="bbaf4-111">GetReferenceValueFromGCHandle 方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="bbaf4-112">获取指定的托管对象具有垃圾回收句柄引用指针。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="bbaf4-113">GetThreadForTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="bbaf4-114">获取在其执行具有指定标识符的任务的线程。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="bbaf4-115">GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="bbaf4-116">获取在其运行正在调试的进程的 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="bbaf4-117">SetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="bbaf4-118">设置所需的映像加载到正在调试的进程在实时 (JIT) 编译器的标志。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="bbaf4-119">SetUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="bbaf4-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="bbaf4-120">指定的本机映像的偏移量处设置非托管的断点。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbaf4-121">备注</span><span class="sxs-lookup"><span data-stu-id="bbaf4-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbaf4-122">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbaf4-123">要求</span><span class="sxs-lookup"><span data-stu-id="bbaf4-123">Requirements</span></span>  
 <span data-ttu-id="bbaf4-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbaf4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbaf4-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbaf4-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbaf4-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbaf4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbaf4-127">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbaf4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbaf4-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbaf4-128">See Also</span></span>  
 [<span data-ttu-id="bbaf4-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="bbaf4-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
