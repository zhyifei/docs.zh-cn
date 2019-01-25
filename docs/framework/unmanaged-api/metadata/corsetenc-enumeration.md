---
title: CorSetENC 枚举
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf1be8d5c709f3d6e5991e4d33dde2e923291a95
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569409"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="c00a5-102">CorSetENC 枚举</span><span class="sxs-lookup"><span data-stu-id="c00a5-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="c00a5-103">包含一些值，用于在元数据生成期间影响行为。</span><span class="sxs-lookup"><span data-stu-id="c00a5-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c00a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="c00a5-104">Syntax</span></span>  
  
```  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="c00a5-105">成员</span><span class="sxs-lookup"><span data-stu-id="c00a5-105">Members</span></span>  
  
|<span data-ttu-id="c00a5-106">成员</span><span class="sxs-lookup"><span data-stu-id="c00a5-106">Member</span></span>|<span data-ttu-id="c00a5-107">描述</span><span class="sxs-lookup"><span data-stu-id="c00a5-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="c00a5-108">已过时。</span><span class="sxs-lookup"><span data-stu-id="c00a5-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="c00a5-109">已过时。</span><span class="sxs-lookup"><span data-stu-id="c00a5-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="c00a5-110">指示可以更新元数据，而不能移动标记。</span><span class="sxs-lookup"><span data-stu-id="c00a5-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="c00a5-111">指示可以在更新过程移动标记。</span><span class="sxs-lookup"><span data-stu-id="c00a5-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="c00a5-112">指示更新可以包含仅的新增功能。</span><span class="sxs-lookup"><span data-stu-id="c00a5-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="c00a5-113">不能移动标记。</span><span class="sxs-lookup"><span data-stu-id="c00a5-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="c00a5-114">指示增量编译。</span><span class="sxs-lookup"><span data-stu-id="c00a5-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="c00a5-115">指示应保存该仅更改了元数据。</span><span class="sxs-lookup"><span data-stu-id="c00a5-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="c00a5-116">包括`MDUpdateENC`，`MDUpdateFull`和`MDUpdateIncremental`。</span><span class="sxs-lookup"><span data-stu-id="c00a5-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c00a5-117">要求</span><span class="sxs-lookup"><span data-stu-id="c00a5-117">Requirements</span></span>  
 <span data-ttu-id="c00a5-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c00a5-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c00a5-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c00a5-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c00a5-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c00a5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00a5-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c00a5-121">See also</span></span>
- [<span data-ttu-id="c00a5-122">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="c00a5-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
