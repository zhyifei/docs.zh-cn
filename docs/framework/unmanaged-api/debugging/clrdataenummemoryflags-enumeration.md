---
title: CLRDataEnumMemoryFlags 枚举
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cd385c1176bea41b41a981e743c6104227d8acd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708189"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="6a4bf-102">CLRDataEnumMemoryFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="6a4bf-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="6a4bf-103">指示调用的内存区域[iclrdataenummemoryregions:: Enummemoryregions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md)方法应包括。</span><span class="sxs-lookup"><span data-stu-id="6a4bf-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a4bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a4bf-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6a4bf-105">成员</span><span class="sxs-lookup"><span data-stu-id="6a4bf-105">Members</span></span>  
  
|<span data-ttu-id="6a4bf-106">成员</span><span class="sxs-lookup"><span data-stu-id="6a4bf-106">Member</span></span>|<span data-ttu-id="6a4bf-107">描述</span><span class="sxs-lookup"><span data-stu-id="6a4bf-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="6a4bf-108">小型转储，也就是说，稀疏内存转储。</span><span class="sxs-lookup"><span data-stu-id="6a4bf-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="6a4bf-109">完整的堆转储。</span><span class="sxs-lookup"><span data-stu-id="6a4bf-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a4bf-110">要求</span><span class="sxs-lookup"><span data-stu-id="6a4bf-110">Requirements</span></span>  
 <span data-ttu-id="6a4bf-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a4bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a4bf-112">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="6a4bf-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6a4bf-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a4bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a4bf-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a4bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a4bf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a4bf-115">See also</span></span>
- [<span data-ttu-id="6a4bf-116">调试枚举</span><span class="sxs-lookup"><span data-stu-id="6a4bf-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
