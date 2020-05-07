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
ms.openlocfilehash: a725aa2c0f1fdea523bbf7cba880bc805f855782
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860736"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="36253-102">\_EFN\_StackTrace 函数</span><span class="sxs-lookup"><span data-stu-id="36253-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="36253-103">提供托管堆栈跟踪的文本表示形式以及 `CONTEXT` 记录的数组，其中每项对应非托管代码和托管代码之间的每个转换。</span><span class="sxs-lookup"><span data-stu-id="36253-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36253-104">语法</span><span class="sxs-lookup"><span data-stu-id="36253-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="36253-105">参数</span><span class="sxs-lookup"><span data-stu-id="36253-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="36253-106">中正在调试的客户端。</span><span class="sxs-lookup"><span data-stu-id="36253-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="36253-107">弄堆栈跟踪的文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="36253-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="36253-108">弄一个指针，指向中`wszTextOut`的字符数。</span><span class="sxs-lookup"><span data-stu-id="36253-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="36253-109">弄转换上下文的数组。</span><span class="sxs-lookup"><span data-stu-id="36253-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="36253-110">弄指向数组中的转换上下文数的指针。</span><span class="sxs-lookup"><span data-stu-id="36253-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="36253-111">中上下文结构的大小。</span><span class="sxs-lookup"><span data-stu-id="36253-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="36253-112">中设置为0或 SOS_STACKTRACE_SHOWADDRESSES （0x01）以显示 EBP 寄存器，并在每`module!functionname`行前面设置输入堆栈指针（ESP）。</span><span class="sxs-lookup"><span data-stu-id="36253-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36253-113">备注</span><span class="sxs-lookup"><span data-stu-id="36253-113">Remarks</span></span>  
 <span data-ttu-id="36253-114">此`_EFN_StackTrace`结构可从 WinDbg 编程界面调用。</span><span class="sxs-lookup"><span data-stu-id="36253-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="36253-115">参数的使用方式如下：</span><span class="sxs-lookup"><span data-stu-id="36253-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="36253-116">如果`wszTextOut`为 null 且`puiTextLength`不为 null，则该函数将返回中`puiTextLength`的字符串长度。</span><span class="sxs-lookup"><span data-stu-id="36253-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="36253-117">如果`wszTextOut`不为 null，则该函数将文本`wszTextOut`存储到指示的位置`puiTextLength`。</span><span class="sxs-lookup"><span data-stu-id="36253-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="36253-118">如果缓冲区中有足够的空间，则它将成功返回，如果缓冲区不够长，则返回 E_OUTOFMEMORY。</span><span class="sxs-lookup"><span data-stu-id="36253-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="36253-119">如果`pTransitionContexts`和都为 null， `puiTransitionContextCount`则忽略函数的转换部分。</span><span class="sxs-lookup"><span data-stu-id="36253-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="36253-120">在这种情况下，函数向调用方提供仅包含函数名称的文本输出。</span><span class="sxs-lookup"><span data-stu-id="36253-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="36253-121">如果`pTransitionContexts`为 null 且`puiTransitionContextCount`不为 null，则该函数将在中`puiTransitionContextCount`返回所需数量的上下文项。</span><span class="sxs-lookup"><span data-stu-id="36253-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="36253-122">如果`pTransitionContexts`不为 null，则函数会将其视为长度`puiTransitionContextCount`的结构数组。</span><span class="sxs-lookup"><span data-stu-id="36253-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="36253-123">结构大小由`uiSizeOfContext`指定，并且必须是[SimpleContext](stacktrace-simplecontext-structure.md)的大小或`CONTEXT`体系结构的大小。</span><span class="sxs-lookup"><span data-stu-id="36253-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="36253-124">`wszTextOut`采用以下格式编写：</span><span class="sxs-lookup"><span data-stu-id="36253-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="36253-125">如果偏移量（十六进制）为0x0，则不写入偏移量。</span><span class="sxs-lookup"><span data-stu-id="36253-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="36253-126">如果线程上当前没有托管代码，该函数将返回 SOS_E_NOMANAGEDCODE。</span><span class="sxs-lookup"><span data-stu-id="36253-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="36253-127">`Flags`参数为0或 SOS_STACKTRACE_SHOWADDRESSES，以在每`module!functionname`行的前面显示 EBP 和 ESP。</span><span class="sxs-lookup"><span data-stu-id="36253-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="36253-128">默认情况下，它是0。</span><span class="sxs-lookup"><span data-stu-id="36253-128">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="36253-129">要求</span><span class="sxs-lookup"><span data-stu-id="36253-129">Requirements</span></span>  
 <span data-ttu-id="36253-130">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="36253-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36253-131">**标头：** SOS_Stacktrace。h</span><span class="sxs-lookup"><span data-stu-id="36253-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="36253-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36253-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36253-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36253-133">See also</span></span>

- [<span data-ttu-id="36253-134">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="36253-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
