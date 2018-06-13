---
title: ICLRDataTarget2::AllocVirtual 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.AllocVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46532592057f4fa6d9883d46dcef2f8f9e5f7228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406339"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="6313e-102">ICLRDataTarget2::AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="6313e-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="6313e-103">调用由公共语言运行时 (CLR) 数据访问服务以中此目标进程的地址空间分配内存。</span><span class="sxs-lookup"><span data-stu-id="6313e-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6313e-104">语法</span><span class="sxs-lookup"><span data-stu-id="6313e-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6313e-105">参数</span><span class="sxs-lookup"><span data-stu-id="6313e-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="6313e-106">[in]A`CLRDATA_ADDRESS`值，该值指定要分配的内存的请求的起始地址。</span><span class="sxs-lookup"><span data-stu-id="6313e-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="6313e-107">[in]以字节为单位，要分配的内存的大小。</span><span class="sxs-lookup"><span data-stu-id="6313e-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="6313e-108">[in]控制的内存分配的标志。</span><span class="sxs-lookup"><span data-stu-id="6313e-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="6313e-109">请参阅 Win32`VirtualAlloc`函数。</span><span class="sxs-lookup"><span data-stu-id="6313e-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="6313e-110">[in]分配的内存保护特性。</span><span class="sxs-lookup"><span data-stu-id="6313e-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="6313e-111">请参阅 Win32`VirtualAlloc`函数。</span><span class="sxs-lookup"><span data-stu-id="6313e-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="6313e-112">[out]指向的指针`CLRDATA_ADDRESS`值，该值指定分配的内存的实际起始地址。</span><span class="sxs-lookup"><span data-stu-id="6313e-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6313e-113">备注</span><span class="sxs-lookup"><span data-stu-id="6313e-113">Remarks</span></span>  
 <span data-ttu-id="6313e-114">`AllocVirtual`方法用作的逻辑包装为 Win32`VirtualAlloc`函数。</span><span class="sxs-lookup"><span data-stu-id="6313e-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="6313e-115">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="6313e-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6313e-116">要求</span><span class="sxs-lookup"><span data-stu-id="6313e-116">Requirements</span></span>  
 <span data-ttu-id="6313e-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6313e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6313e-118">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6313e-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6313e-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6313e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6313e-120">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6313e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6313e-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="6313e-121">See Also</span></span>  
 [<span data-ttu-id="6313e-122">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="6313e-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="6313e-123">FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="6313e-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
