---
title: "CorManifestResourceFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorManifestResourceFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorManifestResourceFlags
helpviewer_keywords: CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a1ad2aa505ba77f136a28b2cfa9f1fa357c37ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="70c8b-102">CorManifestResourceFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="70c8b-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="70c8b-103">指示程序集清单中编码的资源的可见性。</span><span class="sxs-lookup"><span data-stu-id="70c8b-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70c8b-104">语法</span><span class="sxs-lookup"><span data-stu-id="70c8b-104">Syntax</span></span>  
  
```  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="70c8b-105">成员</span><span class="sxs-lookup"><span data-stu-id="70c8b-105">Members</span></span>  
  
|<span data-ttu-id="70c8b-106">成员</span><span class="sxs-lookup"><span data-stu-id="70c8b-106">Member</span></span>|<span data-ttu-id="70c8b-107">描述</span><span class="sxs-lookup"><span data-stu-id="70c8b-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="70c8b-108">保留。</span><span class="sxs-lookup"><span data-stu-id="70c8b-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="70c8b-109">资源是公共的。</span><span class="sxs-lookup"><span data-stu-id="70c8b-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="70c8b-110">资源是私有类型。</span><span class="sxs-lookup"><span data-stu-id="70c8b-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70c8b-111">惠?</span><span class="sxs-lookup"><span data-stu-id="70c8b-111">Requirements</span></span>  
 <span data-ttu-id="70c8b-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70c8b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70c8b-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="70c8b-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="70c8b-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70c8b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70c8b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="70c8b-115">See Also</span></span>  
 [<span data-ttu-id="70c8b-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="70c8b-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
