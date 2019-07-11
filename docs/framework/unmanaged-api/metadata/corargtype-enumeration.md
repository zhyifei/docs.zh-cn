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
ms.openlocfilehash: 4ae7b61d056c08691e19e639353b6ab6fb8443c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780943"
---
# <a name="corargtype-enumeration"></a><span data-ttu-id="6bb52-102">CorArgType 枚举</span><span class="sxs-lookup"><span data-stu-id="6bb52-102">CorArgType Enumeration</span></span>
<span data-ttu-id="6bb52-103">包含一些值，用于描述运行时句柄的本机类型。</span><span class="sxs-lookup"><span data-stu-id="6bb52-103">Contains values that describe the native type of a runtime handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bb52-104">语法</span><span class="sxs-lookup"><span data-stu-id="6bb52-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="requirements"></a><span data-ttu-id="6bb52-105">要求</span><span class="sxs-lookup"><span data-stu-id="6bb52-105">Requirements</span></span>  
 <span data-ttu-id="6bb52-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6bb52-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bb52-107">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6bb52-107">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6bb52-108">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bb52-108">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb52-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bb52-109">See also</span></span>

- [<span data-ttu-id="6bb52-110">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="6bb52-110">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
