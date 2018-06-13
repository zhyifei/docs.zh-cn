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
ms.openlocfilehash: f716ff35ae0cd3d2a53c55756b8957e54fa355c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431530"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="76c9c-102">IDENTITY_ATTRIBUTE 结构</span><span class="sxs-lookup"><span data-stu-id="76c9c-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="76c9c-103">包含有关的元数据特性信息[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="76c9c-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76c9c-104">语法</span><span class="sxs-lookup"><span data-stu-id="76c9c-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="76c9c-105">成员</span><span class="sxs-lookup"><span data-stu-id="76c9c-105">Members</span></span>  
  
|<span data-ttu-id="76c9c-106">成员</span><span class="sxs-lookup"><span data-stu-id="76c9c-106">Member</span></span>|<span data-ttu-id="76c9c-107">描述</span><span class="sxs-lookup"><span data-stu-id="76c9c-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="76c9c-108">属性是在指向包含的命名空间的以 null 结尾的字符字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="76c9c-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="76c9c-109">指向包含属性的名称的以 null 结尾的字符字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="76c9c-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="76c9c-110">指向包含属性的值的以 null 结尾的字符字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="76c9c-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76c9c-111">备注</span><span class="sxs-lookup"><span data-stu-id="76c9c-111">Remarks</span></span>  
 <span data-ttu-id="76c9c-112">`IDENTITY_ATTRIBUTE`结构包含三个指针指向以 null 结尾的字符字符串。</span><span class="sxs-lookup"><span data-stu-id="76c9c-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="76c9c-113">这三个字符串描述一个属性。</span><span class="sxs-lookup"><span data-stu-id="76c9c-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="76c9c-114">实例`IDENTITY_ATTRIBUTE`结构是与实例相关联[IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)结构。</span><span class="sxs-lookup"><span data-stu-id="76c9c-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="76c9c-115">`IDENTITY_ATTRIBUTE`结构包含实际的字符串，并相应`IDENTITY_ATTRIBUTE_BLOB`结构列出的三个字符串中列出的偏移量`IDENTITY_ATTRIBUTE`结构。</span><span class="sxs-lookup"><span data-stu-id="76c9c-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76c9c-116">要求</span><span class="sxs-lookup"><span data-stu-id="76c9c-116">Requirements</span></span>  
 <span data-ttu-id="76c9c-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76c9c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76c9c-118">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="76c9c-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="76c9c-119">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76c9c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76c9c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="76c9c-120">See Also</span></span>  
 [<span data-ttu-id="76c9c-121">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="76c9c-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [<span data-ttu-id="76c9c-122">IDENTITY_ATTRIBUTE_BLOB 结构</span><span class="sxs-lookup"><span data-stu-id="76c9c-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [<span data-ttu-id="76c9c-123">合成结构</span><span class="sxs-lookup"><span data-stu-id="76c9c-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
