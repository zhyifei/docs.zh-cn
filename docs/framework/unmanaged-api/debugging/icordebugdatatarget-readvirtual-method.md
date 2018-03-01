---
title: "ICorDebugDataTarget::ReadVirtual 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a406af14d4cb5612009972542c0efe9c1b5f62cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="a271b-102">ICorDebugDataTarget::ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="a271b-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="a271b-103">获取指定的地址处开始的连续内存块，并在提供的缓冲区中将其返回。</span><span class="sxs-lookup"><span data-stu-id="a271b-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a271b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a271b-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a271b-105">参数</span><span class="sxs-lookup"><span data-stu-id="a271b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="a271b-106">[in]起始地址的请求的内存。</span><span class="sxs-lookup"><span data-stu-id="a271b-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="a271b-107">[out]将存储内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="a271b-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="a271b-108">[in]要获得的目标地址的字节数。</span><span class="sxs-lookup"><span data-stu-id="a271b-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="a271b-109">[out]从目标地址实际读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="a271b-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="a271b-110">这可能是数不能超过`bytesRequested`。</span><span class="sxs-lookup"><span data-stu-id="a271b-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a271b-111">备注</span><span class="sxs-lookup"><span data-stu-id="a271b-111">Remarks</span></span>  
 <span data-ttu-id="a271b-112">如果可以读取 （在指定的开始地址中） 的第一个字节，则调用应返回成功 （用于支持高效读取使用自我描述长度，如以 null 结尾的字符串的数据结构）。</span><span class="sxs-lookup"><span data-stu-id="a271b-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a271b-113">惠?</span><span class="sxs-lookup"><span data-stu-id="a271b-113">Requirements</span></span>  
 <span data-ttu-id="a271b-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a271b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a271b-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a271b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a271b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a271b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a271b-117">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a271b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a271b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a271b-118">See Also</span></span>  
 [<span data-ttu-id="a271b-119">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="a271b-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="a271b-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="a271b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a271b-121">调试</span><span class="sxs-lookup"><span data-stu-id="a271b-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
