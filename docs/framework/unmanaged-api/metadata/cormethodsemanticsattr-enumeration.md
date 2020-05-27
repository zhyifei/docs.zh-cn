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
ms.openlocfilehash: 1572c206f4a5a5fe0fd189ca84d0bcda2249c6d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007645"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="3bc6c-102">CorMethodSemanticsAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="3bc6c-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="3bc6c-103">包含一些值，用于描述方法和关联属性或事件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="3bc6c-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bc6c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3bc6c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="3bc6c-105">成员</span><span class="sxs-lookup"><span data-stu-id="3bc6c-105">Members</span></span>  
  
|<span data-ttu-id="3bc6c-106">成员</span><span class="sxs-lookup"><span data-stu-id="3bc6c-106">Member</span></span>|<span data-ttu-id="3bc6c-107">描述</span><span class="sxs-lookup"><span data-stu-id="3bc6c-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="3bc6c-108">指定该方法是属性的 `set` 访问器。</span><span class="sxs-lookup"><span data-stu-id="3bc6c-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="3bc6c-109">指定该方法是属性的 `get` 访问器。</span><span class="sxs-lookup"><span data-stu-id="3bc6c-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="3bc6c-110">指定该方法与在此处定义的属性或事件无关。</span><span class="sxs-lookup"><span data-stu-id="3bc6c-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="3bc6c-111">指定方法为事件添加处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="3bc6c-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="3bc6c-112">指定该方法移除事件的处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="3bc6c-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="3bc6c-113">指定方法引发事件。</span><span class="sxs-lookup"><span data-stu-id="3bc6c-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bc6c-114">要求</span><span class="sxs-lookup"><span data-stu-id="3bc6c-114">Requirements</span></span>  
 <span data-ttu-id="3bc6c-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3bc6c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bc6c-116">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="3bc6c-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3bc6c-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bc6c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc6c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bc6c-118">See also</span></span>

- [<span data-ttu-id="3bc6c-119">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="3bc6c-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
