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
ms.openlocfilehash: 2efe159eaa8b49d4d3825e9737593d0a12fc4d4c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740732"
---
# <a name="corfield-structure"></a><span data-ttu-id="5c1df-102">COR_FIELD 结构</span><span class="sxs-lookup"><span data-stu-id="5c1df-102">COR_FIELD Structure</span></span>
<span data-ttu-id="5c1df-103">提供有关对象中的某个字段的信息。</span><span class="sxs-lookup"><span data-stu-id="5c1df-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c1df-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c1df-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="5c1df-105">成员</span><span class="sxs-lookup"><span data-stu-id="5c1df-105">Members</span></span>  
  
|<span data-ttu-id="5c1df-106">成员</span><span class="sxs-lookup"><span data-stu-id="5c1df-106">Member</span></span>|<span data-ttu-id="5c1df-107">描述</span><span class="sxs-lookup"><span data-stu-id="5c1df-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="5c1df-108">`mdFieldDef`令牌可用于获取字段信息。</span><span class="sxs-lookup"><span data-stu-id="5c1df-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="5c1df-109">偏移量，以字节为单位，该对象中的字段数据。</span><span class="sxs-lookup"><span data-stu-id="5c1df-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="5c1df-110">一个[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)值，该值标识此字段的类型。</span><span class="sxs-lookup"><span data-stu-id="5c1df-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="5c1df-111">CorElementType 枚举值，该值指示字段的类型。</span><span class="sxs-lookup"><span data-stu-id="5c1df-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c1df-112">备注</span><span class="sxs-lookup"><span data-stu-id="5c1df-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c1df-113">要求</span><span class="sxs-lookup"><span data-stu-id="5c1df-113">Requirements</span></span>  
 <span data-ttu-id="5c1df-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c1df-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c1df-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c1df-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c1df-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c1df-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c1df-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c1df-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1df-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c1df-118">See also</span></span>

- [<span data-ttu-id="5c1df-119">调试结构</span><span class="sxs-lookup"><span data-stu-id="5c1df-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="5c1df-120">调试</span><span class="sxs-lookup"><span data-stu-id="5c1df-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
