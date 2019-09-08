---
title: IEnumIDENTITY_ATTRIBUTE 接口
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbb3ac150ebfe9fe3698427d8bb2bfb3e3347c07
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796468"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="e1f1a-102">IEnumIDENTITY_ATTRIBUTE 接口</span><span class="sxs-lookup"><span data-stu-id="e1f1a-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="e1f1a-103">用作当前范围中代码对象的特性的枚举数。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1f1a-104">方法</span><span class="sxs-lookup"><span data-stu-id="e1f1a-104">Methods</span></span>  
  
|<span data-ttu-id="e1f1a-105">方法</span><span class="sxs-lookup"><span data-stu-id="e1f1a-105">Method</span></span>|<span data-ttu-id="e1f1a-106">描述</span><span class="sxs-lookup"><span data-stu-id="e1f1a-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="e1f1a-107">获取一个接口指针，该指针`IEnumIDENTITY_ATTRIBUTE`指向包含与此`IEnumIDENTITY_ATTRIBUTE`相同的成员的新。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="e1f1a-108">将此`IEnumIDENTITY_ATTRIBUTE`中包含的数据写入指定的数据缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="e1f1a-109">从当前位置开始，获取指定数目的属性。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="e1f1a-110">将指令指针移到此`IEnumIDENTITY_ATTRIBUTE`的开头。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="e1f1a-111">从当前位置开始，将指令指针向前移动指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1f1a-112">要求</span><span class="sxs-lookup"><span data-stu-id="e1f1a-112">Requirements</span></span>  
 <span data-ttu-id="e1f1a-113">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1f1a-114">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="e1f1a-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e1f1a-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1f1a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f1a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1f1a-116">See also</span></span>

- [<span data-ttu-id="e1f1a-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="e1f1a-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
