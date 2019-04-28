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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88d563918709a6cf31d9c14a52bbd461ae004420
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698299"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="e7341-102">ICLRDataTarget::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="e7341-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="e7341-103">获取目标进程中的给定线程的当前执行上下文。</span><span class="sxs-lookup"><span data-stu-id="e7341-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="e7341-104">由公共语言运行时数据访问服务调用此方法。</span><span class="sxs-lookup"><span data-stu-id="e7341-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7341-105">语法</span><span class="sxs-lookup"><span data-stu-id="e7341-105">Syntax</span></span>  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7341-106">参数</span><span class="sxs-lookup"><span data-stu-id="e7341-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e7341-107">[in]目标进程中线程的操作系统的系统标识符。</span><span class="sxs-lookup"><span data-stu-id="e7341-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="e7341-108">[in]指定要返回的上下文中的哪些部分的标志。</span><span class="sxs-lookup"><span data-stu-id="e7341-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="e7341-109">实现将返回上下文的至少包含这些部件。</span><span class="sxs-lookup"><span data-stu-id="e7341-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e7341-110">[in]上下文的大小。</span><span class="sxs-lookup"><span data-stu-id="e7341-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="e7341-111">[out]指向要在其中放置上下文缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="e7341-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="e7341-112">中的数据`context`Win32 的格式必须为缓冲区`CONTEXT`结构。</span><span class="sxs-lookup"><span data-stu-id="e7341-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="e7341-113">上下文指定特定于处理器的寄存器数据，因此定义的 Win32`CONTEXT`结构取决于处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="e7341-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="e7341-114">请参阅 WinNT.h 中的标头文件定义的 Win32`CONTEXT`结构。</span><span class="sxs-lookup"><span data-stu-id="e7341-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7341-115">备注</span><span class="sxs-lookup"><span data-stu-id="e7341-115">Remarks</span></span>  
 <span data-ttu-id="e7341-116">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="e7341-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7341-117">要求</span><span class="sxs-lookup"><span data-stu-id="e7341-117">Requirements</span></span>  
 <span data-ttu-id="e7341-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7341-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7341-119">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e7341-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e7341-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7341-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7341-121">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7341-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7341-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7341-122">See also</span></span>

- [<span data-ttu-id="e7341-123">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="e7341-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
