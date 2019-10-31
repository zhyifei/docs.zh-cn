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
ms.openlocfilehash: 1305b9ebe3cd87ba002ee87610ff309d015a44e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131751"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="35886-102">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="35886-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="35886-103">用作 `IReferenceIdentity` 对象的集合的枚举器。</span><span class="sxs-lookup"><span data-stu-id="35886-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35886-104">方法</span><span class="sxs-lookup"><span data-stu-id="35886-104">Methods</span></span>  
  
|<span data-ttu-id="35886-105">方法</span><span class="sxs-lookup"><span data-stu-id="35886-105">Method</span></span>|<span data-ttu-id="35886-106">描述</span><span class="sxs-lookup"><span data-stu-id="35886-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="35886-107">获取一个接口指针，该指针指向与此 `IEnumReferenceIdentity`包含相同成员的新 `IEnumReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="35886-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="35886-108">从当前位置开始，获取指定数目的 `IReferenceIdentity` 对象。</span><span class="sxs-lookup"><span data-stu-id="35886-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="35886-109">将指令指针移动到此 `IEnumReferenceIdentity`的开头。</span><span class="sxs-lookup"><span data-stu-id="35886-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="35886-110">从当前位置开始，将指令指针向前移动指定数量的元素。</span><span class="sxs-lookup"><span data-stu-id="35886-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35886-111">要求</span><span class="sxs-lookup"><span data-stu-id="35886-111">Requirements</span></span>  
 <span data-ttu-id="35886-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35886-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35886-113">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="35886-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="35886-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35886-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35886-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="35886-115">See also</span></span>

- [<span data-ttu-id="35886-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="35886-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="35886-117">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="35886-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
