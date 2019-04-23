---
title: ICorDebugRegisterSet::GetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fecbcff0fd124b94aeeecf82e23d9875c34ebb9b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091572"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="cb3e6-102">ICorDebugRegisterSet::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="cb3e6-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="cb3e6-103">获取当前线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="cb3e6-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb3e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb3e6-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb3e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb3e6-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="cb3e6-106">[in]大小，以字节为单位的`context`数组。</span><span class="sxs-lookup"><span data-stu-id="cb3e6-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="cb3e6-107">[in、 out]编写 Win32 的字节数组`CONTEXT`对于当前平台的结构。</span><span class="sxs-lookup"><span data-stu-id="cb3e6-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb3e6-108">备注</span><span class="sxs-lookup"><span data-stu-id="cb3e6-108">Remarks</span></span>  
 <span data-ttu-id="cb3e6-109">调试程序应调用此函数而不是 Win32`GetThreadContext`函数，因为该线程可能在其上下文已被暂时更改"被劫持"状态。</span><span class="sxs-lookup"><span data-stu-id="cb3e6-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="cb3e6-110">返回的数据是 Win32`CONTEXT`对于当前平台的结构。</span><span class="sxs-lookup"><span data-stu-id="cb3e6-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="cb3e6-111">对于非叶帧，客户端应检查哪些寄存器是有效的通过使用[icordebugregisterset:: Getregistersavailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)。</span><span class="sxs-lookup"><span data-stu-id="cb3e6-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb3e6-112">要求</span><span class="sxs-lookup"><span data-stu-id="cb3e6-112">Requirements</span></span>  
 <span data-ttu-id="cb3e6-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb3e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb3e6-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb3e6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb3e6-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb3e6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb3e6-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb3e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3e6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb3e6-117">See also</span></span>

- [<span data-ttu-id="cb3e6-118">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="cb3e6-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="cb3e6-119">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="cb3e6-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
