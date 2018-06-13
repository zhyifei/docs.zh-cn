---
title: ICorDebugMutableDataTarget::SetThreadContext 方法
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05f0c0d23b4885f2d6fd351fdf845a25c899228e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418413"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="334d5-102">ICorDebugMutableDataTarget::SetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="334d5-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="334d5-103">设置某个线程的上下文（寄存器值）。</span><span class="sxs-lookup"><span data-stu-id="334d5-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="334d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="334d5-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="334d5-105">参数</span><span class="sxs-lookup"><span data-stu-id="334d5-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="334d5-106">[in] 由操作系统定义的线程标识符。</span><span class="sxs-lookup"><span data-stu-id="334d5-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="334d5-107">[in] 要写入的 `pContext` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="334d5-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="334d5-108">[in] 指向要写入的字节的指针。</span><span class="sxs-lookup"><span data-stu-id="334d5-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="334d5-109">备注</span><span class="sxs-lookup"><span data-stu-id="334d5-109">Remarks</span></span>  
 <span data-ttu-id="334d5-110">`SetThreadContext` 方法将更新由操作系统定义的 `dwThreadID` 参数指定的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="334d5-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="334d5-111">上下文记录的格式由通过指示的平台[icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="334d5-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="334d5-112">在 Windows 上，这是[上下文](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx)结构。</span><span class="sxs-lookup"><span data-stu-id="334d5-112">On Windows, this is a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="334d5-113">要求</span><span class="sxs-lookup"><span data-stu-id="334d5-113">Requirements</span></span>  
 <span data-ttu-id="334d5-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="334d5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="334d5-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="334d5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="334d5-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="334d5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="334d5-117">**.NET framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="334d5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334d5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="334d5-118">See Also</span></span>  
 [<span data-ttu-id="334d5-119">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="334d5-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="334d5-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="334d5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
