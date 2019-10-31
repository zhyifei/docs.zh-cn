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
ms.openlocfilehash: 8b7edf1cc642228c4a79c855b51727264f31741c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107984"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="5d4d7-102">IDENTITY_ATTRIBUTE 结构</span><span class="sxs-lookup"><span data-stu-id="5d4d7-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="5d4d7-103">包含有关[IDefinitionIdentity](idefinitionidentity-interface.md)实例的元数据属性信息。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d4d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d4d7-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="5d4d7-105">Members</span><span class="sxs-lookup"><span data-stu-id="5d4d7-105">Members</span></span>  
  
|<span data-ttu-id="5d4d7-106">成员</span><span class="sxs-lookup"><span data-stu-id="5d4d7-106">Member</span></span>|<span data-ttu-id="5d4d7-107">描述</span><span class="sxs-lookup"><span data-stu-id="5d4d7-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="5d4d7-108">指向以 null 结尾的字符串的指针，该字符串包含特性所在的命名空间。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="5d4d7-109">指向以 null 结尾的字符串的指针，该字符串包含属性的名称。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="5d4d7-110">指向以 null 结尾的字符串的指针，该字符串包含属性的值。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d4d7-111">备注</span><span class="sxs-lookup"><span data-stu-id="5d4d7-111">Remarks</span></span>  
 <span data-ttu-id="5d4d7-112">`IDENTITY_ATTRIBUTE` 结构包含三个指向以 null 结尾的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="5d4d7-113">这三个字符串描述了一个属性。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="5d4d7-114">`IDENTITY_ATTRIBUTE` 结构的实例与[IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md)结构的实例相关联。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="5d4d7-115">`IDENTITY_ATTRIBUTE` 结构包含实际字符串，相应的 `IDENTITY_ATTRIBUTE_BLOB` 结构列出了 `IDENTITY_ATTRIBUTE` 结构中列出的三个字符串的偏移量。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d4d7-116">要求</span><span class="sxs-lookup"><span data-stu-id="5d4d7-116">Requirements</span></span>  
 <span data-ttu-id="5d4d7-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d4d7-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d4d7-118">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="5d4d7-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="5d4d7-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d4d7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d4d7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d4d7-120">See also</span></span>

- [<span data-ttu-id="5d4d7-121">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="5d4d7-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="5d4d7-122">IDENTITY_ATTRIBUTE_BLOB 结构</span><span class="sxs-lookup"><span data-stu-id="5d4d7-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="5d4d7-123">合成结构</span><span class="sxs-lookup"><span data-stu-id="5d4d7-123">Fusion Structures</span></span>](fusion-structures.md)
