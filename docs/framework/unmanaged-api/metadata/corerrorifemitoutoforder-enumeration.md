---
title: CorErrorIfEmitOutOfOrder 枚举
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: fec049297bfa12d86cb2a7f7950e84ae540832b1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007424"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="11d58-102">CorErrorIfEmitOutOfOrder 枚举</span><span class="sxs-lookup"><span data-stu-id="11d58-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="11d58-103">包含一些标志值，用于指示无序发出元数据时应生成错误消息的条件。</span><span class="sxs-lookup"><span data-stu-id="11d58-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d58-104">语法</span><span class="sxs-lookup"><span data-stu-id="11d58-104">Syntax</span></span>  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="11d58-105">成员</span><span class="sxs-lookup"><span data-stu-id="11d58-105">Members</span></span>  
  
|<span data-ttu-id="11d58-106">成员</span><span class="sxs-lookup"><span data-stu-id="11d58-106">Member</span></span>|<span data-ttu-id="11d58-107">描述</span><span class="sxs-lookup"><span data-stu-id="11d58-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="11d58-108">指示默认行为，不会生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="11d58-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="11d58-109">指示编译器不应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="11d58-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="11d58-110">指示当字段、属性、事件、方法或参数的顺序发出时，编译器应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="11d58-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="11d58-111">指示当方法无序发出时，编译器应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="11d58-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="11d58-112">指示当字段按顺序发出时，编译器应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="11d58-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="11d58-113">指示当参数不按顺序发出时，编译器应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="11d58-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="11d58-114">指示当某个属性未按顺序发出时，编译器应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="11d58-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="11d58-115">指示当事件顺序发出时，编译器应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="11d58-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11d58-116">要求</span><span class="sxs-lookup"><span data-stu-id="11d58-116">Requirements</span></span>  
 <span data-ttu-id="11d58-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11d58-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11d58-118">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="11d58-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="11d58-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11d58-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d58-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11d58-120">See also</span></span>

- [<span data-ttu-id="11d58-121">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="11d58-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
