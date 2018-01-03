---
title: "ICorDebugRegisterSet::GetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fba96f9d86f1df5c0800c8cafb9c7fd1b0a6f8c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="a1bbf-102">ICorDebugRegisterSet::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="a1bbf-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="a1bbf-103">获取当前线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="a1bbf-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bbf-104">语法</span><span class="sxs-lookup"><span data-stu-id="a1bbf-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1bbf-105">参数</span><span class="sxs-lookup"><span data-stu-id="a1bbf-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="a1bbf-106">[in]大小，以字节为单位的`context`数组。</span><span class="sxs-lookup"><span data-stu-id="a1bbf-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="a1bbf-107">[在中，out]撰写 Win32 的字节数组`CONTEXT`当前平台的结构。</span><span class="sxs-lookup"><span data-stu-id="a1bbf-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1bbf-108">备注</span><span class="sxs-lookup"><span data-stu-id="a1bbf-108">Remarks</span></span>  
 <span data-ttu-id="a1bbf-109">调试器应调用此函数而不是 Win32`GetThreadContext`函数，因为该线程可能处于其上下文已被暂时更改"被劫持"状态。</span><span class="sxs-lookup"><span data-stu-id="a1bbf-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="a1bbf-110">返回的数据是 Win32`CONTEXT`当前平台的结构。</span><span class="sxs-lookup"><span data-stu-id="a1bbf-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="a1bbf-111">对于非叶的帧，客户端应检查哪些寄存器是有效的通过使用[icordebugregisterset:: Getregistersavailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a1bbf-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1bbf-112">惠?</span><span class="sxs-lookup"><span data-stu-id="a1bbf-112">Requirements</span></span>  
 <span data-ttu-id="a1bbf-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a1bbf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1bbf-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1bbf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1bbf-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1bbf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1bbf-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1bbf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bbf-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1bbf-117">See Also</span></span>  
 [<span data-ttu-id="a1bbf-118">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="a1bbf-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="a1bbf-119">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="a1bbf-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
