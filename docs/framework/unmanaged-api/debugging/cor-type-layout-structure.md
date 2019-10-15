---
title: COR_TYPE_LAYOUT 结构
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bd274b1eb14532629580e777288317186544912
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274168"
---
# <a name="cor_type_layout-structure"></a><span data-ttu-id="a7bd7-102">COR_TYPE_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="a7bd7-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="a7bd7-103">提供有关内存中某个对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7bd7-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7bd7-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="a7bd7-105">成员</span><span class="sxs-lookup"><span data-stu-id="a7bd7-105">Members</span></span>  
  
|<span data-ttu-id="a7bd7-106">成员</span><span class="sxs-lookup"><span data-stu-id="a7bd7-106">Member</span></span>|<span data-ttu-id="a7bd7-107">描述</span><span class="sxs-lookup"><span data-stu-id="a7bd7-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="a7bd7-108">此类型的父类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="a7bd7-109">如果类型 id 对应<xref:System.Object?displayProperty=nameWithType>于，则此值将为 NULL 类型 id （token1 = 0，token2 = 0）。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="a7bd7-110">此类型的对象的基大小。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-110">The base size of an object of this type.</span></span> <span data-ttu-id="a7bd7-111">这是非变量大小对象的总大小。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="a7bd7-112">此类型的对象中包含的字段数。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="a7bd7-113">如果此类型为装箱，则为对象字段的开始偏移量。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="a7bd7-114">此字段仅对基元和结构等值类型有效。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="a7bd7-115">此类型所属的 CorElementType。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7bd7-116">备注</span><span class="sxs-lookup"><span data-stu-id="a7bd7-116">Remarks</span></span>  
 <span data-ttu-id="a7bd7-117">如果`numFields`大于零，则可以调用[ICorDebugProcess5：： GetTypeFields](icordebugprocess5-gettypefields-method.md)方法来获取有关此类型中的字段的信息。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="a7bd7-118">如果`type`为 `ELEMENT_TYPE_STRING`、`ELEMENT_TYPE_ARRAY` 或`ELEMENT_TYPE_SZARRAY`，则此类型的对象的大小是可变的，你可以将 [COR_TYPEID](cor-typeid-structure.md) 结构传递到[ICorDebugProcess5：： GetArrayLayout](icordebugprocess5-getarraylayout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7bd7-119">要求</span><span class="sxs-lookup"><span data-stu-id="a7bd7-119">Requirements</span></span>  
 <span data-ttu-id="a7bd7-120">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7bd7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7bd7-121">**标头：** Cordebug.idl，Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="a7bd7-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7bd7-122">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7bd7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7bd7-123">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7bd7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bd7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7bd7-124">See also</span></span>

- [<span data-ttu-id="a7bd7-125">调试结构</span><span class="sxs-lookup"><span data-stu-id="a7bd7-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="a7bd7-126">调试</span><span class="sxs-lookup"><span data-stu-id="a7bd7-126">Debugging</span></span>](index.md)
