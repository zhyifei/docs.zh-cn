---
title: IDefinitionAppId 接口
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e8bb31967a6ad515761e6cd03657f2c834debe5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545551"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="0297c-102">IDefinitionAppId 接口</span><span class="sxs-lookup"><span data-stu-id="0297c-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="0297c-103">表示在当前范围内定义的应用程序的代码的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0297c-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0297c-104">方法</span><span class="sxs-lookup"><span data-stu-id="0297c-104">Methods</span></span>  
  
|<span data-ttu-id="0297c-105">方法</span><span class="sxs-lookup"><span data-stu-id="0297c-105">Method</span></span>|<span data-ttu-id="0297c-106">描述</span><span class="sxs-lookup"><span data-stu-id="0297c-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="0297c-107">获取表示在此代码的格式化的字符串`IDefinitionAppId`对象。</span><span class="sxs-lookup"><span data-stu-id="0297c-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="0297c-108">设置此代码`IDefinitionAppId`对象改为指定格式字符串的值。</span><span class="sxs-lookup"><span data-stu-id="0297c-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="0297c-109">获取到的接口指针[IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)对象，其中包含当前应用程序路径中的程序集。</span><span class="sxs-lookup"><span data-stu-id="0297c-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="0297c-110">设置到由指定引用的值在当前范围内的程序集的应用程序路径[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="0297c-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="0297c-111">获取一个指针指向的标记标识符的字符串表示形式与此订阅`IDefinitionAppId`对象。</span><span class="sxs-lookup"><span data-stu-id="0297c-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="0297c-112">设置与此订阅的标记标识符`IDefinitionAppId`对象到指定的字符串值。</span><span class="sxs-lookup"><span data-stu-id="0297c-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0297c-113">要求</span><span class="sxs-lookup"><span data-stu-id="0297c-113">Requirements</span></span>  
 <span data-ttu-id="0297c-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0297c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0297c-115">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="0297c-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0297c-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0297c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0297c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0297c-117">See also</span></span>
- [<span data-ttu-id="0297c-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="0297c-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
