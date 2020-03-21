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
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178655"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="9181e-102">ICorDebugProcess::ReadMemory 方法</span><span class="sxs-lookup"><span data-stu-id="9181e-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="9181e-103">读取此过程的指定内存区域。</span><span class="sxs-lookup"><span data-stu-id="9181e-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9181e-104">语法</span><span class="sxs-lookup"><span data-stu-id="9181e-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9181e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="9181e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="9181e-106">[在]指定`CORDB_ADDRESS`要读取的内存的基本地址的值。</span><span class="sxs-lookup"><span data-stu-id="9181e-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="9181e-107">[在]要从内存中读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="9181e-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9181e-108">[出]接收内存内容的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9181e-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="9181e-109">[出]指向传输到指定缓冲区的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="9181e-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9181e-110">备注</span><span class="sxs-lookup"><span data-stu-id="9181e-110">Remarks</span></span>  
 <span data-ttu-id="9181e-111">该方法`ReadMemory`主要用于内部调试，以检查调试器的非托管部分正在使用的内存区域。</span><span class="sxs-lookup"><span data-stu-id="9181e-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="9181e-112">此方法还可用于读取 Microsoft 中间语言 （MSIL） 代码和本机 JIT 编译代码。</span><span class="sxs-lookup"><span data-stu-id="9181e-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="9181e-113">任何托管断点都将从`buffer`参数中返回的数据中删除。</span><span class="sxs-lookup"><span data-stu-id="9181e-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="9181e-114">[ICorDebugProcess2：：：setUn托管断点](icordebugprocess2-setunmanagedbreakpoint-method.md)设置的本机断点不会进行调整。</span><span class="sxs-lookup"><span data-stu-id="9181e-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="9181e-115">不执行进程内存的缓存。</span><span class="sxs-lookup"><span data-stu-id="9181e-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9181e-116">要求</span><span class="sxs-lookup"><span data-stu-id="9181e-116">Requirements</span></span>  
 <span data-ttu-id="9181e-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9181e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9181e-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9181e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9181e-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9181e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9181e-120">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9181e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
