---
title: COR_FIELD 结构
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f857f773f02da25fe6650000be777b8290f5af91
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274063"
---
# <a name="cor_field-structure"></a><span data-ttu-id="92021-102">COR_FIELD 结构</span><span class="sxs-lookup"><span data-stu-id="92021-102">COR_FIELD Structure</span></span>
<span data-ttu-id="92021-103">提供有关对象中的某个字段的信息。</span><span class="sxs-lookup"><span data-stu-id="92021-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92021-104">语法</span><span class="sxs-lookup"><span data-stu-id="92021-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="92021-105">成员</span><span class="sxs-lookup"><span data-stu-id="92021-105">Members</span></span>  
  
|<span data-ttu-id="92021-106">成员</span><span class="sxs-lookup"><span data-stu-id="92021-106">Member</span></span>|<span data-ttu-id="92021-107">描述</span><span class="sxs-lookup"><span data-stu-id="92021-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="92021-108">可用于获取字段信息的标记。`mdFieldDef`</span><span class="sxs-lookup"><span data-stu-id="92021-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="92021-109">对象中字段数据的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="92021-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="92021-110">标识此字段的类型的[COR_TYPEID](cor-typeid-structure.md)值。</span><span class="sxs-lookup"><span data-stu-id="92021-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="92021-111">一个 CorElementType 枚举值，该值指示字段的类型。</span><span class="sxs-lookup"><span data-stu-id="92021-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92021-112">备注</span><span class="sxs-lookup"><span data-stu-id="92021-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92021-113">要求</span><span class="sxs-lookup"><span data-stu-id="92021-113">Requirements</span></span>  
 <span data-ttu-id="92021-114">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92021-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92021-115">**标头：** Cordebug.idl，Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="92021-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92021-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92021-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92021-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92021-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92021-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="92021-118">See also</span></span>

- [<span data-ttu-id="92021-119">调试结构</span><span class="sxs-lookup"><span data-stu-id="92021-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="92021-120">调试</span><span class="sxs-lookup"><span data-stu-id="92021-120">Debugging</span></span>](index.md)
