---
title: ICorDebugProcess::WriteMemory 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
ms.openlocfilehash: eaf5b9980d55b0efb473b4631a8c052b013d0796
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137258"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="1caf4-102">ICorDebugProcess::WriteMemory 方法</span><span class="sxs-lookup"><span data-stu-id="1caf4-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="1caf4-103">将数据写入到此进程中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="1caf4-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1caf4-104">语法</span><span class="sxs-lookup"><span data-stu-id="1caf4-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1caf4-105">参数</span><span class="sxs-lookup"><span data-stu-id="1caf4-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1caf4-106">中一个 `CORDB_ADDRESS` 值，该值是写入数据的内存区域的基址。</span><span class="sxs-lookup"><span data-stu-id="1caf4-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="1caf4-107">在进行数据传输之前，系统将验证指定大小（从基址开始）的内存区域是否可供写入。</span><span class="sxs-lookup"><span data-stu-id="1caf4-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="1caf4-108">如果不可访问，则该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="1caf4-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="1caf4-109">中要写入内存区域的字节数。</span><span class="sxs-lookup"><span data-stu-id="1caf4-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="1caf4-110">中包含要写入的数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1caf4-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="1caf4-111">弄指向一个变量的指针，该变量接收写入到此进程中的内存区域的字节数。</span><span class="sxs-lookup"><span data-stu-id="1caf4-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="1caf4-112">如果 `written` 为 NULL，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="1caf4-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1caf4-113">备注</span><span class="sxs-lookup"><span data-stu-id="1caf4-113">Remarks</span></span>  
 <span data-ttu-id="1caf4-114">数据将在任何断点后面自动写入。</span><span class="sxs-lookup"><span data-stu-id="1caf4-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="1caf4-115">在 .NET Framework 版本2.0 中，本机调试器不应使用此方法将断点注入到指令流中。</span><span class="sxs-lookup"><span data-stu-id="1caf4-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="1caf4-116">改[为使用 ICorDebugProcess2：： SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) 。</span><span class="sxs-lookup"><span data-stu-id="1caf4-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="1caf4-117">`WriteMemory` 方法只应在托管代码之外使用。</span><span class="sxs-lookup"><span data-stu-id="1caf4-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="1caf4-118">如果使用不当，此方法可能会损坏运行时。</span><span class="sxs-lookup"><span data-stu-id="1caf4-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1caf4-119">要求</span><span class="sxs-lookup"><span data-stu-id="1caf4-119">Requirements</span></span>  
 <span data-ttu-id="1caf4-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1caf4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1caf4-121">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1caf4-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1caf4-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1caf4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1caf4-123">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1caf4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
