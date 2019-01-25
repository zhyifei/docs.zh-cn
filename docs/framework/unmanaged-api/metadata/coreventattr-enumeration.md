---
title: CorEventAttr 枚举
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d34aa954126cc26519aaea963f99299e5557d2c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743045"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="43c8f-102">CorEventAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="43c8f-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="43c8f-103">包含一些值，用于描述事件的元数据。</span><span class="sxs-lookup"><span data-stu-id="43c8f-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c8f-104">语法</span><span class="sxs-lookup"><span data-stu-id="43c8f-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="43c8f-105">成员</span><span class="sxs-lookup"><span data-stu-id="43c8f-105">Members</span></span>  
  
|<span data-ttu-id="43c8f-106">成员</span><span class="sxs-lookup"><span data-stu-id="43c8f-106">Member</span></span>|<span data-ttu-id="43c8f-107">描述</span><span class="sxs-lookup"><span data-stu-id="43c8f-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="43c8f-108">指定事件特殊，并且其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="43c8f-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="43c8f-109">公共语言运行时，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="43c8f-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="43c8f-110">指定公共语言运行时应检查事件名称的编码。</span><span class="sxs-lookup"><span data-stu-id="43c8f-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43c8f-111">要求</span><span class="sxs-lookup"><span data-stu-id="43c8f-111">Requirements</span></span>  
 <span data-ttu-id="43c8f-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="43c8f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c8f-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="43c8f-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="43c8f-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c8f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c8f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="43c8f-115">See also</span></span>
- [<span data-ttu-id="43c8f-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="43c8f-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
