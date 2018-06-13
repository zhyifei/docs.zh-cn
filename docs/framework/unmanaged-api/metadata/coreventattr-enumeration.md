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
ms.openlocfilehash: e4e4b9d9c7481bdc51aaf75b26b3805940875f8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442301"
---
# <a name="coreventattr-enumeration"></a><span data-ttu-id="d1d46-102">CorEventAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="d1d46-102">CorEventAttr Enumeration</span></span>
<span data-ttu-id="d1d46-103">包含一些值，用于描述事件的元数据。</span><span class="sxs-lookup"><span data-stu-id="d1d46-103">Contains values that describe the metadata of an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1d46-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1d46-104">Syntax</span></span>  
  
```  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="d1d46-105">成员</span><span class="sxs-lookup"><span data-stu-id="d1d46-105">Members</span></span>  
  
|<span data-ttu-id="d1d46-106">成员</span><span class="sxs-lookup"><span data-stu-id="d1d46-106">Member</span></span>|<span data-ttu-id="d1d46-107">描述</span><span class="sxs-lookup"><span data-stu-id="d1d46-107">Description</span></span>|  
|------------|-----------------|  
|`evSpecialName`|<span data-ttu-id="d1d46-108">指定事件为特殊，且其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="d1d46-108">Specifies that the event is special, and that its name describes how.</span></span>|  
|`evReservedMask`|<span data-ttu-id="d1d46-109">保留供内部使用公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="d1d46-109">Reserved for internal use by the common language runtime.</span></span>|  
|`evRTSpecialName`|<span data-ttu-id="d1d46-110">指定公共语言运行时，应检查的事件名称的编码。</span><span class="sxs-lookup"><span data-stu-id="d1d46-110">Specifies that the common language runtime should check the encoding of the event name.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1d46-111">要求</span><span class="sxs-lookup"><span data-stu-id="d1d46-111">Requirements</span></span>  
 <span data-ttu-id="d1d46-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1d46-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1d46-113">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d1d46-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d1d46-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1d46-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d46-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1d46-115">See Also</span></span>  
 [<span data-ttu-id="d1d46-116">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="d1d46-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
