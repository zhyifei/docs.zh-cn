---
title: MALLOC_TYPE 枚举
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
ms.openlocfilehash: 630fe4e79b369bfdefc19be72780f1893090895e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008451"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="66934-102">MALLOC_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="66934-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="66934-103">包含指定正在分配的内存特性的值。</span><span class="sxs-lookup"><span data-stu-id="66934-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66934-104">语法</span><span class="sxs-lookup"><span data-stu-id="66934-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="66934-105">成员</span><span class="sxs-lookup"><span data-stu-id="66934-105">Members</span></span>  
  
|<span data-ttu-id="66934-106">成员</span><span class="sxs-lookup"><span data-stu-id="66934-106">Member</span></span>|<span data-ttu-id="66934-107">描述</span><span class="sxs-lookup"><span data-stu-id="66934-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="66934-108">分配的内存可以包含可执行文件。</span><span class="sxs-lookup"><span data-stu-id="66934-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="66934-109">分配的内存是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="66934-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="66934-110">也就是说，无需任何同步即可通过多个线程访问内存。</span><span class="sxs-lookup"><span data-stu-id="66934-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="66934-111">如果未设置此标志，则必须序列化对该对象的调用。</span><span class="sxs-lookup"><span data-stu-id="66934-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66934-112">要求</span><span class="sxs-lookup"><span data-stu-id="66934-112">Requirements</span></span>  
 <span data-ttu-id="66934-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="66934-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66934-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="66934-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66934-115">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="66934-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66934-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66934-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66934-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66934-117">See also</span></span>

- [<span data-ttu-id="66934-118">承载枚举</span><span class="sxs-lookup"><span data-stu-id="66934-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
