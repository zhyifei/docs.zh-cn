---
title: "IReferenceAppId 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceAppId
helpviewer_keywords: IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cac4ef63292f1bd342bb94799872b002fdcdf945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="eaafe-102">IReferenceAppId 接口</span><span class="sxs-lookup"><span data-stu-id="eaafe-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="eaafe-103">表示当前范围中的应用程序的唯一标识符的引用。</span><span class="sxs-lookup"><span data-stu-id="eaafe-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eaafe-104">方法</span><span class="sxs-lookup"><span data-stu-id="eaafe-104">Methods</span></span>  
  
|<span data-ttu-id="eaafe-105">方法</span><span class="sxs-lookup"><span data-stu-id="eaafe-105">Method</span></span>|<span data-ttu-id="eaafe-106">描述</span><span class="sxs-lookup"><span data-stu-id="eaafe-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="eaafe-107">获取一个指向的字符串表示形式的代码标识符的应用程序引用此`IReferenceAppId`。</span><span class="sxs-lookup"><span data-stu-id="eaafe-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="eaafe-108">设置此引用的应用程序的代码标识符`IReferenceAppId`。</span><span class="sxs-lookup"><span data-stu-id="eaafe-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="eaafe-109">获取到的接口指针`IEnumReferenceIdentity`实例包含`IReferenceIdentity`表示此成员的实例`IReferenceAppId`。</span><span class="sxs-lookup"><span data-stu-id="eaafe-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="eaafe-110">获取一个指针指向的字符串表示形式的令牌标识符对此订阅`IReferenceAppId`。</span><span class="sxs-lookup"><span data-stu-id="eaafe-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="eaafe-111">设置与此订阅的令牌标识符`IReferenceAppId`到指定的字符串值。</span><span class="sxs-lookup"><span data-stu-id="eaafe-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eaafe-112">要求</span><span class="sxs-lookup"><span data-stu-id="eaafe-112">Requirements</span></span>  
 <span data-ttu-id="eaafe-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eaafe-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaafe-114">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="eaafe-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="eaafe-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaafe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaafe-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eaafe-116">See Also</span></span>  
 [<span data-ttu-id="eaafe-117">合成接口</span><span class="sxs-lookup"><span data-stu-id="eaafe-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="eaafe-118">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="eaafe-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [<span data-ttu-id="eaafe-119">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="eaafe-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
