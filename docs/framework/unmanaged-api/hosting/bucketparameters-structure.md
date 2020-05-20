---
title: BucketParameters 结构
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
ms.openlocfilehash: 7037065be138c369b847e7f86de7b46fc5ae601a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616874"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="68e7d-102">BucketParameters 结构</span><span class="sxs-lookup"><span data-stu-id="68e7d-102">BucketParameters Structure</span></span>
<span data-ttu-id="68e7d-103">存储事件的类型名称和与事件关联的当前异常的参数。</span><span class="sxs-lookup"><span data-stu-id="68e7d-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68e7d-104">语法</span><span class="sxs-lookup"><span data-stu-id="68e7d-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="68e7d-105">成员</span><span class="sxs-lookup"><span data-stu-id="68e7d-105">Members</span></span>  
  
|<span data-ttu-id="68e7d-106">成员</span><span class="sxs-lookup"><span data-stu-id="68e7d-106">Member</span></span>|<span data-ttu-id="68e7d-107">描述</span><span class="sxs-lookup"><span data-stu-id="68e7d-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="68e7d-108">`true`如果此结构的其余部分有效，则为; 否则为。否则为 `false` 。</span><span class="sxs-lookup"><span data-stu-id="68e7d-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="68e7d-109">事件类型的名称。</span><span class="sxs-lookup"><span data-stu-id="68e7d-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="68e7d-110">一个字符串数组，其中每个字符串都为与事件关联的当前异常指定一个参数。</span><span class="sxs-lookup"><span data-stu-id="68e7d-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68e7d-111">要求</span><span class="sxs-lookup"><span data-stu-id="68e7d-111">Requirements</span></span>  
 <span data-ttu-id="68e7d-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="68e7d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68e7d-113">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="68e7d-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="68e7d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68e7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68e7d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68e7d-115">See also</span></span>

- [<span data-ttu-id="68e7d-116">承载结构</span><span class="sxs-lookup"><span data-stu-id="68e7d-116">Hosting Structures</span></span>](hosting-structures.md)
