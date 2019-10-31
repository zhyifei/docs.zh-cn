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
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131650"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="a4ae2-102">IReferenceAppId 接口</span><span class="sxs-lookup"><span data-stu-id="a4ae2-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="a4ae2-103">表示对当前范围内的应用程序的唯一标识符的引用。</span><span class="sxs-lookup"><span data-stu-id="a4ae2-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4ae2-104">方法</span><span class="sxs-lookup"><span data-stu-id="a4ae2-104">Methods</span></span>  
  
|<span data-ttu-id="a4ae2-105">方法</span><span class="sxs-lookup"><span data-stu-id="a4ae2-105">Method</span></span>|<span data-ttu-id="a4ae2-106">描述</span><span class="sxs-lookup"><span data-stu-id="a4ae2-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="a4ae2-107">获取一个指针，该指针指向此 `IReferenceAppId`引用的应用程序的代码标识符的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="a4ae2-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="a4ae2-108">设置此 `IReferenceAppId`引用的应用程序的代码标识符。</span><span class="sxs-lookup"><span data-stu-id="a4ae2-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="a4ae2-109">获取一个接口指针，该指针指向包含表示此 `IReferenceAppId`成员的 `IReferenceIdentity` 实例的 `IEnumReferenceIdentity` 实例。</span><span class="sxs-lookup"><span data-stu-id="a4ae2-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="a4ae2-110">获取一个指针，该指针指向此 `IReferenceAppId`的订阅的标记标识符的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="a4ae2-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="a4ae2-111">将此 `IReferenceAppId` 的订阅的标记标识符设置为指定的字符串值。</span><span class="sxs-lookup"><span data-stu-id="a4ae2-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4ae2-112">要求</span><span class="sxs-lookup"><span data-stu-id="a4ae2-112">Requirements</span></span>  
 <span data-ttu-id="a4ae2-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4ae2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4ae2-114">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="a4ae2-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a4ae2-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4ae2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ae2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4ae2-116">See also</span></span>

- [<span data-ttu-id="a4ae2-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="a4ae2-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="a4ae2-118">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="a4ae2-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="a4ae2-119">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="a4ae2-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
