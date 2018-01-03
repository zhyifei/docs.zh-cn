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
ms.workload: dotnet
ms.openlocfilehash: 250d78dd9983b75fa7e1b3cfd99215160fbc2b1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="2b701-102">COR_TYPE_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="2b701-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="2b701-103">提供有关内存中某个对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="2b701-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b701-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b701-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="2b701-105">成员</span><span class="sxs-lookup"><span data-stu-id="2b701-105">Members</span></span>  
  
|<span data-ttu-id="2b701-106">成员</span><span class="sxs-lookup"><span data-stu-id="2b701-106">Member</span></span>|<span data-ttu-id="2b701-107">描述</span><span class="sxs-lookup"><span data-stu-id="2b701-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="2b701-108">为此类型的父类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="2b701-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="2b701-109">这将是 NULL 类型 id (token1 = 0，token2 = 0) 如果类型 id 对应于<xref:System.Object?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2b701-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="2b701-110">此类型的对象的基大小。</span><span class="sxs-lookup"><span data-stu-id="2b701-110">The base size of an object of this type.</span></span> <span data-ttu-id="2b701-111">这是非变量大小对象的总大小。</span><span class="sxs-lookup"><span data-stu-id="2b701-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="2b701-112">此类型的对象中包含的字段数。</span><span class="sxs-lookup"><span data-stu-id="2b701-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="2b701-113">如果此类型进行装箱时，对象的字段的偏移量开始。</span><span class="sxs-lookup"><span data-stu-id="2b701-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="2b701-114">此字段为仅对值类型，如基元和结构有效。</span><span class="sxs-lookup"><span data-stu-id="2b701-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="2b701-115">此类型属于 CorElementType。</span><span class="sxs-lookup"><span data-stu-id="2b701-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b701-116">备注</span><span class="sxs-lookup"><span data-stu-id="2b701-116">Remarks</span></span>  
 <span data-ttu-id="2b701-117">如果`numFields`大于零，可以调用[icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)方法来获取有关此类型中的字段的信息。</span><span class="sxs-lookup"><span data-stu-id="2b701-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="2b701-118">如果`type`是`ELEMENT_TYPE_STRING`， `ELEMENT_TYPE_ARRAY`，或`ELEMENT_TYPE_SZARRAY`，此类型的对象的大小是变量，并且可以通过[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)结构[icordebugprocess5:: Getarraylayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2b701-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b701-119">惠?</span><span class="sxs-lookup"><span data-stu-id="2b701-119">Requirements</span></span>  
 <span data-ttu-id="2b701-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b701-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b701-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b701-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b701-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b701-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b701-123">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b701-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b701-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b701-124">See Also</span></span>  
 [<span data-ttu-id="2b701-125">调试结构</span><span class="sxs-lookup"><span data-stu-id="2b701-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="2b701-126">调试</span><span class="sxs-lookup"><span data-stu-id="2b701-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
