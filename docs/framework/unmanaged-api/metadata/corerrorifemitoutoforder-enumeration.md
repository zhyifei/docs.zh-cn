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
ms.openlocfilehash: 16f6d7bf6fa1730d50cfe81526817e492a453dad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781983"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="c13bd-102">CorErrorIfEmitOutOfOrder 枚举</span><span class="sxs-lookup"><span data-stu-id="c13bd-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="c13bd-103">包含一些标志值，用于指示无序发出元数据时应生成错误消息的条件。</span><span class="sxs-lookup"><span data-stu-id="c13bd-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c13bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="c13bd-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c13bd-105">成员</span><span class="sxs-lookup"><span data-stu-id="c13bd-105">Members</span></span>  
  
|<span data-ttu-id="c13bd-106">成员</span><span class="sxs-lookup"><span data-stu-id="c13bd-106">Member</span></span>|<span data-ttu-id="c13bd-107">描述</span><span class="sxs-lookup"><span data-stu-id="c13bd-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="c13bd-108">指示默认行为，不会生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="c13bd-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="c13bd-109">指示编译器不应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="c13bd-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="c13bd-110">指示编译器应该生成一条错误消息时字段、 属性、 事件、 方法或参数，将发出顺序。</span><span class="sxs-lookup"><span data-stu-id="c13bd-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="c13bd-111">指示一种方法发出顺序时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c13bd-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="c13bd-112">指示无序发出一个字段时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c13bd-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="c13bd-113">指示参数发出顺序时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c13bd-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="c13bd-114">指示无序发出属性时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c13bd-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="c13bd-115">指示事件发出顺序时，编译器应该生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c13bd-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c13bd-116">要求</span><span class="sxs-lookup"><span data-stu-id="c13bd-116">Requirements</span></span>  
 <span data-ttu-id="c13bd-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c13bd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c13bd-118">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c13bd-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c13bd-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c13bd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c13bd-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c13bd-120">See also</span></span>

- [<span data-ttu-id="c13bd-121">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="c13bd-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
