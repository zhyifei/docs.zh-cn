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
ms.openlocfilehash: e22b390271a7813dd1d34aecf5f8a62d7eb81005
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007427"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="5f0e8-102">CorEventAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="5f0e8-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="5f0e8-103">包含一些值，用于描述事件的元数据。</span><span class="sxs-lookup"><span data-stu-id="5f0e8-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f0e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f0e8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="5f0e8-105">成员</span><span class="sxs-lookup"><span data-stu-id="5f0e8-105">Members</span></span>  
  
|<span data-ttu-id="5f0e8-106">成员</span><span class="sxs-lookup"><span data-stu-id="5f0e8-106">Member</span></span>|<span data-ttu-id="5f0e8-107">描述</span><span class="sxs-lookup"><span data-stu-id="5f0e8-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="5f0e8-108">指定事件是特殊的，其名称描述了操作方法。</span><span class="sxs-lookup"><span data-stu-id="5f0e8-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="5f0e8-109">保留供公共语言运行时内部使用。</span><span class="sxs-lookup"><span data-stu-id="5f0e8-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="5f0e8-110">指定公共语言运行时应检查事件名称的编码。</span><span class="sxs-lookup"><span data-stu-id="5f0e8-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f0e8-111">要求</span><span class="sxs-lookup"><span data-stu-id="5f0e8-111">Requirements</span></span>  
 <span data-ttu-id="5f0e8-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f0e8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f0e8-113">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="5f0e8-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5f0e8-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f0e8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f0e8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f0e8-115">See also</span></span>

- [<span data-ttu-id="5f0e8-116">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="5f0e8-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
