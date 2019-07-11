---
title: CorManifestResourceFlags 枚举
ms.date: 03/30/2017
api_name:
- CorManifestResourceFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorManifestResourceFlags
helpviewer_keywords:
- CorManifestResourceFlags enumeration [.NET Framework metadata]
ms.assetid: 1b0306b7-622b-4b57-8edc-3c713bb147ae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08f997e133fa6cc8769efe18e7ca06c0153f15a4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781800"
---
# <a name="cormanifestresourceflags-enumeration"></a><span data-ttu-id="81236-102">CorManifestResourceFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="81236-102">CorManifestResourceFlags Enumeration</span></span>
<span data-ttu-id="81236-103">指示程序集清单中编码的资源的可见性。</span><span class="sxs-lookup"><span data-stu-id="81236-103">Indicates the visibility of resources encoded in an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81236-104">语法</span><span class="sxs-lookup"><span data-stu-id="81236-104">Syntax</span></span>  
  
```cpp  
typedef enum CorManifestResourceFlags {  
  
    mrVisibilityMask        =   0x0007,  
    mrPublic                =   0x0001,  
    mrPrivate               =   0x0002  
  
} CorManifestResourceFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="81236-105">成员</span><span class="sxs-lookup"><span data-stu-id="81236-105">Members</span></span>  
  
|<span data-ttu-id="81236-106">成员</span><span class="sxs-lookup"><span data-stu-id="81236-106">Member</span></span>|<span data-ttu-id="81236-107">描述</span><span class="sxs-lookup"><span data-stu-id="81236-107">Description</span></span>|  
|------------|-----------------|  
|`mrVisibilityMask`|<span data-ttu-id="81236-108">保留。</span><span class="sxs-lookup"><span data-stu-id="81236-108">Reserved.</span></span>|  
|`mrPublic`|<span data-ttu-id="81236-109">资源是公共的。</span><span class="sxs-lookup"><span data-stu-id="81236-109">The resources are public.</span></span>|  
|`mrPrivate`|<span data-ttu-id="81236-110">资源是私有的。</span><span class="sxs-lookup"><span data-stu-id="81236-110">The resources are private.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81236-111">要求</span><span class="sxs-lookup"><span data-stu-id="81236-111">Requirements</span></span>  
 <span data-ttu-id="81236-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81236-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81236-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="81236-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="81236-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81236-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81236-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="81236-115">See also</span></span>

- [<span data-ttu-id="81236-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="81236-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
