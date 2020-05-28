---
title: CorPropertyAttr 枚举
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: b6651f30e0df3a5ffc29d310b9067e76761dcf01
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007528"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="44554-102">CorPropertyAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="44554-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="44554-103">包含一些值，用于描述属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="44554-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44554-104">语法</span><span class="sxs-lookup"><span data-stu-id="44554-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="44554-105">成员</span><span class="sxs-lookup"><span data-stu-id="44554-105">Members</span></span>  
  
|<span data-ttu-id="44554-106">成员</span><span class="sxs-lookup"><span data-stu-id="44554-106">Member</span></span>|<span data-ttu-id="44554-107">描述</span><span class="sxs-lookup"><span data-stu-id="44554-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="44554-108">指定属性是特殊的，其名称描述了操作方法。</span><span class="sxs-lookup"><span data-stu-id="44554-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="44554-109">保留供公共语言运行时内部使用。</span><span class="sxs-lookup"><span data-stu-id="44554-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="44554-110">指定公共语言运行时元数据内部 Api 应检查属性名称的编码。</span><span class="sxs-lookup"><span data-stu-id="44554-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="44554-111">指定属性具有默认值。</span><span class="sxs-lookup"><span data-stu-id="44554-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="44554-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="44554-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44554-113">要求</span><span class="sxs-lookup"><span data-stu-id="44554-113">Requirements</span></span>  
 <span data-ttu-id="44554-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44554-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44554-115">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="44554-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="44554-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44554-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44554-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44554-117">See also</span></span>

- [<span data-ttu-id="44554-118">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="44554-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
