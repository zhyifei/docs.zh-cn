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
ms.openlocfilehash: 2796be32154275387da891683cc5053095f534af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772322"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="44e8d-102">CorSetENC 枚举</span><span class="sxs-lookup"><span data-stu-id="44e8d-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="44e8d-103">包含一些值，用于在元数据生成期间影响行为。</span><span class="sxs-lookup"><span data-stu-id="44e8d-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="44e8d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="44e8d-105">成员</span><span class="sxs-lookup"><span data-stu-id="44e8d-105">Members</span></span>  
  
|<span data-ttu-id="44e8d-106">成员</span><span class="sxs-lookup"><span data-stu-id="44e8d-106">Member</span></span>|<span data-ttu-id="44e8d-107">描述</span><span class="sxs-lookup"><span data-stu-id="44e8d-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="44e8d-108">已过时。</span><span class="sxs-lookup"><span data-stu-id="44e8d-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="44e8d-109">已过时。</span><span class="sxs-lookup"><span data-stu-id="44e8d-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="44e8d-110">指示可以更新元数据，而不能移动标记。</span><span class="sxs-lookup"><span data-stu-id="44e8d-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="44e8d-111">指示可以在更新过程移动标记。</span><span class="sxs-lookup"><span data-stu-id="44e8d-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="44e8d-112">指示更新可以包含仅的新增功能。</span><span class="sxs-lookup"><span data-stu-id="44e8d-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="44e8d-113">不能移动标记。</span><span class="sxs-lookup"><span data-stu-id="44e8d-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="44e8d-114">指示增量编译。</span><span class="sxs-lookup"><span data-stu-id="44e8d-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="44e8d-115">指示应保存该仅更改了元数据。</span><span class="sxs-lookup"><span data-stu-id="44e8d-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="44e8d-116">包括`MDUpdateENC`，`MDUpdateFull`和`MDUpdateIncremental`。</span><span class="sxs-lookup"><span data-stu-id="44e8d-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44e8d-117">要求</span><span class="sxs-lookup"><span data-stu-id="44e8d-117">Requirements</span></span>  
 <span data-ttu-id="44e8d-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44e8d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e8d-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="44e8d-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="44e8d-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e8d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e8d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="44e8d-121">See also</span></span>

- [<span data-ttu-id="44e8d-122">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="44e8d-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
