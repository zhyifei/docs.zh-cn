---
title: ICorDebugDataTarget::GetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 79708aa5a2abcb8d7465f82a8beb918484c193b9
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976546"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="17741-102">ICorDebugDataTarget::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="17741-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="17741-103">返回指定线程的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="17741-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17741-104">语法</span><span class="sxs-lookup"><span data-stu-id="17741-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17741-105">参数</span><span class="sxs-lookup"><span data-stu-id="17741-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="17741-106">中要检索其上下文的线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="17741-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="17741-107">标识符由操作系统定义。</span><span class="sxs-lookup"><span data-stu-id="17741-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="17741-108">中平台相关标志的按位组合，用于指示应读取上下文的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="17741-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="17741-109">[输入] `pContext` 的大小。</span><span class="sxs-lookup"><span data-stu-id="17741-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="17741-110">弄将存储线程上下文的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="17741-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17741-111">备注</span><span class="sxs-lookup"><span data-stu-id="17741-111">Remarks</span></span>  
 <span data-ttu-id="17741-112">在 Windows 平台上`pContext` ，必须是`CONTEXT`适用于由[ICorDebugDataTarget：： GetPlatform](icordebugdatatarget-getplatform-method.md)方法指定的计算机类型的结构（在 WinNT .h 中定义）。</span><span class="sxs-lookup"><span data-stu-id="17741-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="17741-113">`contextFlags`必须与`ContextFlags` `CONTEXT`结构的字段具有相同的值。</span><span class="sxs-lookup"><span data-stu-id="17741-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="17741-114">`CONTEXT`结构特定于处理器;有关详细信息，请参阅 WinNT .h 文件。</span><span class="sxs-lookup"><span data-stu-id="17741-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17741-115">要求</span><span class="sxs-lookup"><span data-stu-id="17741-115">Requirements</span></span>  
 <span data-ttu-id="17741-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="17741-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17741-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17741-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17741-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17741-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17741-119">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17741-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17741-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17741-120">See also</span></span>

- [<span data-ttu-id="17741-121">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="17741-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="17741-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="17741-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="17741-123">调试</span><span class="sxs-lookup"><span data-stu-id="17741-123">Debugging</span></span>](index.md)
