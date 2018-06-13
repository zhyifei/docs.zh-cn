---
title: CorArgType 枚举
ms.date: 03/30/2017
api_name:
- CorArgType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorArgType
helpviewer_keywords:
- CorArgType enumeration [.NET Framework metadata]
ms.assetid: 3c1cb268-57a0-4664-91c7-f6908ff29e32
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5803f958c9340c068d6ce6e7fc0b1d6846d67876
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441570"
---
# <a name="corargtype-enumeration"></a><span data-ttu-id="c527f-102">CorArgType 枚举</span><span class="sxs-lookup"><span data-stu-id="c527f-102">CorArgType Enumeration</span></span>
<span data-ttu-id="c527f-103">包含一些值，用于描述运行时句柄的本机类型。</span><span class="sxs-lookup"><span data-stu-id="c527f-103">Contains values that describe the native type of a runtime handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c527f-104">语法</span><span class="sxs-lookup"><span data-stu-id="c527f-104">Syntax</span></span>  
  
```  
typedef enum CorArgType {  
  
    IMAGE_CEE_CS_END        = 0x0,  
    IMAGE_CEE_CS_VOID       = 0x1,  
    IMAGE_CEE_CS_I4         = 0x2,  
    IMAGE_CEE_CS_I8         = 0x3,  
    IMAGE_CEE_CS_R4         = 0x4,  
    IMAGE_CEE_CS_R8         = 0x5,  
    IMAGE_CEE_CS_PTR        = 0x6,  
    IMAGE_CEE_CS_OBJECT     = 0x7,  
    IMAGE_CEE_CS_STRUCT4    = 0x8,  
    IMAGE_CEE_CS_STRUCT32   = 0x9,  
    IMAGE_CEE_CS_BYVALUE    = 0xA  
  
} CorArgType;  
```  
  
## <a name="requirements"></a><span data-ttu-id="c527f-105">要求</span><span class="sxs-lookup"><span data-stu-id="c527f-105">Requirements</span></span>  
 <span data-ttu-id="c527f-106">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c527f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c527f-107">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c527f-107">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c527f-108">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c527f-108">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c527f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c527f-109">See Also</span></span>  
 [<span data-ttu-id="c527f-110">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="c527f-110">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
