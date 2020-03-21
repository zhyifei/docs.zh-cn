---
title: ICLRDataTarget::WriteVirtual 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: bd2f67c2d7230d3873b4dc0df73ac1be778a0828
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179101"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="6e17c-102">ICLRDataTarget::WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="6e17c-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="6e17c-103">将数据从指定的缓冲区写入指定的虚拟内存地址。</span><span class="sxs-lookup"><span data-stu-id="6e17c-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e17c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e17c-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e17c-105">parameters</span><span class="sxs-lookup"><span data-stu-id="6e17c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="6e17c-106">[在]存储虚拟内存地址的CLRDATA_ADDRESS。</span><span class="sxs-lookup"><span data-stu-id="6e17c-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="6e17c-107">[在]指向存储要写入数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="6e17c-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="6e17c-108">[在]要写入的字节数。</span><span class="sxs-lookup"><span data-stu-id="6e17c-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="6e17c-109">[出]指向写入的实际字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="6e17c-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e17c-110">要求</span><span class="sxs-lookup"><span data-stu-id="6e17c-110">Requirements</span></span>  
 <span data-ttu-id="6e17c-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e17c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e17c-112">**标题：** ClrData.idl， ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6e17c-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6e17c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e17c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e17c-114">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e17c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e17c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e17c-115">See also</span></span>

- [<span data-ttu-id="6e17c-116">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="6e17c-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
