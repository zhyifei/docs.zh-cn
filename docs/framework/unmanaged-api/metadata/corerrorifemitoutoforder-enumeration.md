---
title: "CorErrorIfEmitOutOfOrder 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorErrorIfEmitOutOfOrder
api_location: mscoree.dll
api_type: COM
f1_keywords: CorErrorIfEmitOutOfOrder
helpviewer_keywords: CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c049d78d8ba67ec5f08fc2beb584fef4987c9e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="8169b-102">CorErrorIfEmitOutOfOrder 枚举</span><span class="sxs-lookup"><span data-stu-id="8169b-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="8169b-103">包含一些标志值，用于指示无序发出元数据时应生成错误消息的条件。</span><span class="sxs-lookup"><span data-stu-id="8169b-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8169b-104">语法</span><span class="sxs-lookup"><span data-stu-id="8169b-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8169b-105">成员</span><span class="sxs-lookup"><span data-stu-id="8169b-105">Members</span></span>  
  
|<span data-ttu-id="8169b-106">成员</span><span class="sxs-lookup"><span data-stu-id="8169b-106">Member</span></span>|<span data-ttu-id="8169b-107">描述</span><span class="sxs-lookup"><span data-stu-id="8169b-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="8169b-108">指示默认行为，不会生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="8169b-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="8169b-109">指示编译器不应生成错误消息。</span><span class="sxs-lookup"><span data-stu-id="8169b-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="8169b-110">指示当字段、 属性、 事件、 方法时，编译器应生成一条错误消息或无序发出参数。</span><span class="sxs-lookup"><span data-stu-id="8169b-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="8169b-111">指示当无序发出方法时，编译器应生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="8169b-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="8169b-112">指示当无序发出字段时，编译器应生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="8169b-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="8169b-113">指示当无序发出参数时，编译器应生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="8169b-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="8169b-114">指示当无序发出属性时，编译器应生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="8169b-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="8169b-115">指示当无序发出事件时，编译器应生成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="8169b-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8169b-116">惠?</span><span class="sxs-lookup"><span data-stu-id="8169b-116">Requirements</span></span>  
 <span data-ttu-id="8169b-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8169b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8169b-118">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8169b-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8169b-119">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8169b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8169b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8169b-120">See Also</span></span>  
 [<span data-ttu-id="8169b-121">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="8169b-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
