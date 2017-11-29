---
title: "ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b1897b18a8dcbb261a5041ca8b530b7877b910
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="01f8a-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 方法</span><span class="sxs-lookup"><span data-stu-id="01f8a-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="01f8a-103">由调用[iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="01f8a-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="01f8a-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01f8a-105">参数</span><span class="sxs-lookup"><span data-stu-id="01f8a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="01f8a-106">[in]是要枚举的内存区域起始地址。</span><span class="sxs-lookup"><span data-stu-id="01f8a-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="01f8a-107">[in]以字节为单位的内存区域的大小。</span><span class="sxs-lookup"><span data-stu-id="01f8a-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01f8a-108">备注</span><span class="sxs-lookup"><span data-stu-id="01f8a-108">Remarks</span></span>  
 <span data-ttu-id="01f8a-109">`ICLRDataEnumMemoryRegions::EnumMemoryRegions`方法将在每次尝试枚举内存区域之后调用此回调方法。</span><span class="sxs-lookup"><span data-stu-id="01f8a-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="01f8a-110">即使此方法返回 HRESULT，指示失败，则会继续在枚举。</span><span class="sxs-lookup"><span data-stu-id="01f8a-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="01f8a-111">报告的此回调的区域可能是重复或重叠区域。</span><span class="sxs-lookup"><span data-stu-id="01f8a-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01f8a-112">要求</span><span class="sxs-lookup"><span data-stu-id="01f8a-112">Requirements</span></span>  
 <span data-ttu-id="01f8a-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01f8a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f8a-114">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="01f8a-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="01f8a-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01f8a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01f8a-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f8a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f8a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01f8a-117">See Also</span></span>  
 [<span data-ttu-id="01f8a-118">ICLRDataEnumMemoryRegionsCallback 接口</span><span class="sxs-lookup"><span data-stu-id="01f8a-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
