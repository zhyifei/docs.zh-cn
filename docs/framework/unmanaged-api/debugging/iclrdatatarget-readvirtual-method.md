---
title: ICLRDataTarget::ReadVirtual 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
ms.openlocfilehash: 0332fae46d6a65cfb7cc0b929cc2fd0d97e1790e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179146"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="d6342-102">ICLRDataTarget::ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="d6342-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="d6342-103">将数据从指定的虚拟内存地址读取到指定的缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="d6342-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6342-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6342-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6342-105">parameters</span><span class="sxs-lookup"><span data-stu-id="d6342-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="d6342-106">[在]存储虚拟内存地址的CLRDATA_ADDRESS。</span><span class="sxs-lookup"><span data-stu-id="d6342-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="d6342-107">[出]指向接收数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="d6342-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="d6342-108">[在]缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="d6342-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="d6342-109">[出]指向返回的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="d6342-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6342-110">要求</span><span class="sxs-lookup"><span data-stu-id="d6342-110">Requirements</span></span>  
 <span data-ttu-id="d6342-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6342-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6342-112">**标题：** ClrData.idl， ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d6342-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d6342-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6342-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6342-114">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6342-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6342-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6342-115">See also</span></span>

- [<span data-ttu-id="d6342-116">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="d6342-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
