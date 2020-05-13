---
title: ICorDebugMutableDataTarget::SetThreadContext 方法
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: a6df6bf030ad339f5d02b95cd191b30db60aa167
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210145"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="cd900-102">ICorDebugMutableDataTarget::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="cd900-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="cd900-103">设置某个线程的上下文（寄存器值）。</span><span class="sxs-lookup"><span data-stu-id="cd900-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd900-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd900-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd900-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd900-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="cd900-106">[in] 由操作系统定义的线程标识符。</span><span class="sxs-lookup"><span data-stu-id="cd900-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="cd900-107">[in] 要写入的 `pContext` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="cd900-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="cd900-108">[in] 指向要写入的字节的指针。</span><span class="sxs-lookup"><span data-stu-id="cd900-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd900-109">备注</span><span class="sxs-lookup"><span data-stu-id="cd900-109">Remarks</span></span>  
 <span data-ttu-id="cd900-110">`SetThreadContext` 方法将更新由操作系统定义的 `dwThreadID` 参数指定的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="cd900-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="cd900-111">上下文记录的格式由[ICorDebugDataTarget：： GetPlatform](icordebugdatatarget-getplatform-method.md)方法指示的平台决定。</span><span class="sxs-lookup"><span data-stu-id="cd900-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="cd900-112">在 Windows 上，这是一个[上下文](/windows/win32/api/winnt/ns-winnt-arm64_nt_context)结构。</span><span class="sxs-lookup"><span data-stu-id="cd900-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd900-113">要求</span><span class="sxs-lookup"><span data-stu-id="cd900-113">Requirements</span></span>  
 <span data-ttu-id="cd900-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd900-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd900-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd900-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd900-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd900-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd900-117">**.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd900-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd900-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd900-118">See also</span></span>

- [<span data-ttu-id="cd900-119">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="cd900-119">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="cd900-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="cd900-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
