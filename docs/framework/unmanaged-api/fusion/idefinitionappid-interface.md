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
ms.openlocfilehash: 929909a7f2c4fa1799c8fed94787b8f853c7eac2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796516"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="7c783-102">IDefinitionAppId 接口</span><span class="sxs-lookup"><span data-stu-id="7c783-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="7c783-103">表示定义当前作用域中的应用程序的代码的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7c783-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7c783-104">方法</span><span class="sxs-lookup"><span data-stu-id="7c783-104">Methods</span></span>  
  
|<span data-ttu-id="7c783-105">方法</span><span class="sxs-lookup"><span data-stu-id="7c783-105">Method</span></span>|<span data-ttu-id="7c783-106">描述</span><span class="sxs-lookup"><span data-stu-id="7c783-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="7c783-107">获取表示此`IDefinitionAppId`对象中的代码的格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="7c783-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="7c783-108">将此`IDefinitionAppId`对象的代码设置为指定的格式化字符串值。</span><span class="sxs-lookup"><span data-stu-id="7c783-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="7c783-109">获取一个指向[IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md)对象的接口指针，该对象包含当前应用程序路径中的程序集。</span><span class="sxs-lookup"><span data-stu-id="7c783-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="7c783-110">将当前范围中的程序集的应用程序路径设置为指定的[IDefinitionIdentity](idefinitionidentity-interface.md)对象所引用的值。</span><span class="sxs-lookup"><span data-stu-id="7c783-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="7c783-111">获取一个指针，该指针指向此`IDefinitionAppId`对象的订阅的标记标识符的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="7c783-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="7c783-112">将此`IDefinitionAppId`对象的订阅的标记标识符设置为指定的字符串值。</span><span class="sxs-lookup"><span data-stu-id="7c783-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c783-113">要求</span><span class="sxs-lookup"><span data-stu-id="7c783-113">Requirements</span></span>  
 <span data-ttu-id="7c783-114">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c783-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c783-115">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="7c783-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="7c783-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c783-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c783-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c783-117">See also</span></span>

- [<span data-ttu-id="7c783-118">合成接口</span><span class="sxs-lookup"><span data-stu-id="7c783-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
