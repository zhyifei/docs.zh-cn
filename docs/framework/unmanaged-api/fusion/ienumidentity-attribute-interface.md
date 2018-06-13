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
ms.openlocfilehash: da6462a320b1f090940473f566ade91d36e74780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431696"
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="7f764-102">IEnumIDENTITY_ATTRIBUTE 接口</span><span class="sxs-lookup"><span data-stu-id="7f764-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="7f764-103">用作当前范围中的代码对象的属性的枚举数。</span><span class="sxs-lookup"><span data-stu-id="7f764-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f764-104">方法</span><span class="sxs-lookup"><span data-stu-id="7f764-104">Methods</span></span>  
  
|<span data-ttu-id="7f764-105">方法</span><span class="sxs-lookup"><span data-stu-id="7f764-105">Method</span></span>|<span data-ttu-id="7f764-106">描述</span><span class="sxs-lookup"><span data-stu-id="7f764-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="7f764-107">到新获取的接口指针`IEnumIDENTITY_ATTRIBUTE`，其中包含与此相同的成员`IEnumIDENTITY_ATTRIBUTE`。</span><span class="sxs-lookup"><span data-stu-id="7f764-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="7f764-108">此元素中包含的数据写入`IEnumIDENTITY_ATTRIBUTE`到指定的数据缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7f764-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="7f764-109">获取指定的数目的属性，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="7f764-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="7f764-110">将指令指针移到此开头`IEnumIDENTITY_ATTRIBUTE`。</span><span class="sxs-lookup"><span data-stu-id="7f764-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="7f764-111">将指令指针向前移动指定数量的元素，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="7f764-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f764-112">要求</span><span class="sxs-lookup"><span data-stu-id="7f764-112">Requirements</span></span>  
 <span data-ttu-id="7f764-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7f764-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f764-114">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="7f764-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="7f764-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f764-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f764-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f764-116">See Also</span></span>  
 [<span data-ttu-id="7f764-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="7f764-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
