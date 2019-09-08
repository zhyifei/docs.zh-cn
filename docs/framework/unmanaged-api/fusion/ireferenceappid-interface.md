---
title: IReferenceAppId 接口
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796366"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="304b3-102">IReferenceAppId 接口</span><span class="sxs-lookup"><span data-stu-id="304b3-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="304b3-103">表示对当前范围内的应用程序的唯一标识符的引用。</span><span class="sxs-lookup"><span data-stu-id="304b3-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="304b3-104">方法</span><span class="sxs-lookup"><span data-stu-id="304b3-104">Methods</span></span>  
  
|<span data-ttu-id="304b3-105">方法</span><span class="sxs-lookup"><span data-stu-id="304b3-105">Method</span></span>|<span data-ttu-id="304b3-106">描述</span><span class="sxs-lookup"><span data-stu-id="304b3-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="304b3-107">获取一个指针，该指针指向由此`IReferenceAppId`引用的应用程序的代码标识符的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="304b3-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="304b3-108">设置由此`IReferenceAppId`引用的应用程序的代码标识符。</span><span class="sxs-lookup"><span data-stu-id="304b3-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="304b3-109">获取一个接口指针，该`IEnumReferenceIdentity`指针指向一个`IReferenceIdentity`实例，该实例包含表示`IReferenceAppId`此的成员的实例。</span><span class="sxs-lookup"><span data-stu-id="304b3-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="304b3-110">获取一个指针，该指针指向此`IReferenceAppId`的订阅的标记标识符的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="304b3-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="304b3-111">将此`IReferenceAppId`订阅的标记标识符设置为指定的字符串值。</span><span class="sxs-lookup"><span data-stu-id="304b3-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="304b3-112">要求</span><span class="sxs-lookup"><span data-stu-id="304b3-112">Requirements</span></span>  
 <span data-ttu-id="304b3-113">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="304b3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="304b3-114">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="304b3-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="304b3-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="304b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="304b3-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="304b3-116">See also</span></span>

- [<span data-ttu-id="304b3-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="304b3-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="304b3-118">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="304b3-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="304b3-119">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="304b3-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
