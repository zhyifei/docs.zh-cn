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
ms.openlocfilehash: 3eace2d91b3bb6e637a659b8b49a31450ebc2c42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783720"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="a4923-102">ICorDebugDataTarget::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="a4923-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="a4923-103">返回指定线程的当前线程上下文。</span><span class="sxs-lookup"><span data-stu-id="a4923-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4923-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4923-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4923-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4923-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="a4923-106">中要检索其上下文的线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="a4923-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="a4923-107">标识符由操作系统定义。</span><span class="sxs-lookup"><span data-stu-id="a4923-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="a4923-108">中平台相关标志的按位组合，用于指示应读取上下文的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="a4923-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a4923-109">[输入] `pContext` 的大小。</span><span class="sxs-lookup"><span data-stu-id="a4923-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="a4923-110">弄将存储线程上下文的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="a4923-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4923-111">备注</span><span class="sxs-lookup"><span data-stu-id="a4923-111">Remarks</span></span>  
 <span data-ttu-id="a4923-112">在 Windows 平台上，`pContext` 必须是适用于由[ICorDebugDataTarget：： GetPlatform](icordebugdatatarget-getplatform-method.md)方法指定的计算机类型的 `CONTEXT` 结构（在 WinNT .h 中定义）。</span><span class="sxs-lookup"><span data-stu-id="a4923-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="a4923-113">`contextFlags` 必须具有与 `CONTEXT` 结构的 `ContextFlags` 字段相同的值。</span><span class="sxs-lookup"><span data-stu-id="a4923-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="a4923-114">`CONTEXT` 结构特定于处理器;有关详细信息，请参阅 WinNT .h 文件。</span><span class="sxs-lookup"><span data-stu-id="a4923-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4923-115">需求</span><span class="sxs-lookup"><span data-stu-id="a4923-115">Requirements</span></span>  
 <span data-ttu-id="a4923-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4923-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4923-117">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4923-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4923-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4923-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4923-119">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4923-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4923-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4923-120">See also</span></span>

- [<span data-ttu-id="a4923-121">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="a4923-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="a4923-122">调试接口</span><span class="sxs-lookup"><span data-stu-id="a4923-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a4923-123">调试</span><span class="sxs-lookup"><span data-stu-id="a4923-123">Debugging</span></span>](index.md)
