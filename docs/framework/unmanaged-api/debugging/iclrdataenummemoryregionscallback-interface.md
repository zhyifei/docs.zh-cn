---
title: "ICLRDataEnumMemoryRegionsCallback 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords: ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40e51bfc176d8be6b008bc4274c0933253d7be3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdataenummemoryregionscallback-interface"></a><span data-ttu-id="7ff37-102">ICLRDataEnumMemoryRegionsCallback 接口</span><span class="sxs-lookup"><span data-stu-id="7ff37-102">ICLRDataEnumMemoryRegionsCallback Interface</span></span>
<span data-ttu-id="7ff37-103">提供回调方法以[iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="7ff37-103">Provides a callback method for [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ff37-104">方法</span><span class="sxs-lookup"><span data-stu-id="7ff37-104">Methods</span></span>  
  
|<span data-ttu-id="7ff37-105">方法</span><span class="sxs-lookup"><span data-stu-id="7ff37-105">Method</span></span>|<span data-ttu-id="7ff37-106">描述</span><span class="sxs-lookup"><span data-stu-id="7ff37-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ff37-107">EnumMemoryRegion 方法</span><span class="sxs-lookup"><span data-stu-id="7ff37-107">EnumMemoryRegion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-enummemoryregion-method.md)|<span data-ttu-id="7ff37-108">由调用`ICLRDataEnumMemoryRegions::EnumMemoryRegions`向调试器报告尝试枚举指定的内存区域的结果。</span><span class="sxs-lookup"><span data-stu-id="7ff37-108">Called by `ICLRDataEnumMemoryRegions::EnumMemoryRegions` to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ff37-109">要求</span><span class="sxs-lookup"><span data-stu-id="7ff37-109">Requirements</span></span>  
 <span data-ttu-id="7ff37-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ff37-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ff37-111">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7ff37-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7ff37-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ff37-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ff37-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ff37-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ff37-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ff37-114">See Also</span></span>  
 [<span data-ttu-id="7ff37-115">调试接口</span><span class="sxs-lookup"><span data-stu-id="7ff37-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
