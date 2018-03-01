---
title: "ICLRDataEnumMemoryRegionsCallback 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 091f5345461ebe5054e769ae9d051ef2e0737ffb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="6288d-102">ICLRDataEnumMemoryRegionsCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6288d-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="6288d-103">提供回调方法以[iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="6288d-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6288d-104">方法</span><span class="sxs-lookup"><span data-stu-id="6288d-104">Methods</span></span>  
  
|<span data-ttu-id="6288d-105">方法</span><span class="sxs-lookup"><span data-stu-id="6288d-105">Method</span></span>|<span data-ttu-id="6288d-106">描述</span><span class="sxs-lookup"><span data-stu-id="6288d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6288d-107">EnumMemoryRegion 方法</span><span class="sxs-lookup"><span data-stu-id="6288d-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="6288d-108">由调用`ICLRDataEnumMemoryRegions::EnumMemoryRegions`向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="6288d-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6288d-109">惠?</span><span class="sxs-lookup"><span data-stu-id="6288d-109">Requirements</span></span>  
 <span data-ttu-id="6288d-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6288d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6288d-111">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6288d-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6288d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6288d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6288d-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6288d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6288d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6288d-114">See Also</span></span>  
 [<span data-ttu-id="6288d-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="6288d-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
