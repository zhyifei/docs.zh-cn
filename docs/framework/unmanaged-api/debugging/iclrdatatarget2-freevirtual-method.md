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
ms.openlocfilehash: 02bba59a1c4445b3e432d5e44f2bccc4b72ce1da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711650"
---
# <a name="iclrdatatarget2freevirtual-method"></a><span data-ttu-id="99e0a-102">ICLRDataTarget2::FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="99e0a-102">ICLRDataTarget2::FreeVirtual Method</span></span>
<span data-ttu-id="99e0a-103">由以前分配的目标进程的地址空间中的可用内存为公共语言运行时 (CLR) 数据访问服务调用。</span><span class="sxs-lookup"><span data-stu-id="99e0a-103">Called by the common language runtime (CLR) data access services to free memory that was previously allocated in the address space of the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e0a-104">语法</span><span class="sxs-lookup"><span data-stu-id="99e0a-104">Syntax</span></span>  
  
```  
HRESULT FreeVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99e0a-105">参数</span><span class="sxs-lookup"><span data-stu-id="99e0a-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="99e0a-106">[in]一个`CLRDATA_ADDRESS`值，该值指定要释放的内存的起始地址。</span><span class="sxs-lookup"><span data-stu-id="99e0a-106">[in] A `CLRDATA_ADDRESS` value that specifies the starting address of the memory to be freed.</span></span>  
  
 `size`  
 <span data-ttu-id="99e0a-107">[in]以字节为单位，要释放的内存的大小。</span><span class="sxs-lookup"><span data-stu-id="99e0a-107">[in] The size, in bytes, of the memory to be freed.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="99e0a-108">[in]控制释放内存的标志。</span><span class="sxs-lookup"><span data-stu-id="99e0a-108">[in] Flags that control the freeing of memory.</span></span> <span data-ttu-id="99e0a-109">请参阅 Win32`VirtualFree`函数。</span><span class="sxs-lookup"><span data-stu-id="99e0a-109">See the Win32 `VirtualFree` function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99e0a-110">备注</span><span class="sxs-lookup"><span data-stu-id="99e0a-110">Remarks</span></span>  
 <span data-ttu-id="99e0a-111">`FreeVirtual`方法用作逻辑包装为 Win32`VirtualFree`函数。</span><span class="sxs-lookup"><span data-stu-id="99e0a-111">The `FreeVirtual` method serves as a logical wrapper for the Win32 `VirtualFree` function.</span></span>  
  
 <span data-ttu-id="99e0a-112">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="99e0a-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99e0a-113">要求</span><span class="sxs-lookup"><span data-stu-id="99e0a-113">Requirements</span></span>  
 <span data-ttu-id="99e0a-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="99e0a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99e0a-115">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="99e0a-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="99e0a-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99e0a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99e0a-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99e0a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e0a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="99e0a-118">See also</span></span>
- [<span data-ttu-id="99e0a-119">ICLRDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="99e0a-119">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="99e0a-120">AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="99e0a-120">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)
