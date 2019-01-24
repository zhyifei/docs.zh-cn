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
ms.openlocfilehash: 713913fa046fc1bef12b8849ac82e4399a8dc534
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577571"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="93ede-102">CorPropertyAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="93ede-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="93ede-103">包含一些值，用于描述属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="93ede-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93ede-104">语法</span><span class="sxs-lookup"><span data-stu-id="93ede-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="93ede-105">成员</span><span class="sxs-lookup"><span data-stu-id="93ede-105">Members</span></span>  
  
|<span data-ttu-id="93ede-106">成员</span><span class="sxs-lookup"><span data-stu-id="93ede-106">Member</span></span>|<span data-ttu-id="93ede-107">描述</span><span class="sxs-lookup"><span data-stu-id="93ede-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="93ede-108">指定该属性是特殊，并且其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="93ede-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="93ede-109">公共语言运行时，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="93ede-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="93ede-110">指定公共语言运行时元数据内部 Api 应检查属性名称的编码。</span><span class="sxs-lookup"><span data-stu-id="93ede-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="93ede-111">指定属性具有默认值。</span><span class="sxs-lookup"><span data-stu-id="93ede-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="93ede-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="93ede-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93ede-113">要求</span><span class="sxs-lookup"><span data-stu-id="93ede-113">Requirements</span></span>  
 <span data-ttu-id="93ede-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="93ede-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93ede-115">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="93ede-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="93ede-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93ede-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ede-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="93ede-117">See also</span></span>
- [<span data-ttu-id="93ede-118">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="93ede-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
