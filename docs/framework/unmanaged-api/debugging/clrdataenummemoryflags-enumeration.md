---
title: "CLRDataEnumMemoryFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRDataEnumMemoryFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLRDataEnumMemoryFlags
helpviewer_keywords: CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c88fe4e6bcbe4f2ec3f13c08450f7dea44ccdbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="7c5c8-102">CLRDataEnumMemoryFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="7c5c8-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="7c5c8-103">指示的内存区域对的调用[iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)应包括方法。</span><span class="sxs-lookup"><span data-stu-id="7c5c8-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c5c8-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c5c8-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7c5c8-105">成员</span><span class="sxs-lookup"><span data-stu-id="7c5c8-105">Members</span></span>  
  
|<span data-ttu-id="7c5c8-106">成员</span><span class="sxs-lookup"><span data-stu-id="7c5c8-106">Member</span></span>|<span data-ttu-id="7c5c8-107">描述</span><span class="sxs-lookup"><span data-stu-id="7c5c8-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="7c5c8-108">小型转储，也就是说，稀疏内存转储。</span><span class="sxs-lookup"><span data-stu-id="7c5c8-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="7c5c8-109">完整的堆转储。</span><span class="sxs-lookup"><span data-stu-id="7c5c8-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c5c8-110">要求</span><span class="sxs-lookup"><span data-stu-id="7c5c8-110">Requirements</span></span>  
 <span data-ttu-id="7c5c8-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5c8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c5c8-112">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7c5c8-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7c5c8-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c5c8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c5c8-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c5c8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c5c8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c5c8-115">See Also</span></span>  
 [<span data-ttu-id="7c5c8-116">调试枚举</span><span class="sxs-lookup"><span data-stu-id="7c5c8-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
