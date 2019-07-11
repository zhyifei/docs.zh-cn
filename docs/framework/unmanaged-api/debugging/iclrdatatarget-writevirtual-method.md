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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0ad4b7e907412aced911d7869ffce81eb867448
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738516"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="bb3f2-102">ICLRDataTarget::WriteVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="bb3f2-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="bb3f2-103">将数据从指定的缓冲区写入到指定的虚拟内存地址。</span><span class="sxs-lookup"><span data-stu-id="bb3f2-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb3f2-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb3f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb3f2-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="bb3f2-106">[in]存储的虚拟内存地址 CLRDATA_ADDRESS。</span><span class="sxs-lookup"><span data-stu-id="bb3f2-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="bb3f2-107">[in]指向存储的数据要写入的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="bb3f2-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="bb3f2-108">[in]要写入的字节数。</span><span class="sxs-lookup"><span data-stu-id="bb3f2-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="bb3f2-109">[out]指向实际写入的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="bb3f2-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb3f2-110">要求</span><span class="sxs-lookup"><span data-stu-id="bb3f2-110">Requirements</span></span>  
 <span data-ttu-id="bb3f2-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3f2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb3f2-112">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bb3f2-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bb3f2-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb3f2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb3f2-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb3f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3f2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb3f2-115">See also</span></span>

- [<span data-ttu-id="bb3f2-116">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="bb3f2-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
