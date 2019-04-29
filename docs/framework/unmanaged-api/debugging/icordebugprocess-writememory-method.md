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
ms.openlocfilehash: 2e9d640fb1c9dae5bb195baa504e560ba8e45821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930294"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="2db3a-102">ICorDebugProcess::WriteMemory 方法</span><span class="sxs-lookup"><span data-stu-id="2db3a-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="2db3a-103">将数据写入到的此过程中的内存区域。</span><span class="sxs-lookup"><span data-stu-id="2db3a-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db3a-104">语法</span><span class="sxs-lookup"><span data-stu-id="2db3a-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2db3a-105">参数</span><span class="sxs-lookup"><span data-stu-id="2db3a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="2db3a-106">[in]一个`CORDB_ADDRESS`写入数据的内存区域的基址的值。</span><span class="sxs-lookup"><span data-stu-id="2db3a-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="2db3a-107">在传输数据之前，系统将验证开始的位置的基址的指定大小的内存区域可以进行写入访问。</span><span class="sxs-lookup"><span data-stu-id="2db3a-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="2db3a-108">如果不能访问，该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="2db3a-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="2db3a-109">[in]要写入到的内存区域的字节数。</span><span class="sxs-lookup"><span data-stu-id="2db3a-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="2db3a-110">[in]包含要写入的数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2db3a-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="2db3a-111">[out]指向一个变量来接收此过程中的内存区域写入的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="2db3a-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="2db3a-112">如果`written`为 NULL，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="2db3a-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2db3a-113">备注</span><span class="sxs-lookup"><span data-stu-id="2db3a-113">Remarks</span></span>  
 <span data-ttu-id="2db3a-114">任何断点后自动写入数据。</span><span class="sxs-lookup"><span data-stu-id="2db3a-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="2db3a-115">在.NET Framework 2.0 版中，本机调试器应使用此方法用于将断点注入到指令流。</span><span class="sxs-lookup"><span data-stu-id="2db3a-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="2db3a-116">使用[ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)相反。</span><span class="sxs-lookup"><span data-stu-id="2db3a-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="2db3a-117">`WriteMemory`应仅之外托管代码使用方法。</span><span class="sxs-lookup"><span data-stu-id="2db3a-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="2db3a-118">如果使用不当，则此方法会损坏运行时。</span><span class="sxs-lookup"><span data-stu-id="2db3a-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db3a-119">要求</span><span class="sxs-lookup"><span data-stu-id="2db3a-119">Requirements</span></span>  
 <span data-ttu-id="2db3a-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2db3a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db3a-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2db3a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2db3a-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2db3a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2db3a-123">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2db3a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
