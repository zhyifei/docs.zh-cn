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
ms.openlocfilehash: 53c01d2db44f4d0adf1ba5b9cc225ab49581aa5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868338"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="649e8-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="649e8-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="649e8-103">[仅在 .NET Framework 4.6.1 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="649e8-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="649e8-104">从内存中的符号流中读取字节。</span><span class="sxs-lookup"><span data-stu-id="649e8-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="649e8-105">语法</span><span class="sxs-lookup"><span data-stu-id="649e8-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="649e8-106">参数</span><span class="sxs-lookup"><span data-stu-id="649e8-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="649e8-107">中包含内存中流的模块的标识符。</span><span class="sxs-lookup"><span data-stu-id="649e8-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="649e8-108">中内存中流中的偏移量，从此处开始读取字节。</span><span class="sxs-lookup"><span data-stu-id="649e8-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="649e8-109">弄指向数据将复制到的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="649e8-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="649e8-110">缓冲区的可用空间应 `countSymbolBytes`。</span><span class="sxs-lookup"><span data-stu-id="649e8-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="649e8-111">中要复制的字节数。</span><span class="sxs-lookup"><span data-stu-id="649e8-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="649e8-112">弄当该方法返回时，包含所读取的实际字节数。</span><span class="sxs-lookup"><span data-stu-id="649e8-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="649e8-113">返回值</span><span class="sxs-lookup"><span data-stu-id="649e8-113">Return Value</span></span>  
 <span data-ttu-id="649e8-114">如果读取了非零字节数，则 `S_OK`。</span><span class="sxs-lookup"><span data-stu-id="649e8-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="649e8-115">如果该模块是使用 <xref:System.Reflection.Emit>创建的 `CORPROF_E_MODULE_IS_DYNAMIC`，则为。</span><span class="sxs-lookup"><span data-stu-id="649e8-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="649e8-116">备注</span><span class="sxs-lookup"><span data-stu-id="649e8-116">Remarks</span></span>  
 <span data-ttu-id="649e8-117">`ReadInMemorySymbols` 方法尝试读取内存中流中 `symbolsReadOffset` 偏移开始的数据 `countSymbolBytes`。</span><span class="sxs-lookup"><span data-stu-id="649e8-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="649e8-118">数据将复制到 `pSymbolBytes`，这应该具有可用的空间 `countSymbolBytes`。</span><span class="sxs-lookup"><span data-stu-id="649e8-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="649e8-119">`pCountSymbolsBytesRead` 包含读取的实际字节数，如果已到达流的末尾，则该值可能小于 `countSymbolBytes`。</span><span class="sxs-lookup"><span data-stu-id="649e8-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="649e8-120">当前实现不支持反射。发出。</span><span class="sxs-lookup"><span data-stu-id="649e8-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="649e8-121">如果该模块是使用反射创建的，则该方法将返回 `CORPROF_E_MODULE_IS_DYNAMIC`。</span><span class="sxs-lookup"><span data-stu-id="649e8-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="649e8-122">需求</span><span class="sxs-lookup"><span data-stu-id="649e8-122">Requirements</span></span>  
 <span data-ttu-id="649e8-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="649e8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="649e8-124">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="649e8-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="649e8-125">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="649e8-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="649e8-126">**.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="649e8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="649e8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="649e8-127">See also</span></span>

- [<span data-ttu-id="649e8-128">ICorProfilerInfo7 接口</span><span class="sxs-lookup"><span data-stu-id="649e8-128">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
