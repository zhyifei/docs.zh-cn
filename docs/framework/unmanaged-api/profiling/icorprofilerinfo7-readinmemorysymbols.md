---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3df5324e23ebeded38f3aa9843f81701f7fd333
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251052"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="59ece-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="59ece-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="59ece-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="59ece-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="59ece-104">从内存中的符号流读取字节数。</span><span class="sxs-lookup"><span data-stu-id="59ece-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ece-105">语法</span><span class="sxs-lookup"><span data-stu-id="59ece-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59ece-106">参数</span><span class="sxs-lookup"><span data-stu-id="59ece-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="59ece-107">[in]包含内存中流的模块标识符。</span><span class="sxs-lookup"><span data-stu-id="59ece-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="59ece-108">[in]在开始读取字节的内存中流内的偏移量。</span><span class="sxs-lookup"><span data-stu-id="59ece-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="59ece-109">[out]指向数据将复制到其中的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="59ece-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="59ece-110">缓冲区应具有`countSymbolBytes`的可用空间。</span><span class="sxs-lookup"><span data-stu-id="59ece-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="59ece-111">[in]要复制的字节数。</span><span class="sxs-lookup"><span data-stu-id="59ece-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="59ece-112">[out]方法返回时，包含实际读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="59ece-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59ece-113">返回值</span><span class="sxs-lookup"><span data-stu-id="59ece-113">Return Value</span></span>  
 <span data-ttu-id="59ece-114">`S_OK`如果已读取的字节非零值数。</span><span class="sxs-lookup"><span data-stu-id="59ece-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="59ece-115">`CORPROF_E_MODULE_IS_DYNAMIC`如果该模块使用创建<xref:System.Reflection.Emit>。</span><span class="sxs-lookup"><span data-stu-id="59ece-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59ece-116">备注</span><span class="sxs-lookup"><span data-stu-id="59ece-116">Remarks</span></span>  
 <span data-ttu-id="59ece-117">`ReadInMemorySymbols`方法会尝试读取`countSymbolBytes`的数据偏移量开始`symbolsReadOffset`中内存流中。</span><span class="sxs-lookup"><span data-stu-id="59ece-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="59ece-118">将数据复制到`pSymbolBytes`，这都必须具有`countSymbolBytes`的可用空间。</span><span class="sxs-lookup"><span data-stu-id="59ece-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="59ece-119">`pCountSymbolsBytesRead` 包含实际读取，这可能会更少的字节数比`countSymbolBytes`如果到达流的末尾。</span><span class="sxs-lookup"><span data-stu-id="59ece-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59ece-120">当前实现不支持 Reflection.Emit。</span><span class="sxs-lookup"><span data-stu-id="59ece-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="59ece-121">如果通过使用 Reflection.Emit 创建模块，该方法返回`CORPROF_E_MODULE_IS_DYNAMIC`。</span><span class="sxs-lookup"><span data-stu-id="59ece-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59ece-122">要求</span><span class="sxs-lookup"><span data-stu-id="59ece-122">Requirements</span></span>  
 <span data-ttu-id="59ece-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="59ece-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59ece-124">**标头：** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59ece-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59ece-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59ece-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59ece-126">**.NET Framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59ece-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ece-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="59ece-127">See also</span></span>

- [<span data-ttu-id="59ece-128">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="59ece-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
