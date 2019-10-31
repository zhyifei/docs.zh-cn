---
title: _EFN_StackTrace 函数
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
ms.openlocfilehash: 272856c7eedbdc577158edcc463535a7946bb060
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122994"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="5bfd9-102">\_EFN\_StackTrace 函数</span><span class="sxs-lookup"><span data-stu-id="5bfd9-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="5bfd9-103">提供托管堆栈跟踪的文本表示形式以及 `CONTEXT` 记录的数组，其中每项对应非托管代码和托管代码之间的每个转换。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bfd9-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bfd9-104">Syntax</span></span>  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bfd9-105">参数</span><span class="sxs-lookup"><span data-stu-id="5bfd9-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="5bfd9-106">中正在调试的客户端。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="5bfd9-107">弄堆栈跟踪的文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="5bfd9-108">弄一个指针，指向 `wszTextOut`中的字符数。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="5bfd9-109">弄转换上下文的数组。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="5bfd9-110">弄指向数组中的转换上下文数的指针。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="5bfd9-111">中上下文结构的大小。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="5bfd9-112">中设置为0或 SOS_STACKTRACE_SHOWADDRESSES （0x01）以在每个 `module!functionname` 行的前面显示 EBP 寄存器并输入堆栈指针（ESP）。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bfd9-113">备注</span><span class="sxs-lookup"><span data-stu-id="5bfd9-113">Remarks</span></span>  
 <span data-ttu-id="5bfd9-114">`_EFN_StackTrace` 结构可从 WinDbg 编程界面调用。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="5bfd9-115">参数的使用方式如下：</span><span class="sxs-lookup"><span data-stu-id="5bfd9-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="5bfd9-116">如果 `wszTextOut` 为 null 且 `puiTextLength` 不为 null，则函数返回 `puiTextLength`中的字符串长度。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="5bfd9-117">如果 `wszTextOut` 不为 null，则该函数将在 `wszTextOut` 中存储文本，直到 `puiTextLength`指示的位置。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="5bfd9-118">如果缓冲区中有足够的空间，则它将成功返回，如果缓冲区不够长，则返回 E_OUTOFMEMORY。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="5bfd9-119">如果 `pTransitionContexts` 和 `puiTransitionContextCount` 均为 null，则忽略函数的转换部分。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="5bfd9-120">在这种情况下，函数向调用方提供仅包含函数名称的文本输出。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="5bfd9-121">如果 `pTransitionContexts` 为 null 且 `puiTransitionContextCount` 不为 null，则该函数将返回 `puiTransitionContextCount`中所需的上下文条目数。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="5bfd9-122">如果 `pTransitionContexts` 不为 null，则函数会将其视为长度为 `puiTransitionContextCount`的结构的数组。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="5bfd9-123">结构大小由 `uiSizeOfContext`给定，并且必须是体系结构的[SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)或 `CONTEXT` 的大小。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="5bfd9-124">`wszTextOut` 采用以下格式编写：</span><span class="sxs-lookup"><span data-stu-id="5bfd9-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="5bfd9-125">如果偏移量（十六进制）为0x0，则不写入偏移量。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="5bfd9-126">如果当前上下文中的线程上没有托管代码，则该函数将返回 SOS_E_NOMANAGEDCODE。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="5bfd9-127">`Flags` 参数为0或 SOS_STACKTRACE_SHOWADDRESSES，用于在每 `module!functionname` 行的前面查看 EBP 和 ESP。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="5bfd9-128">默认情况下，它是0。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-128">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="5bfd9-129">要求</span><span class="sxs-lookup"><span data-stu-id="5bfd9-129">Requirements</span></span>  
 <span data-ttu-id="5bfd9-130">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bfd9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bfd9-131">**标头：** SOS_Stacktrace</span><span class="sxs-lookup"><span data-stu-id="5bfd9-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="5bfd9-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bfd9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bfd9-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bfd9-133">See also</span></span>

- [<span data-ttu-id="5bfd9-134">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="5bfd9-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
