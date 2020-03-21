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
ms.openlocfilehash: 4d9de489bdeb0ab506f56ff08f4afb4cf6d0ab4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178279"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="91a25-102">BucketParameters 结构</span><span class="sxs-lookup"><span data-stu-id="91a25-102">BucketParameters Structure</span></span>
<span data-ttu-id="91a25-103">存储事件的类型名称以及与事件关联的当前异常的参数。</span><span class="sxs-lookup"><span data-stu-id="91a25-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a25-104">语法</span><span class="sxs-lookup"><span data-stu-id="91a25-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="91a25-105">成员</span><span class="sxs-lookup"><span data-stu-id="91a25-105">Members</span></span>  
  
|<span data-ttu-id="91a25-106">成员</span><span class="sxs-lookup"><span data-stu-id="91a25-106">Member</span></span>|<span data-ttu-id="91a25-107">说明</span><span class="sxs-lookup"><span data-stu-id="91a25-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="91a25-108">`true`，如果此结构的其余部分有效;如果此结构的其余部分有效，则为否则， `false`.</span><span class="sxs-lookup"><span data-stu-id="91a25-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="91a25-109">事件类型的名称。</span><span class="sxs-lookup"><span data-stu-id="91a25-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="91a25-110">字符串数组，每个字符串都指定与事件关联的当前异常的参数。</span><span class="sxs-lookup"><span data-stu-id="91a25-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91a25-111">要求</span><span class="sxs-lookup"><span data-stu-id="91a25-111">Requirements</span></span>  
 <span data-ttu-id="91a25-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91a25-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a25-113">**标题：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="91a25-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="91a25-114">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a25-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a25-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91a25-115">See also</span></span>

- [<span data-ttu-id="91a25-116">承载结构</span><span class="sxs-lookup"><span data-stu-id="91a25-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
