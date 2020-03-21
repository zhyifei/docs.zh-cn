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
ms.openlocfilehash: 95a798d662b44cf2e088af84d3b1eec97da8e7fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177942"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="c42e5-102">CorPropertyAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="c42e5-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="c42e5-103">包含一些值，用于描述属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="c42e5-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c42e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="c42e5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c42e5-105">成员</span><span class="sxs-lookup"><span data-stu-id="c42e5-105">Members</span></span>  
  
|<span data-ttu-id="c42e5-106">成员</span><span class="sxs-lookup"><span data-stu-id="c42e5-106">Member</span></span>|<span data-ttu-id="c42e5-107">说明</span><span class="sxs-lookup"><span data-stu-id="c42e5-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="c42e5-108">指定属性是特殊的，并且其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="c42e5-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="c42e5-109">保留供公共语言运行时的内部使用。</span><span class="sxs-lookup"><span data-stu-id="c42e5-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="c42e5-110">指定通用语言运行时元数据内部 API 应检查属性名称的编码。</span><span class="sxs-lookup"><span data-stu-id="c42e5-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="c42e5-111">指定属性具有默认值。</span><span class="sxs-lookup"><span data-stu-id="c42e5-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="c42e5-112">未使用。</span><span class="sxs-lookup"><span data-stu-id="c42e5-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c42e5-113">要求</span><span class="sxs-lookup"><span data-stu-id="c42e5-113">Requirements</span></span>  
 <span data-ttu-id="c42e5-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c42e5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c42e5-115">**标题：** 科尔赫德</span><span class="sxs-lookup"><span data-stu-id="c42e5-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c42e5-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c42e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c42e5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c42e5-117">See also</span></span>

- [<span data-ttu-id="c42e5-118">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="c42e5-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
