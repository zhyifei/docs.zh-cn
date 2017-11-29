---
title: "COR_TYPE_LAYOUT 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPE_LAYOUT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPE_LAYOUT
helpviewer_keywords: COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc23e33abf47d19792c25d36a62bf95a098ee7a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="c6079-102">COR_TYPE_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="c6079-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="c6079-103">提供有关内存中某个对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="c6079-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6079-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6079-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="c6079-105">成员</span><span class="sxs-lookup"><span data-stu-id="c6079-105">Members</span></span>  
  
|<span data-ttu-id="c6079-106">成员</span><span class="sxs-lookup"><span data-stu-id="c6079-106">Member</span></span>|<span data-ttu-id="c6079-107">描述</span><span class="sxs-lookup"><span data-stu-id="c6079-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="c6079-108">为此类型的父类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="c6079-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="c6079-109">这将是 NULL 类型 id (token1 = 0，token2 = 0) 如果类型 id 对应于<xref:System.Object?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="c6079-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="c6079-110">此类型的对象的基大小。</span><span class="sxs-lookup"><span data-stu-id="c6079-110">The base size of an object of this type.</span></span> <span data-ttu-id="c6079-111">这是非变量大小对象的总大小。</span><span class="sxs-lookup"><span data-stu-id="c6079-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="c6079-112">此类型的对象中包含的字段数。</span><span class="sxs-lookup"><span data-stu-id="c6079-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="c6079-113">如果此类型进行装箱时，对象的字段的偏移量开始。</span><span class="sxs-lookup"><span data-stu-id="c6079-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="c6079-114">此字段为仅对值类型，如基元和结构有效。</span><span class="sxs-lookup"><span data-stu-id="c6079-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="c6079-115">此类型属于 CorElementType。</span><span class="sxs-lookup"><span data-stu-id="c6079-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6079-116">备注</span><span class="sxs-lookup"><span data-stu-id="c6079-116">Remarks</span></span>  
 <span data-ttu-id="c6079-117">如果`numFields`大于零，可以调用[icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)方法来获取有关此类型中的字段的信息。</span><span class="sxs-lookup"><span data-stu-id="c6079-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="c6079-118">如果`type`是`ELEMENT_TYPE_STRING`， `ELEMENT_TYPE_ARRAY`，或`ELEMENT_TYPE_SZARRAY`，此类型的对象的大小是变量，并且可以通过[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)结构[icordebugprocess5:: Getarraylayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c6079-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6079-119">要求</span><span class="sxs-lookup"><span data-stu-id="c6079-119">Requirements</span></span>  
 <span data-ttu-id="c6079-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6079-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6079-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6079-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6079-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6079-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6079-123">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6079-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6079-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6079-124">See Also</span></span>  
 [<span data-ttu-id="c6079-125">调试结构</span><span class="sxs-lookup"><span data-stu-id="c6079-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="c6079-126">调试</span><span class="sxs-lookup"><span data-stu-id="c6079-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
