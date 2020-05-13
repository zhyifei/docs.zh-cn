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
ms.openlocfilehash: 04ae3c4dd663351eaf1a58646e24e8ae95aeb9ad
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378285"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="423b7-102">ICorDebugRegisterSet::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="423b7-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="423b7-103">获取当前线程的上下文。</span><span class="sxs-lookup"><span data-stu-id="423b7-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="423b7-104">语法</span><span class="sxs-lookup"><span data-stu-id="423b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="423b7-105">参数</span><span class="sxs-lookup"><span data-stu-id="423b7-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="423b7-106">中数组的大小（以字节为单位） `context` 。</span><span class="sxs-lookup"><span data-stu-id="423b7-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="423b7-107">[in，out]为当前平台构成 Win32 结构的字节数组 `CONTEXT` 。</span><span class="sxs-lookup"><span data-stu-id="423b7-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="423b7-108">备注</span><span class="sxs-lookup"><span data-stu-id="423b7-108">Remarks</span></span>  
 <span data-ttu-id="423b7-109">调试器应调用此函数，而不是 Win32 `GetThreadContext` 函数，因为该线程可能处于暂时更改其上下文的 "被劫持" 状态。</span><span class="sxs-lookup"><span data-stu-id="423b7-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="423b7-110">返回的数据是 `CONTEXT` 当前平台的 Win32 结构。</span><span class="sxs-lookup"><span data-stu-id="423b7-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="423b7-111">对于非叶帧，客户端应使用[ICorDebugRegisterSet：： GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)检查哪些寄存器是有效的。</span><span class="sxs-lookup"><span data-stu-id="423b7-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="423b7-112">要求</span><span class="sxs-lookup"><span data-stu-id="423b7-112">Requirements</span></span>  
 <span data-ttu-id="423b7-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="423b7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="423b7-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="423b7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="423b7-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="423b7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="423b7-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="423b7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="423b7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="423b7-117">See also</span></span>

- [<span data-ttu-id="423b7-118">ICorDebugRegisterSet 接口</span><span class="sxs-lookup"><span data-stu-id="423b7-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="423b7-119">ICorDebugRegisterSet2 接口</span><span class="sxs-lookup"><span data-stu-id="423b7-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
