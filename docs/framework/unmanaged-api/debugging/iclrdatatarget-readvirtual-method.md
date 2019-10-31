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
ms.openlocfilehash: 0c26a2df3f73af5ebd1f8b735d7662bb23ba4228
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134164"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="45d3c-102">ICLRDataTarget::ReadVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="45d3c-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="45d3c-103">将数据从指定的虚拟内存地址读入指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="45d3c-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d3c-104">语法</span><span class="sxs-lookup"><span data-stu-id="45d3c-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45d3c-105">参数</span><span class="sxs-lookup"><span data-stu-id="45d3c-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="45d3c-106">中存储虚拟内存地址的 CLRDATA_ADDRESS。</span><span class="sxs-lookup"><span data-stu-id="45d3c-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="45d3c-107">弄指向接收数据的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="45d3c-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="45d3c-108">中缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="45d3c-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="45d3c-109">弄指向返回的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="45d3c-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45d3c-110">要求</span><span class="sxs-lookup"><span data-stu-id="45d3c-110">Requirements</span></span>  
 <span data-ttu-id="45d3c-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45d3c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45d3c-112">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="45d3c-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="45d3c-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45d3c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45d3c-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45d3c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d3c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="45d3c-115">See also</span></span>

- [<span data-ttu-id="45d3c-116">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="45d3c-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
