---
title: ICorDebugProcess::ReadMemory 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 218279684304b766a9bf009f5891ac4910254a3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994378"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="702e4-102">ICorDebugProcess::ReadMemory 方法</span><span class="sxs-lookup"><span data-stu-id="702e4-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="702e4-103">读取此进程的内存的指定的区域。</span><span class="sxs-lookup"><span data-stu-id="702e4-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="702e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="702e4-104">Syntax</span></span>  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="702e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="702e4-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="702e4-106">[in]一个`CORDB_ADDRESS`值，该值指定要读取的内存的基址。</span><span class="sxs-lookup"><span data-stu-id="702e4-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="702e4-107">[in]要从内存读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="702e4-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="702e4-108">[out]该缓冲区用于接收内存的内容。</span><span class="sxs-lookup"><span data-stu-id="702e4-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="702e4-109">[out]到指定的缓冲区传输到的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="702e4-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="702e4-110">备注</span><span class="sxs-lookup"><span data-stu-id="702e4-110">Remarks</span></span>  
 <span data-ttu-id="702e4-111">`ReadMemory`方法主要用于通过互操作调试用于检查正在使用的调试对象的非托管部分的内存区域。</span><span class="sxs-lookup"><span data-stu-id="702e4-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="702e4-112">此方法还可以用于读取 Microsoft 中间语言 (MSIL) 代码和 JIT 编译的本机代码。</span><span class="sxs-lookup"><span data-stu-id="702e4-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="702e4-113">将从中返回的数据中删除任何托管的断点`buffer`参数。</span><span class="sxs-lookup"><span data-stu-id="702e4-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="702e4-114">为本机断点集将进行任何调整[ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)。</span><span class="sxs-lookup"><span data-stu-id="702e4-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="702e4-115">执行进程内存没有缓存。</span><span class="sxs-lookup"><span data-stu-id="702e4-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="702e4-116">要求</span><span class="sxs-lookup"><span data-stu-id="702e4-116">Requirements</span></span>  
 <span data-ttu-id="702e4-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="702e4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="702e4-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="702e4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="702e4-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="702e4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="702e4-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="702e4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
