---
title: IEnumReferenceIdentity 接口
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796442"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="75f92-102">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="75f92-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="75f92-103">用作对象集合的`IReferenceIdentity`枚举器。</span><span class="sxs-lookup"><span data-stu-id="75f92-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75f92-104">方法</span><span class="sxs-lookup"><span data-stu-id="75f92-104">Methods</span></span>  
  
|<span data-ttu-id="75f92-105">方法</span><span class="sxs-lookup"><span data-stu-id="75f92-105">Method</span></span>|<span data-ttu-id="75f92-106">描述</span><span class="sxs-lookup"><span data-stu-id="75f92-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="75f92-107">获取一个接口指针，该指针`IEnumReferenceIdentity`指向包含与此`IEnumReferenceIdentity`相同的成员的新。</span><span class="sxs-lookup"><span data-stu-id="75f92-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="75f92-108">从当前位置开始，获取`IReferenceIdentity`指定数目的对象。</span><span class="sxs-lookup"><span data-stu-id="75f92-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="75f92-109">将指令指针移到此`IEnumReferenceIdentity`的开头。</span><span class="sxs-lookup"><span data-stu-id="75f92-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="75f92-110">从当前位置开始，将指令指针向前移动指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="75f92-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75f92-111">要求</span><span class="sxs-lookup"><span data-stu-id="75f92-111">Requirements</span></span>  
 <span data-ttu-id="75f92-112">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75f92-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75f92-113">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="75f92-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="75f92-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75f92-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f92-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="75f92-115">See also</span></span>

- [<span data-ttu-id="75f92-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="75f92-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="75f92-117">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="75f92-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
