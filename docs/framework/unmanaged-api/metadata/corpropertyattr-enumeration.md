---
title: "CorPropertyAttr 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPropertyAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPropertyAttr
helpviewer_keywords: CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a87676064f39dc01d04e881bbf46476fb12a1c65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="b3836-102">CorPropertyAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="b3836-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="b3836-103">包含一些值，用于描述属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="b3836-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3836-104">语法</span><span class="sxs-lookup"><span data-stu-id="b3836-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="b3836-105">成员</span><span class="sxs-lookup"><span data-stu-id="b3836-105">Members</span></span>  
  
|<span data-ttu-id="b3836-106">成员</span><span class="sxs-lookup"><span data-stu-id="b3836-106">Member</span></span>|<span data-ttu-id="b3836-107">描述</span><span class="sxs-lookup"><span data-stu-id="b3836-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="b3836-108">指定属性是特殊，并且其名称，描述如何。</span><span class="sxs-lookup"><span data-stu-id="b3836-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="b3836-109">保留供内部使用公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="b3836-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="b3836-110">指定公共语言运行时元数据内部 Api 应检查的属性名称的编码。</span><span class="sxs-lookup"><span data-stu-id="b3836-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="b3836-111">指定属性具有默认值。</span><span class="sxs-lookup"><span data-stu-id="b3836-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="b3836-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="b3836-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3836-113">要求</span><span class="sxs-lookup"><span data-stu-id="b3836-113">Requirements</span></span>  
 <span data-ttu-id="b3836-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b3836-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3836-115">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b3836-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b3836-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3836-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3836-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3836-117">See Also</span></span>  
 [<span data-ttu-id="b3836-118">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="b3836-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
