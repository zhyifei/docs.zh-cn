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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f888c39160e52e550d07f58b9c5bcd11fd625658
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564076"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="d7f64-102">CorMethodSemanticsAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="d7f64-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="d7f64-103">包含一些值，用于描述方法和关联属性或事件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="d7f64-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f64-104">语法</span><span class="sxs-lookup"><span data-stu-id="d7f64-104">Syntax</span></span>  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="d7f64-105">成员</span><span class="sxs-lookup"><span data-stu-id="d7f64-105">Members</span></span>  
  
|<span data-ttu-id="d7f64-106">成员</span><span class="sxs-lookup"><span data-stu-id="d7f64-106">Member</span></span>|<span data-ttu-id="d7f64-107">描述</span><span class="sxs-lookup"><span data-stu-id="d7f64-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="d7f64-108">指定的方法是`set`属性访问器。</span><span class="sxs-lookup"><span data-stu-id="d7f64-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="d7f64-109">指定的方法是`get`属性访问器。</span><span class="sxs-lookup"><span data-stu-id="d7f64-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="d7f64-110">指定该方法具有一个属性或事件而不是此处定义的关系。</span><span class="sxs-lookup"><span data-stu-id="d7f64-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="d7f64-111">指定该方法将添加事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="d7f64-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="d7f64-112">指定方法移除事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="d7f64-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="d7f64-113">指定该方法将引发一个事件。</span><span class="sxs-lookup"><span data-stu-id="d7f64-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7f64-114">要求</span><span class="sxs-lookup"><span data-stu-id="d7f64-114">Requirements</span></span>  
 <span data-ttu-id="d7f64-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d7f64-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f64-116">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d7f64-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d7f64-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f64-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f64-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7f64-118">See also</span></span>
- [<span data-ttu-id="d7f64-119">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="d7f64-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
