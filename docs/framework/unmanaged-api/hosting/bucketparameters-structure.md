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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf52f74c38b479664ad7e015180b26e0a53c235e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508296"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="3c41a-102">BucketParameters 结构</span><span class="sxs-lookup"><span data-stu-id="3c41a-102">BucketParameters Structure</span></span>
<span data-ttu-id="3c41a-103">存储与事件相关联的当前异常的事件和参数的类型名称。</span><span class="sxs-lookup"><span data-stu-id="3c41a-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c41a-104">语法</span><span class="sxs-lookup"><span data-stu-id="3c41a-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="3c41a-105">成员</span><span class="sxs-lookup"><span data-stu-id="3c41a-105">Members</span></span>  
  
|<span data-ttu-id="3c41a-106">成员</span><span class="sxs-lookup"><span data-stu-id="3c41a-106">Member</span></span>|<span data-ttu-id="3c41a-107">描述</span><span class="sxs-lookup"><span data-stu-id="3c41a-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="3c41a-108">`true`此结构的其余部分是否有效，则为否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="3c41a-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="3c41a-109">事件类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3c41a-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="3c41a-110">一个字符串数组，其中每个指定与事件相关联的当前异常的参数。</span><span class="sxs-lookup"><span data-stu-id="3c41a-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c41a-111">要求</span><span class="sxs-lookup"><span data-stu-id="3c41a-111">Requirements</span></span>  
 <span data-ttu-id="3c41a-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3c41a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c41a-113">**标头：** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="3c41a-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="3c41a-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c41a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c41a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c41a-115">See also</span></span>
- [<span data-ttu-id="3c41a-116">承载结构</span><span class="sxs-lookup"><span data-stu-id="3c41a-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
