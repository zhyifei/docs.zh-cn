---
title: ICLRDataTarget::GetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179184"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="07775-102">ICLRDataTarget::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="07775-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="07775-103">获取目标进程中给定线程的当前执行上下文。</span><span class="sxs-lookup"><span data-stu-id="07775-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="07775-104">此方法由通用语言运行时数据访问服务调用。</span><span class="sxs-lookup"><span data-stu-id="07775-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07775-105">语法</span><span class="sxs-lookup"><span data-stu-id="07775-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07775-106">parameters</span><span class="sxs-lookup"><span data-stu-id="07775-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="07775-107">[在]目标进程中线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="07775-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="07775-108">[在]指定要返回上下文的哪些部分的标志。</span><span class="sxs-lookup"><span data-stu-id="07775-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="07775-109">实现将至少返回上下文的这些部分。</span><span class="sxs-lookup"><span data-stu-id="07775-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="07775-110">[在]上下文的大小。</span><span class="sxs-lookup"><span data-stu-id="07775-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="07775-111">[出]指向要在其中放置上下文的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="07775-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="07775-112">缓冲区中`context`的数据必须采用 Win32`CONTEXT`结构的格式。</span><span class="sxs-lookup"><span data-stu-id="07775-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="07775-113">上下文指定特定于处理器的寄存器数据，因此 Win32`CONTEXT`结构的定义取决于处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="07775-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="07775-114">有关 Win32`CONTEXT`结构的定义，请参阅 WinNT.h 标头文件。</span><span class="sxs-lookup"><span data-stu-id="07775-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07775-115">备注</span><span class="sxs-lookup"><span data-stu-id="07775-115">Remarks</span></span>  
 <span data-ttu-id="07775-116">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="07775-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07775-117">要求</span><span class="sxs-lookup"><span data-stu-id="07775-117">Requirements</span></span>  
 <span data-ttu-id="07775-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="07775-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07775-119">**标题：** ClrData.idl， ClrData.h</span><span class="sxs-lookup"><span data-stu-id="07775-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="07775-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07775-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07775-121">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07775-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07775-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07775-122">See also</span></span>

- [<span data-ttu-id="07775-123">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="07775-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
