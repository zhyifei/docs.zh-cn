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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5e970a1677b1e43821cce9985e32ebd0726686
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442535"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="ce367-102">MALLOC_TYPE 枚举</span><span class="sxs-lookup"><span data-stu-id="ce367-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="ce367-103">包含指定的内存的分配时的特征的值。</span><span class="sxs-lookup"><span data-stu-id="ce367-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce367-104">语法</span><span class="sxs-lookup"><span data-stu-id="ce367-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="ce367-105">成员</span><span class="sxs-lookup"><span data-stu-id="ce367-105">Members</span></span>  
  
|<span data-ttu-id="ce367-106">成员</span><span class="sxs-lookup"><span data-stu-id="ce367-106">Member</span></span>|<span data-ttu-id="ce367-107">描述</span><span class="sxs-lookup"><span data-stu-id="ce367-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="ce367-108">分配的内存可以包含可执行文件。</span><span class="sxs-lookup"><span data-stu-id="ce367-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="ce367-109">分配的内存是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="ce367-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="ce367-110">也就是说，可以通过而不进行任何同步多个线程访问内存。</span><span class="sxs-lookup"><span data-stu-id="ce367-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="ce367-111">如果未设置此标志，则必须序列化对象上的调用。</span><span class="sxs-lookup"><span data-stu-id="ce367-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce367-112">要求</span><span class="sxs-lookup"><span data-stu-id="ce367-112">Requirements</span></span>  
 <span data-ttu-id="ce367-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce367-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce367-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce367-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce367-115">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce367-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce367-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce367-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce367-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce367-117">See Also</span></span>  
 [<span data-ttu-id="ce367-118">承载枚举</span><span class="sxs-lookup"><span data-stu-id="ce367-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
