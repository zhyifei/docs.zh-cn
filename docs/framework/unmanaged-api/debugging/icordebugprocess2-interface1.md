---
title: ICorDebugProcess2 接口
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
ms.openlocfilehash: c3009ee6a2ba22771a2132032744f76ca527c422
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965678"
---
# <a name="icordebugprocess2-interface"></a><span data-ttu-id="ce1d2-102">ICorDebugProcess2 接口</span><span class="sxs-lookup"><span data-stu-id="ce1d2-102">ICorDebugProcess2 Interface</span></span>
<span data-ttu-id="ce1d2-103">ICorDebugProcess 接口，它表示进程正在运行托管的代码的逻辑扩展。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-103">A logical extension of the ICorDebugProcess interface, which represents a process running managed code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce1d2-104">方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-104">Methods</span></span>  
  
|<span data-ttu-id="ce1d2-105">方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-105">Method</span></span>|<span data-ttu-id="ce1d2-106">描述</span><span class="sxs-lookup"><span data-stu-id="ce1d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce1d2-107">ClearUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-107">ClearUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md)|<span data-ttu-id="ce1d2-108">删除指定的偏移量对的早期调用所设置的断点`ICorDebugProcess2::SetUnmanagedBreakpoint`。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-108">Removes a breakpoint at the specified offset that was set by an earlier call to `ICorDebugProcess2::SetUnmanagedBreakpoint`.</span></span>|  
|[<span data-ttu-id="ce1d2-109">GetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-109">GetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getdesiredngencompilerflags-method.md)|<span data-ttu-id="ce1d2-110">获取必须为公共语言运行时 (CLR) 设置，以将图像加载到此引用的进程的标志`ICorDebugProcess2`。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-110">Gets the flags that must be set for the common language runtime (CLR) to load the image into the process referenced by this `ICorDebugProcess2`.</span></span>|  
|[<span data-ttu-id="ce1d2-111">GetReferenceValueFromGCHandle 方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-111">GetReferenceValueFromGCHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getreferencevaluefromgchandle-method.md)|<span data-ttu-id="ce1d2-112">获取指定的托管对象具有垃圾回收句柄引用指向。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-112">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>|  
|[<span data-ttu-id="ce1d2-113">GetThreadForTaskID 方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-113">GetThreadForTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getthreadfortaskid-method.md)|<span data-ttu-id="ce1d2-114">获取对其执行具有指定标识符的任务的线程。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-114">Gets the thread upon which the task with the specified identifier is executing.</span></span>|  
|[<span data-ttu-id="ce1d2-115">GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-115">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-getversion-method.md)|<span data-ttu-id="ce1d2-116">获取正在调试的进程正在运行的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-116">Gets the version of the CLR upon which the process being debugged is running.</span></span>|  
|[<span data-ttu-id="ce1d2-117">SetDesiredNGENCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-117">SetDesiredNGENCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md)|<span data-ttu-id="ce1d2-118">设置所需的图像加载到正在调试的进程中实时 (JIT) 编译器的标志。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-118">Sets the flags that are required for the just-in-time (JIT) compiler to load an image into the process being debugged.</span></span>|  
|[<span data-ttu-id="ce1d2-119">SetUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="ce1d2-119">SetUnmanagedBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)|<span data-ttu-id="ce1d2-120">设置指定的本机映像的偏移量处的非托管的断点。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-120">Sets an unmanaged breakpoint at the specified native image offset.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce1d2-121">备注</span><span class="sxs-lookup"><span data-stu-id="ce1d2-121">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce1d2-122">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce1d2-123">要求</span><span class="sxs-lookup"><span data-stu-id="ce1d2-123">Requirements</span></span>  
 <span data-ttu-id="ce1d2-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce1d2-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce1d2-125">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce1d2-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce1d2-126">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce1d2-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce1d2-127">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce1d2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce1d2-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce1d2-128">See also</span></span>
- [<span data-ttu-id="ce1d2-129">调试接口</span><span class="sxs-lookup"><span data-stu-id="ce1d2-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
