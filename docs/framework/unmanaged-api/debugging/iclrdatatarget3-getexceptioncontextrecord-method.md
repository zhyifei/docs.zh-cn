---
title: "ICLRDataTarget3::GetExceptionContextRecord 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 517e2a692c3b67a85bc24437dd5fbaedd5fc7254
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="21710-102">ICLRDataTarget3::GetExceptionContextRecord 方法</span><span class="sxs-lookup"><span data-stu-id="21710-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="21710-103">由公共语言运行时 (CLR) 数据访问服务调用，以检索与目标进程关联的上下文记录。</span><span class="sxs-lookup"><span data-stu-id="21710-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="21710-104">例如，对于转储目标时，这将是等效于通过传入的上下文记录`ExceptionParam`参数[MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) Windows 调试帮助库中 (DbgHelp) 的函数。</span><span class="sxs-lookup"><span data-stu-id="21710-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21710-105">语法</span><span class="sxs-lookup"><span data-stu-id="21710-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21710-106">参数</span><span class="sxs-lookup"><span data-stu-id="21710-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="21710-107">[in] 输入缓冲区大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="21710-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="21710-108">此大小必须大到足以容纳上下文记录。</span><span class="sxs-lookup"><span data-stu-id="21710-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="21710-109">[out] 指向接收实际写入缓冲区的字节数的 `ULONG32` 类型的指针。</span><span class="sxs-lookup"><span data-stu-id="21710-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="21710-110">[out] 指向接收上下文记录副本的内存缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="21710-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="21710-111">异常记录将作为[上下文](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx)类型。</span><span class="sxs-lookup"><span data-stu-id="21710-111">The exception record is returned as a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21710-112">返回值</span><span class="sxs-lookup"><span data-stu-id="21710-112">Return Value</span></span>  
 <span data-ttu-id="21710-113">如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。</span><span class="sxs-lookup"><span data-stu-id="21710-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="21710-114">`HRESULT` 代码可以包括但不限于以下代码：</span><span class="sxs-lookup"><span data-stu-id="21710-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="21710-115">返回代码</span><span class="sxs-lookup"><span data-stu-id="21710-115">Return code</span></span>|<span data-ttu-id="21710-116">描述</span><span class="sxs-lookup"><span data-stu-id="21710-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="21710-117">方法成功。</span><span class="sxs-lookup"><span data-stu-id="21710-117">Method succeeded.</span></span> <span data-ttu-id="21710-118">已将上下文记录复制到输出缓冲区。</span><span class="sxs-lookup"><span data-stu-id="21710-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="21710-119">没有与目标关联的上下文记录。</span><span class="sxs-lookup"><span data-stu-id="21710-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="21710-120">输入缓冲区大小不足以容纳上下文记录。</span><span class="sxs-lookup"><span data-stu-id="21710-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21710-121">备注</span><span class="sxs-lookup"><span data-stu-id="21710-121">Remarks</span></span>  
 <span data-ttu-id="21710-122">[上下文](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx)是由 Windows SDK 提供的标头中定义的特定于平台的结构。</span><span class="sxs-lookup"><span data-stu-id="21710-122">[CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="21710-123">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="21710-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21710-124">惠?</span><span class="sxs-lookup"><span data-stu-id="21710-124">Requirements</span></span>  
 <span data-ttu-id="21710-125">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21710-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21710-126">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="21710-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="21710-127">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21710-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21710-128">**.NET framework 版本：**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21710-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21710-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="21710-129">See Also</span></span>  
 [<span data-ttu-id="21710-130">ICLRDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="21710-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="21710-131">GetExceptionRecord 方法</span><span class="sxs-lookup"><span data-stu-id="21710-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [<span data-ttu-id="21710-132">GetExceptionThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="21710-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
