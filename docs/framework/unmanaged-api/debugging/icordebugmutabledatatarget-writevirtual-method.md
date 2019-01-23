---
title: ICorDebugMutableDataTarget::WriteVirtual 方法
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c0f07e02ee92fda772a44fe235c3dcb414882bc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495957"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="bb228-102">ICorDebugMutableDataTarget::WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="bb228-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="bb228-103">将内存写入目标进程地址空间。</span><span class="sxs-lookup"><span data-stu-id="bb228-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb228-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb228-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb228-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb228-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="bb228-106">[in] 要在此处写入 `pBuffer` 的内容的地址。</span><span class="sxs-lookup"><span data-stu-id="bb228-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="bb228-107">[in] 指向包含要写入字节的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="bb228-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="bb228-108">[in] `pBuffer` 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="bb228-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb228-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bb228-109">Return Value</span></span>  
 <span data-ttu-id="bb228-110">若成功，则为`S_OK`若失败，则为 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="bb228-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb228-111">备注</span><span class="sxs-lookup"><span data-stu-id="bb228-111">Remarks</span></span>  
 <span data-ttu-id="bb228-112">如果无法写入任何字节，方法调用失败且不更改目标地址空间中的任何字节。</span><span class="sxs-lookup"><span data-stu-id="bb228-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="bb228-113">（否则，目标状态不一致，从而使进一步的调试不可靠。）</span><span class="sxs-lookup"><span data-stu-id="bb228-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb228-114">要求</span><span class="sxs-lookup"><span data-stu-id="bb228-114">Requirements</span></span>  
 <span data-ttu-id="bb228-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb228-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb228-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb228-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb228-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb228-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb228-118">**.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb228-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb228-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb228-119">See also</span></span>
- [<span data-ttu-id="bb228-120">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="bb228-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="bb228-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="bb228-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
