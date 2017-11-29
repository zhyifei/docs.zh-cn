---
title: "IEnumIDENTITY_ATTRIBUTE 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumIDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords: IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f88e400556421e0908e0a0b115f66ec3221124c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="f382f-102">IEnumIDENTITY_ATTRIBUTE 接口</span><span class="sxs-lookup"><span data-stu-id="f382f-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="f382f-103">用作当前范围中的代码对象的属性的枚举数。</span><span class="sxs-lookup"><span data-stu-id="f382f-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f382f-104">方法</span><span class="sxs-lookup"><span data-stu-id="f382f-104">Methods</span></span>  
  
|<span data-ttu-id="f382f-105">方法</span><span class="sxs-lookup"><span data-stu-id="f382f-105">Method</span></span>|<span data-ttu-id="f382f-106">描述</span><span class="sxs-lookup"><span data-stu-id="f382f-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="f382f-107">到新获取的接口指针`IEnumIDENTITY_ATTRIBUTE`，其中包含与此相同的成员`IEnumIDENTITY_ATTRIBUTE`。</span><span class="sxs-lookup"><span data-stu-id="f382f-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="f382f-108">此元素中包含的数据写入`IEnumIDENTITY_ATTRIBUTE`到指定的数据缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f382f-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="f382f-109">获取指定的数目的属性，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="f382f-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="f382f-110">将指令指针移到此开头`IEnumIDENTITY_ATTRIBUTE`。</span><span class="sxs-lookup"><span data-stu-id="f382f-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="f382f-111">将指令指针向前移动指定数量的元素，从当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="f382f-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f382f-112">要求</span><span class="sxs-lookup"><span data-stu-id="f382f-112">Requirements</span></span>  
 <span data-ttu-id="f382f-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f382f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f382f-114">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="f382f-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f382f-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f382f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f382f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f382f-116">See Also</span></span>  
 [<span data-ttu-id="f382f-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="f382f-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
