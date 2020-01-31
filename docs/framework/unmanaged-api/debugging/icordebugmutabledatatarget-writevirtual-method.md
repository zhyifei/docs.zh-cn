---
title: ICorDebugMutableDataTarget::WriteVirtual 方法
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 2b4bd1dc97f37f5a514ab54f9e4d778fe3b91736
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792835"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="5b20d-102">ICorDebugMutableDataTarget::WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="5b20d-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="5b20d-103">将内存写入目标进程地址空间。</span><span class="sxs-lookup"><span data-stu-id="5b20d-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b20d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5b20d-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b20d-105">参数</span><span class="sxs-lookup"><span data-stu-id="5b20d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5b20d-106">[in] 要在此处写入 `pBuffer` 的内容的地址。</span><span class="sxs-lookup"><span data-stu-id="5b20d-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="5b20d-107">[in] 指向包含要写入字节的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="5b20d-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="5b20d-108">[in] `pBuffer` 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="5b20d-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b20d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5b20d-109">Return Value</span></span>  
 <span data-ttu-id="5b20d-110">若成功，则为`S_OK`若失败，则为 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="5b20d-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b20d-111">备注</span><span class="sxs-lookup"><span data-stu-id="5b20d-111">Remarks</span></span>  
 <span data-ttu-id="5b20d-112">如果无法写入任何字节，方法调用失败且不更改目标地址空间中的任何字节。</span><span class="sxs-lookup"><span data-stu-id="5b20d-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="5b20d-113">（否则，目标状态不一致，从而使进一步的调试不可靠。）</span><span class="sxs-lookup"><span data-stu-id="5b20d-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b20d-114">需求</span><span class="sxs-lookup"><span data-stu-id="5b20d-114">Requirements</span></span>  
 <span data-ttu-id="5b20d-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b20d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b20d-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b20d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b20d-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b20d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b20d-118">**.NET Framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b20d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b20d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b20d-119">See also</span></span>

- [<span data-ttu-id="5b20d-120">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="5b20d-120">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="5b20d-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="5b20d-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
