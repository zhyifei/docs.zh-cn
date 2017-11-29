---
title: "ICLRDataTarget::GetThreadContext 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 480b65b279dbc0359b078f3f1d543f63a0bfd0f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="06166-102">ICLRDataTarget::GetThreadContext 方法</span><span class="sxs-lookup"><span data-stu-id="06166-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="06166-103">获取目标进程中的给定线程的当前执行上下文。</span><span class="sxs-lookup"><span data-stu-id="06166-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="06166-104">由公共语言运行时数据访问服务调用此方法。</span><span class="sxs-lookup"><span data-stu-id="06166-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06166-105">语法</span><span class="sxs-lookup"><span data-stu-id="06166-105">Syntax</span></span>  
  
```  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06166-106">参数</span><span class="sxs-lookup"><span data-stu-id="06166-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="06166-107">[in]目标进程中线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="06166-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="06166-108">[in]指定要返回的上下文中的哪些部分的标志。</span><span class="sxs-lookup"><span data-stu-id="06166-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="06166-109">实现将返回至少这些部分的上下文。</span><span class="sxs-lookup"><span data-stu-id="06166-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="06166-110">[in]上下文的大小。</span><span class="sxs-lookup"><span data-stu-id="06166-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="06166-111">[out]指向要在其中放置上下文缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="06166-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="06166-112">中的数据`context`Win32 的格式必须为缓冲区`CONTEXT`结构。</span><span class="sxs-lookup"><span data-stu-id="06166-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="06166-113">上下文指定特定于处理器的寄存器数据，因此将 win32 定义`CONTEXT`结构取决于处理器的体系结构。</span><span class="sxs-lookup"><span data-stu-id="06166-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="06166-114">参阅 WinNT.h 中的标头文件的定义 Win32`CONTEXT`结构。</span><span class="sxs-lookup"><span data-stu-id="06166-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06166-115">备注</span><span class="sxs-lookup"><span data-stu-id="06166-115">Remarks</span></span>  
 <span data-ttu-id="06166-116">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="06166-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06166-117">要求</span><span class="sxs-lookup"><span data-stu-id="06166-117">Requirements</span></span>  
 <span data-ttu-id="06166-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06166-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06166-119">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="06166-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="06166-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06166-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06166-121">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06166-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06166-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06166-122">See Also</span></span>  
 [<span data-ttu-id="06166-123">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="06166-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
