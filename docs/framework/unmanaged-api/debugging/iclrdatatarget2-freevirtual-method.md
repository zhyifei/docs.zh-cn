---
title: ICLRDataTarget2::FreeVirtual 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2.FreeVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2::FreeVirtual
helpviewer_keywords:
- ICLRDataTarget::FreeVirtual method [.NET Framework debugging]
- FreeVirtual method [.NET Framework debugging]
ms.assetid: 26fb69f8-1467-4711-bd24-cb117c63938f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7351dfb046653e4f3e20e0dc8a4bba8653ec36e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404643"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="86713-102">ICLRDataTarget2::FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="86713-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="86713-103">由为以前分配目标进程的地址空间中的可用内存到公共语言运行时 (CLR) 数据访问服务调用。</span><span class="sxs-lookup"><span data-stu-id="86713-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86713-104">语法</span><span class="sxs-lookup"><span data-stu-id="86713-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86713-105">参数</span><span class="sxs-lookup"><span data-stu-id="86713-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="86713-106">[in]A`CLRDATA_ADDRESS`值，该值指定要释放的内存的起始地址。</span><span class="sxs-lookup"><span data-stu-id="86713-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="86713-107">[in]以字节为单位，要被释放的内存的大小。</span><span class="sxs-lookup"><span data-stu-id="86713-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="86713-108">[in]控制释放内存的标志。</span><span class="sxs-lookup"><span data-stu-id="86713-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="86713-109">请参阅 Win32`VirtualFree`函数。</span><span class="sxs-lookup"><span data-stu-id="86713-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86713-110">备注</span><span class="sxs-lookup"><span data-stu-id="86713-110">Remarks</span></span>  
 <span data-ttu-id="86713-111">`FreeVirtual`方法用作的逻辑包装为 Win32`VirtualFree`函数。</span><span class="sxs-lookup"><span data-stu-id="86713-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="86713-112">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="86713-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86713-113">要求</span><span class="sxs-lookup"><span data-stu-id="86713-113">Requirements</span></span>  
 <span data-ttu-id="86713-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86713-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86713-115">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="86713-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="86713-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86713-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86713-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86713-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86713-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="86713-118">See Also</span></span>  
 [<span data-ttu-id="86713-119">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="86713-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="86713-120">AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="86713-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
