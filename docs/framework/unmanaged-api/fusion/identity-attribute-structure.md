---
title: IDENTITY_ATTRIBUTE 结构
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796483"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="59bc1-102">IDENTITY_ATTRIBUTE 结构</span><span class="sxs-lookup"><span data-stu-id="59bc1-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="59bc1-103">包含有关[IDefinitionIdentity](idefinitionidentity-interface.md)实例的元数据属性信息。</span><span class="sxs-lookup"><span data-stu-id="59bc1-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59bc1-104">语法</span><span class="sxs-lookup"><span data-stu-id="59bc1-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="59bc1-105">成员</span><span class="sxs-lookup"><span data-stu-id="59bc1-105">Members</span></span>  
  
|<span data-ttu-id="59bc1-106">成员</span><span class="sxs-lookup"><span data-stu-id="59bc1-106">Member</span></span>|<span data-ttu-id="59bc1-107">描述</span><span class="sxs-lookup"><span data-stu-id="59bc1-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="59bc1-108">指向以 null 结尾的字符串的指针，该字符串包含特性所在的命名空间。</span><span class="sxs-lookup"><span data-stu-id="59bc1-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="59bc1-109">指向以 null 结尾的字符串的指针，该字符串包含属性的名称。</span><span class="sxs-lookup"><span data-stu-id="59bc1-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="59bc1-110">指向以 null 结尾的字符串的指针，该字符串包含属性的值。</span><span class="sxs-lookup"><span data-stu-id="59bc1-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59bc1-111">备注</span><span class="sxs-lookup"><span data-stu-id="59bc1-111">Remarks</span></span>  
 <span data-ttu-id="59bc1-112">该`IDENTITY_ATTRIBUTE`结构包含三个指向以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="59bc1-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="59bc1-113">这三个字符串描述了一个属性。</span><span class="sxs-lookup"><span data-stu-id="59bc1-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="59bc1-114">`IDENTITY_ATTRIBUTE`结构的实例与[IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md)结构的实例相关联。</span><span class="sxs-lookup"><span data-stu-id="59bc1-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="59bc1-115">结构包含实际的字符串，相应`IDENTITY_ATTRIBUTE_BLOB`的结构列出了`IDENTITY_ATTRIBUTE`结构中列出的三个字符串的偏移量。 `IDENTITY_ATTRIBUTE`</span><span class="sxs-lookup"><span data-stu-id="59bc1-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59bc1-116">要求</span><span class="sxs-lookup"><span data-stu-id="59bc1-116">Requirements</span></span>  
 <span data-ttu-id="59bc1-117">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="59bc1-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59bc1-118">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="59bc1-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="59bc1-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59bc1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59bc1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="59bc1-120">See also</span></span>

- [<span data-ttu-id="59bc1-121">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="59bc1-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="59bc1-122">IDENTITY_ATTRIBUTE_BLOB 结构</span><span class="sxs-lookup"><span data-stu-id="59bc1-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="59bc1-123">合成结构</span><span class="sxs-lookup"><span data-stu-id="59bc1-123">Fusion Structures</span></span>](fusion-structures.md)
