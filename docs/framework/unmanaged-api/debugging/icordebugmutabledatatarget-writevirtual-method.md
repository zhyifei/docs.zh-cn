---
title: ICorDebugMutableDataTarget::WriteVirtual 方法
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 6325dba99fba0ab5e2f752a0635fdd428d3065eb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206745"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="97c83-102">ICorDebugMutableDataTarget::WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="97c83-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="97c83-103">将内存写入目标进程地址空间。</span><span class="sxs-lookup"><span data-stu-id="97c83-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c83-104">语法</span><span class="sxs-lookup"><span data-stu-id="97c83-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97c83-105">参数</span><span class="sxs-lookup"><span data-stu-id="97c83-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="97c83-106">[in] 要在此处写入 `pBuffer` 的内容的地址。</span><span class="sxs-lookup"><span data-stu-id="97c83-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="97c83-107">[in] 指向包含要写入字节的字节数组的指针。</span><span class="sxs-lookup"><span data-stu-id="97c83-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="97c83-108">[in] `pBuffer` 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="97c83-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97c83-109">返回值</span><span class="sxs-lookup"><span data-stu-id="97c83-109">Return Value</span></span>  
 <span data-ttu-id="97c83-110">若成功，则为`S_OK`若失败，则为 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="97c83-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97c83-111">备注</span><span class="sxs-lookup"><span data-stu-id="97c83-111">Remarks</span></span>  
 <span data-ttu-id="97c83-112">如果无法写入任何字节，方法调用失败且不更改目标地址空间中的任何字节。</span><span class="sxs-lookup"><span data-stu-id="97c83-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="97c83-113">（否则，目标状态不一致，从而使进一步的调试不可靠。）</span><span class="sxs-lookup"><span data-stu-id="97c83-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97c83-114">要求</span><span class="sxs-lookup"><span data-stu-id="97c83-114">Requirements</span></span>  
 <span data-ttu-id="97c83-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97c83-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97c83-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97c83-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97c83-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97c83-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97c83-118">**.NET Framework 版本：**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97c83-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c83-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="97c83-119">See also</span></span>

- [<span data-ttu-id="97c83-120">ICorDebugMutableDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="97c83-120">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="97c83-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="97c83-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
