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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 084f0bbab130cd4e7334184fe9baa322c0487942
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616766"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="453a8-102">CorErrorIfEmitOutOfOrder 枚举</span><span class="sxs-lookup"><span data-stu-id="453a8-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="453a8-103">包含一些标志值，用于指示无序发出元数据时应生成错误消息的条件。</span><span class="sxs-lookup"><span data-stu-id="453a8-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="453a8-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="453a8-105">成员</span><span class="sxs-lookup"><span data-stu-id="453a8-105">Members</span></span>  
  
|<span data-ttu-id="453a8-106">成员</span><span class="sxs-lookup"><span data-stu-id="453a8-106">Member</span></span>|<span data-ttu-id="453a8-107">描述</span><span class="sxs-lookup"><span data-stu-id="453a8-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="453a8-108">指示默认行为，不会生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="453a8-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="453a8-109">指示编译器不应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="453a8-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="453a8-110">指示编译器应该生成一条错误消息时字段、 属性、 事件、 方法或参数，将发出顺序。</span><span class="sxs-lookup"><span data-stu-id="453a8-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="453a8-111">指示一种方法发出顺序时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="453a8-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="453a8-112">指示无序发出一个字段时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="453a8-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="453a8-113">指示参数发出顺序时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="453a8-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="453a8-114">指示无序发出属性时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="453a8-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="453a8-115">指示事件发出顺序时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="453a8-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="453a8-116">要求</span><span class="sxs-lookup"><span data-stu-id="453a8-116">Requirements</span></span>  
 <span data-ttu-id="453a8-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="453a8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453a8-118">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="453a8-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="453a8-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453a8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453a8-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="453a8-120">See also</span></span>
- [<span data-ttu-id="453a8-121">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="453a8-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
