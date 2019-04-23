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
ms.openlocfilehash: 25733e459423500352595d6be0eee26ef75ca7e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157191"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="35c8b-102">IReferenceAppId 接口</span><span class="sxs-lookup"><span data-stu-id="35c8b-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="35c8b-103">表示为当前作用域中的应用程序的唯一标识符的引用。</span><span class="sxs-lookup"><span data-stu-id="35c8b-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35c8b-104">方法</span><span class="sxs-lookup"><span data-stu-id="35c8b-104">Methods</span></span>  
  
|<span data-ttu-id="35c8b-105">方法</span><span class="sxs-lookup"><span data-stu-id="35c8b-105">Method</span></span>|<span data-ttu-id="35c8b-106">描述</span><span class="sxs-lookup"><span data-stu-id="35c8b-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="35c8b-107">获取此引用的应用程序的指针的代码标识符的字符串表示形式`IReferenceAppId`。</span><span class="sxs-lookup"><span data-stu-id="35c8b-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="35c8b-108">设置此引用的应用程序的代码标识符`IReferenceAppId`。</span><span class="sxs-lookup"><span data-stu-id="35c8b-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="35c8b-109">获取到的接口指针`IEnumReferenceIdentity`实例，包含`IReferenceIdentity`表示此成员的实例`IReferenceAppId`。</span><span class="sxs-lookup"><span data-stu-id="35c8b-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="35c8b-110">获取一个指针指向的标记标识符的字符串表示形式与此订阅`IReferenceAppId`。</span><span class="sxs-lookup"><span data-stu-id="35c8b-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="35c8b-111">设置与此订阅的标记标识符`IReferenceAppId`到指定的字符串值。</span><span class="sxs-lookup"><span data-stu-id="35c8b-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35c8b-112">要求</span><span class="sxs-lookup"><span data-stu-id="35c8b-112">Requirements</span></span>  
 <span data-ttu-id="35c8b-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35c8b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35c8b-114">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="35c8b-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="35c8b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35c8b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35c8b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="35c8b-116">See also</span></span>

- [<span data-ttu-id="35c8b-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="35c8b-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="35c8b-118">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="35c8b-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [<span data-ttu-id="35c8b-119">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="35c8b-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
