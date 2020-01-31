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
ms.openlocfilehash: 20cea94961a250c3981d892910da1dcee20a060b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783741"
---
# <a name="icordebugdatatargetreadvirtual-method"></a><span data-ttu-id="d8219-102">ICorDebugDataTarget::ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="d8219-102">ICorDebugDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="d8219-103">获取从指定地址开始的连续内存块，并将其返回到提供的缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="d8219-103">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8219-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8219-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8219-105">参数</span><span class="sxs-lookup"><span data-stu-id="d8219-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d8219-106">中请求的内存的开始地址。</span><span class="sxs-lookup"><span data-stu-id="d8219-106">[in] The start address of requested memory.</span></span>  
  
 `pbuffer`  
 <span data-ttu-id="d8219-107">弄内存将存储到的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d8219-107">[out] The buffer where the memory will be stored.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="d8219-108">中要从目标地址获取的字节数。</span><span class="sxs-lookup"><span data-stu-id="d8219-108">[in] The number of bytes to get from the target address.</span></span>  
  
 `pBytesRead`  
 <span data-ttu-id="d8219-109">弄实际从目标地址中读取的字节数。</span><span class="sxs-lookup"><span data-stu-id="d8219-109">[out] The number of bytes actually read from the target address.</span></span> <span data-ttu-id="d8219-110">这可以少于 `bytesRequested`。</span><span class="sxs-lookup"><span data-stu-id="d8219-110">This can be fewer than `bytesRequested`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8219-111">备注</span><span class="sxs-lookup"><span data-stu-id="d8219-111">Remarks</span></span>  
 <span data-ttu-id="d8219-112">如果可以读取第一个字节（在指定的起始地址），则调用应返回 success （以支持通过自描述长度（例如，以 null 结尾的字符串）进行数据结构的有效读取。</span><span class="sxs-lookup"><span data-stu-id="d8219-112">If the first byte (at the specified start address) can be read, the call should return success (to support efficient reading of data structures with self-describing length, like null-terminated strings).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8219-113">需求</span><span class="sxs-lookup"><span data-stu-id="d8219-113">Requirements</span></span>  
 <span data-ttu-id="d8219-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8219-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8219-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8219-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8219-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8219-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8219-117">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8219-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8219-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8219-118">See also</span></span>

- [<span data-ttu-id="d8219-119">ICorDebugDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="d8219-119">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="d8219-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="d8219-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d8219-121">调试</span><span class="sxs-lookup"><span data-stu-id="d8219-121">Debugging</span></span>](index.md)
