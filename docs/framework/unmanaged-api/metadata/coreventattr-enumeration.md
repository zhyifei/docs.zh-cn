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
ms.openlocfilehash: a1a50c15071ea1e696e508c779309225c7e7bfa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046003"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="ba566-102">CorEventAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="ba566-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="ba566-103">包含一些值，用于描述事件的元数据。</span><span class="sxs-lookup"><span data-stu-id="ba566-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba566-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba566-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="ba566-105">成员</span><span class="sxs-lookup"><span data-stu-id="ba566-105">Members</span></span>  
  
|<span data-ttu-id="ba566-106">成员</span><span class="sxs-lookup"><span data-stu-id="ba566-106">Member</span></span>|<span data-ttu-id="ba566-107">描述</span><span class="sxs-lookup"><span data-stu-id="ba566-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="ba566-108">指定事件特殊，并且其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="ba566-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="ba566-109">公共语言运行时，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="ba566-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="ba566-110">指定公共语言运行时应检查事件名称的编码。</span><span class="sxs-lookup"><span data-stu-id="ba566-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba566-111">要求</span><span class="sxs-lookup"><span data-stu-id="ba566-111">Requirements</span></span>  
 <span data-ttu-id="ba566-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba566-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba566-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ba566-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ba566-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba566-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba566-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba566-115">See also</span></span>

- [<span data-ttu-id="ba566-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="ba566-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
