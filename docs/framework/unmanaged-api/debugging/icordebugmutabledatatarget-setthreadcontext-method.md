---
title: ICorDebugMutableDataTarget::SetThreadContext 方法
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 063c7954543174caece6f3dcbe005a4b2d059c64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792847"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="5ee4b-102">ICorDebugMutableDataTarget::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="5ee4b-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="5ee4b-103">设置某个线程的上下文（寄存器值）。</span><span class="sxs-lookup"><span data-stu-id="5ee4b-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee4b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ee4b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ee4b-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ee4b-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="5ee4b-106">[in] 由操作系统定义的线程标识符。</span><span class="sxs-lookup"><span data-stu-id="5ee4b-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="5ee4b-107">[in] 要写入的 `pContext` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="5ee4b-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="5ee4b-108">[in] 指向要写入的字节的指针。</span><span class="sxs-lookup"><span data-stu-id="5ee4b-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee4b-109">备注</span><span class="sxs-lookup"><span data-stu-id="5ee4b-109">Remarks</span></span>  
 <span data-ttu-id="5ee4b-110">`SetThreadContext` 方法将更新由操作系统定义的 `dwThreadID` 参数指定的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="5ee4b-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="5ee4b-111">上下文记录的格式由[ICorDebugDataTarget：： GetPlatform](icordebugdatatarget-getplatform-method.md)方法指示的平台决定。</span><span class="sxs-lookup"><span data-stu-id="5ee4b-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="5ee4b-112">在 Windows 上，这是一个[上下文](/windows/win32/api/winnt/ns-winnt-arm64_nt_context)结构。</span><span class="sxs-lookup"><span data-stu-id="5ee4b-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee4b-113">需求</span><span class="sxs-lookup"><span data-stu-id="5ee4b-113">Requirements</span></span>  
 <span data-ttu-id="5ee4b-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ee4b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee4b-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ee4b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ee4b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ee4b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ee4b-117">**.NET Framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee4b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee4b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ee4b-118">See also</span></span>

- [<span data-ttu-id="5ee4b-119">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="5ee4b-119">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="5ee4b-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="5ee4b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
