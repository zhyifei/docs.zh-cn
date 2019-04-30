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
ms.openlocfilehash: 1fd903cb4a9ce664b7a1c958a3fef0c639d6845d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045313"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="e361b-102">CorSetENC 枚举</span><span class="sxs-lookup"><span data-stu-id="e361b-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="e361b-103">包含一些值，用于在元数据生成期间影响行为。</span><span class="sxs-lookup"><span data-stu-id="e361b-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e361b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e361b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e361b-105">成员</span><span class="sxs-lookup"><span data-stu-id="e361b-105">Members</span></span>  
  
|<span data-ttu-id="e361b-106">成员</span><span class="sxs-lookup"><span data-stu-id="e361b-106">Member</span></span>|<span data-ttu-id="e361b-107">描述</span><span class="sxs-lookup"><span data-stu-id="e361b-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="e361b-108">已过时。</span><span class="sxs-lookup"><span data-stu-id="e361b-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="e361b-109">已过时。</span><span class="sxs-lookup"><span data-stu-id="e361b-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="e361b-110">指示可以更新元数据，而不能移动标记。</span><span class="sxs-lookup"><span data-stu-id="e361b-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="e361b-111">指示可以在更新过程移动标记。</span><span class="sxs-lookup"><span data-stu-id="e361b-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="e361b-112">指示更新可以包含仅的新增功能。</span><span class="sxs-lookup"><span data-stu-id="e361b-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="e361b-113">不能移动标记。</span><span class="sxs-lookup"><span data-stu-id="e361b-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="e361b-114">指示增量编译。</span><span class="sxs-lookup"><span data-stu-id="e361b-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="e361b-115">指示应保存该仅更改了元数据。</span><span class="sxs-lookup"><span data-stu-id="e361b-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="e361b-116">包括`MDUpdateENC`，`MDUpdateFull`和`MDUpdateIncremental`。</span><span class="sxs-lookup"><span data-stu-id="e361b-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e361b-117">要求</span><span class="sxs-lookup"><span data-stu-id="e361b-117">Requirements</span></span>  
 <span data-ttu-id="e361b-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e361b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e361b-119">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e361b-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e361b-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e361b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e361b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e361b-121">See also</span></span>

- [<span data-ttu-id="e361b-122">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="e361b-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
