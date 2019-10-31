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
ms.openlocfilehash: 769e63ac6e23ae0264b79a1cd8d6e3cc1ac5a744
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132411"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="82217-102">CLRDataEnumMemoryFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="82217-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="82217-103">指示对[ICLRDataEnumMemoryRegions：： EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md)方法的调用应包括哪些内存区域。</span><span class="sxs-lookup"><span data-stu-id="82217-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82217-104">语法</span><span class="sxs-lookup"><span data-stu-id="82217-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="82217-105">Members</span><span class="sxs-lookup"><span data-stu-id="82217-105">Members</span></span>  
  
|<span data-ttu-id="82217-106">成员</span><span class="sxs-lookup"><span data-stu-id="82217-106">Member</span></span>|<span data-ttu-id="82217-107">描述</span><span class="sxs-lookup"><span data-stu-id="82217-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="82217-108">小型转储，即稀疏内存转储。</span><span class="sxs-lookup"><span data-stu-id="82217-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="82217-109">完整堆转储。</span><span class="sxs-lookup"><span data-stu-id="82217-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82217-110">要求</span><span class="sxs-lookup"><span data-stu-id="82217-110">Requirements</span></span>  
 <span data-ttu-id="82217-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82217-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82217-112">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="82217-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="82217-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82217-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82217-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82217-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82217-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="82217-115">See also</span></span>

- [<span data-ttu-id="82217-116">调试枚举</span><span class="sxs-lookup"><span data-stu-id="82217-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
