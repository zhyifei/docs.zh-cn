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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1a0fff266e964b506b2dc7c4030caa54abaa5ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171816"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="c8d9f-102">CorPropertyAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="c8d9f-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="c8d9f-103">包含一些值，用于描述属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="c8d9f-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8d9f-104">语法</span><span class="sxs-lookup"><span data-stu-id="c8d9f-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c8d9f-105">成员</span><span class="sxs-lookup"><span data-stu-id="c8d9f-105">Members</span></span>  
  
|<span data-ttu-id="c8d9f-106">成员</span><span class="sxs-lookup"><span data-stu-id="c8d9f-106">Member</span></span>|<span data-ttu-id="c8d9f-107">描述</span><span class="sxs-lookup"><span data-stu-id="c8d9f-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="c8d9f-108">指定该属性是特殊，并且其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="c8d9f-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="c8d9f-109">公共语言运行时，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="c8d9f-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="c8d9f-110">指定公共语言运行时元数据内部 Api 应检查属性名称的编码。</span><span class="sxs-lookup"><span data-stu-id="c8d9f-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="c8d9f-111">指定属性具有默认值。</span><span class="sxs-lookup"><span data-stu-id="c8d9f-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="c8d9f-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="c8d9f-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8d9f-113">要求</span><span class="sxs-lookup"><span data-stu-id="c8d9f-113">Requirements</span></span>  
 <span data-ttu-id="c8d9f-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d9f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8d9f-115">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="c8d9f-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c8d9f-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8d9f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d9f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8d9f-117">See also</span></span>

- [<span data-ttu-id="c8d9f-118">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="c8d9f-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
