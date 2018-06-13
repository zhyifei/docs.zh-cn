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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6da4c282c7f969a406a657d1e30dd6120a32b4e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420903"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="7c0a2-102">ICorDebugProcess::WriteMemory 方法</span><span class="sxs-lookup"><span data-stu-id="7c0a2-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="7c0a2-103">将数据写入的此进程中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c0a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c0a2-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c0a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c0a2-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="7c0a2-106">[in]A`CORDB_ADDRESS`写入到的数据的内存区域的基址的值。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="7c0a2-107">数据传输发生之前，系统将验证开始的基址的指定大小的内存区域可以进行写入访问。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="7c0a2-108">如果它是不可访问，该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="7c0a2-109">[in]要写入到内存区域的字节数。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="7c0a2-110">[in]包含要写入的数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="7c0a2-111">[out]指向一个变量来接收此过程中的内存区域写入的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="7c0a2-112">如果`written`为 NULL，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c0a2-113">备注</span><span class="sxs-lookup"><span data-stu-id="7c0a2-113">Remarks</span></span>  
 <span data-ttu-id="7c0a2-114">在任意断点后，会自动写入数据。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="7c0a2-115">在.NET Framework 2.0 版中，本机调试器不应使用此方法来插入指令流的断点。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="7c0a2-116">使用[icordebugprocess2:: Setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="7c0a2-117">`WriteMemory`方法应仅在托管代码之外使用。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="7c0a2-118">如果使用不正确，此方法会损坏运行时。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c0a2-119">要求</span><span class="sxs-lookup"><span data-stu-id="7c0a2-119">Requirements</span></span>  
 <span data-ttu-id="7c0a2-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c0a2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0a2-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c0a2-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c0a2-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c0a2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c0a2-123">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0a2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
