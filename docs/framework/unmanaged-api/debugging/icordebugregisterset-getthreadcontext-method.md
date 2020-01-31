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
ms.openlocfilehash: 8137d5477b75b864e223852cf524ac8c5b6c0f2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792092"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="68b48-102">ICorDebugRegisterSet::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="68b48-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="68b48-103">获取当前线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="68b48-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68b48-104">语法</span><span class="sxs-lookup"><span data-stu-id="68b48-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68b48-105">参数</span><span class="sxs-lookup"><span data-stu-id="68b48-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="68b48-106">中`context` 数组的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="68b48-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="68b48-107">[in，out]为当前平台构成 Win32 `CONTEXT` 结构的字节数组。</span><span class="sxs-lookup"><span data-stu-id="68b48-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68b48-108">备注</span><span class="sxs-lookup"><span data-stu-id="68b48-108">Remarks</span></span>  
 <span data-ttu-id="68b48-109">调试器应调用此函数，而不是 Win32 `GetThreadContext` 函数，因为该线程的上下文已暂时更改。</span><span class="sxs-lookup"><span data-stu-id="68b48-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="68b48-110">返回的数据是当前平台的 Win32 `CONTEXT` 结构。</span><span class="sxs-lookup"><span data-stu-id="68b48-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="68b48-111">对于非叶帧，客户端应使用[ICorDebugRegisterSet：： GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)检查哪些寄存器是有效的。</span><span class="sxs-lookup"><span data-stu-id="68b48-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68b48-112">需求</span><span class="sxs-lookup"><span data-stu-id="68b48-112">Requirements</span></span>  
 <span data-ttu-id="68b48-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68b48-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68b48-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68b48-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68b48-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68b48-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68b48-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68b48-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b48-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68b48-117">See also</span></span>

- [<span data-ttu-id="68b48-118">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="68b48-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="68b48-119">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="68b48-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
