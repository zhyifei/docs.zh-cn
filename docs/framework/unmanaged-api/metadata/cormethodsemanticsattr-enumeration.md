---
title: CorMethodSemanticsAttr 枚举
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: bab215a8221696a0e43e228278085fcef52a40e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442823"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="c64dd-102">CorMethodSemanticsAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="c64dd-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="c64dd-103">包含一些值，用于描述方法和关联属性或事件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="c64dd-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c64dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="c64dd-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="c64dd-105">Members</span><span class="sxs-lookup"><span data-stu-id="c64dd-105">Members</span></span>  
  
|<span data-ttu-id="c64dd-106">成员</span><span class="sxs-lookup"><span data-stu-id="c64dd-106">Member</span></span>|<span data-ttu-id="c64dd-107">说明</span><span class="sxs-lookup"><span data-stu-id="c64dd-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="c64dd-108">指定该方法是属性的 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="c64dd-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="c64dd-109">指定该方法是属性的 `get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="c64dd-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="c64dd-110">指定该方法与在此处定义的属性或事件无关。</span><span class="sxs-lookup"><span data-stu-id="c64dd-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="c64dd-111">指定方法为事件添加处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="c64dd-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="c64dd-112">指定该方法移除事件的处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="c64dd-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="c64dd-113">指定方法引发事件。</span><span class="sxs-lookup"><span data-stu-id="c64dd-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c64dd-114">要求</span><span class="sxs-lookup"><span data-stu-id="c64dd-114">Requirements</span></span>  
 <span data-ttu-id="c64dd-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c64dd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c64dd-116">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="c64dd-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="c64dd-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c64dd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64dd-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c64dd-118">See also</span></span>

- [<span data-ttu-id="c64dd-119">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="c64dd-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
