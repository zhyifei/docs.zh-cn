---
title: ICorDebugDataTarget::ReadVirtual 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4749bfee22e58ad7c3ca29ec992da88493ca2c5c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763836"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="20345-102">ICorDebugDataTarget::ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="20345-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="20345-103">获取从指定地址处开始的连续内存块，并返回它所提供的缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="20345-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20345-104">语法</span><span class="sxs-lookup"><span data-stu-id="20345-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20345-105">参数</span><span class="sxs-lookup"><span data-stu-id="20345-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="20345-106">[in]起始地址的请求的内存。</span><span class="sxs-lookup"><span data-stu-id="20345-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="20345-107">[out]将在其中存储内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="20345-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="20345-108">[in]要从目标地址中获取的字节数。</span><span class="sxs-lookup"><span data-stu-id="20345-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="20345-109">[out]从目标地址实际读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="20345-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="20345-110">这可以是少于`bytesRequested`。</span><span class="sxs-lookup"><span data-stu-id="20345-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20345-111">备注</span><span class="sxs-lookup"><span data-stu-id="20345-111">Remarks</span></span>  
 <span data-ttu-id="20345-112">如果可以读取 （在指定的开始地址） 的第一个字节，则调用应返回成功 （若要支持高效读取的数据结构使用自我描述长度，类似于以 null 结尾的字符串）。</span><span class="sxs-lookup"><span data-stu-id="20345-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20345-113">要求</span><span class="sxs-lookup"><span data-stu-id="20345-113">Requirements</span></span>  
 <span data-ttu-id="20345-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20345-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20345-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20345-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20345-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20345-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20345-117">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20345-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20345-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="20345-118">See also</span></span>

- [<span data-ttu-id="20345-119">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="20345-119">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="20345-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="20345-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="20345-121">调试</span><span class="sxs-lookup"><span data-stu-id="20345-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
