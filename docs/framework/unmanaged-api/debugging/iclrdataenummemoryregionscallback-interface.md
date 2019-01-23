---
title: ICLRDataEnumMemoryRegionsCallback 接口
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0e7ce243658a8c8a8404ff9079ed1395e56486f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604141"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="b9aac-102">ICLRDataEnumMemoryRegionsCallback 接口</span><span class="sxs-lookup"><span data-stu-id="b9aac-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="b9aac-103">提供回调方法，以[iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="b9aac-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b9aac-104">方法</span><span class="sxs-lookup"><span data-stu-id="b9aac-104">Methods</span></span>  
  
|<span data-ttu-id="b9aac-105">方法</span><span class="sxs-lookup"><span data-stu-id="b9aac-105">Method</span></span>|<span data-ttu-id="b9aac-106">描述</span><span class="sxs-lookup"><span data-stu-id="b9aac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b9aac-107">EnumMemoryRegion 方法</span><span class="sxs-lookup"><span data-stu-id="b9aac-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="b9aac-108">由调用`ICLRDataEnumMemoryRegions::EnumMemoryRegions`向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="b9aac-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9aac-109">要求</span><span class="sxs-lookup"><span data-stu-id="b9aac-109">Requirements</span></span>  
 <span data-ttu-id="b9aac-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9aac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9aac-111">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b9aac-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b9aac-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9aac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9aac-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9aac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9aac-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9aac-114">See also</span></span>
- [<span data-ttu-id="b9aac-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="b9aac-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
