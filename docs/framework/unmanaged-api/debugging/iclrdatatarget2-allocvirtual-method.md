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
ms.openlocfilehash: 7640f7fafd0bf52a302ac0da1e5df39b5da22d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091146"
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="ae23d-102">ICLRDataTarget2::AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="ae23d-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="ae23d-103">由公共语言运行时（CLR）数据访问服务调用，以在此目标进程的地址空间中分配内存。</span><span class="sxs-lookup"><span data-stu-id="ae23d-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae23d-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae23d-104">Syntax</span></span>  
  
```cpp  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae23d-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae23d-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="ae23d-106">中一个 `CLRDATA_ADDRESS` 值，该值指定要分配的内存的起始地址。</span><span class="sxs-lookup"><span data-stu-id="ae23d-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="ae23d-107">中要分配的内存的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ae23d-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="ae23d-108">中控制内存分配的标志。</span><span class="sxs-lookup"><span data-stu-id="ae23d-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="ae23d-109">请参阅 Win32 `VirtualAlloc` 函数。</span><span class="sxs-lookup"><span data-stu-id="ae23d-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="ae23d-110">中已分配内存的保护特性。</span><span class="sxs-lookup"><span data-stu-id="ae23d-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="ae23d-111">请参阅 Win32 `VirtualAlloc` 函数。</span><span class="sxs-lookup"><span data-stu-id="ae23d-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="ae23d-112">弄一个指向 `CLRDATA_ADDRESS` 值的指针，该值指定分配的内存的实际起始地址。</span><span class="sxs-lookup"><span data-stu-id="ae23d-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae23d-113">备注</span><span class="sxs-lookup"><span data-stu-id="ae23d-113">Remarks</span></span>  
 <span data-ttu-id="ae23d-114">`AllocVirtual` 方法用作 Win32 `VirtualAlloc` 函数的逻辑包装。</span><span class="sxs-lookup"><span data-stu-id="ae23d-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="ae23d-115">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="ae23d-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae23d-116">要求</span><span class="sxs-lookup"><span data-stu-id="ae23d-116">Requirements</span></span>  
 <span data-ttu-id="ae23d-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae23d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae23d-118">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="ae23d-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ae23d-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae23d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae23d-120">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae23d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae23d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae23d-121">See also</span></span>

- [<span data-ttu-id="ae23d-122">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="ae23d-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="ae23d-123">FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="ae23d-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)
