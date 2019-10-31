---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 方法
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
ms.openlocfilehash: 2ebe7ef37fb072e3688cc4dcfa5ed89832e886e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122937"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="50b2d-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 方法</span><span class="sxs-lookup"><span data-stu-id="50b2d-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="50b2d-103">由[ICLRDataEnumMemoryRegions：： EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)调用，以向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="50b2d-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50b2d-104">语法</span><span class="sxs-lookup"><span data-stu-id="50b2d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50b2d-105">参数</span><span class="sxs-lookup"><span data-stu-id="50b2d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="50b2d-106">中要枚举的内存区域的起始地址。</span><span class="sxs-lookup"><span data-stu-id="50b2d-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="50b2d-107">中内存区域的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="50b2d-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50b2d-108">备注</span><span class="sxs-lookup"><span data-stu-id="50b2d-108">Remarks</span></span>  
 <span data-ttu-id="50b2d-109">`ICLRDataEnumMemoryRegions::EnumMemoryRegions` 方法将在每次尝试枚举内存区域后调用此回调方法。</span><span class="sxs-lookup"><span data-stu-id="50b2d-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="50b2d-110">即使此方法返回一个指示失败的 HRESULT，枚举也将继续。</span><span class="sxs-lookup"><span data-stu-id="50b2d-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="50b2d-111">此回调报告的区域可能是重复区域或重叠区域。</span><span class="sxs-lookup"><span data-stu-id="50b2d-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50b2d-112">要求</span><span class="sxs-lookup"><span data-stu-id="50b2d-112">Requirements</span></span>  
 <span data-ttu-id="50b2d-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50b2d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50b2d-114">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="50b2d-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="50b2d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50b2d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50b2d-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50b2d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b2d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="50b2d-117">See also</span></span>

- [<span data-ttu-id="50b2d-118">ICLRDataEnumMemoryRegionsCallback 接口</span><span class="sxs-lookup"><span data-stu-id="50b2d-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
