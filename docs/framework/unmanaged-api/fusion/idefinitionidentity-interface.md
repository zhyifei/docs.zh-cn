---
title: IDefinitionIdentity 接口
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84c595bfdcca84ee43a53e2ea913cc978ae0953e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796521"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="a07e7-102">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="a07e7-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="a07e7-103">表示定义当前作用域中的应用程序的代码的唯一签名。</span><span class="sxs-lookup"><span data-stu-id="a07e7-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a07e7-104">方法</span><span class="sxs-lookup"><span data-stu-id="a07e7-104">Methods</span></span>  
  
|<span data-ttu-id="a07e7-105">方法</span><span class="sxs-lookup"><span data-stu-id="a07e7-105">Method</span></span>|<span data-ttu-id="a07e7-106">描述</span><span class="sxs-lookup"><span data-stu-id="a07e7-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="a07e7-107">获取一个接口指针，该指针`IDefinitionIdentity`指向与此`IDefinitionIdentity`相同的新对象，但指定的特性更改除外。</span><span class="sxs-lookup"><span data-stu-id="a07e7-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="a07e7-108">获取一个指向[IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)对象的接口指针，该对象包含与此`IDefinitionIdentity`关联的特性。</span><span class="sxs-lookup"><span data-stu-id="a07e7-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="a07e7-109">获取指定命名空间中具有指定名称的属性的值。</span><span class="sxs-lookup"><span data-stu-id="a07e7-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="a07e7-110">将指定命名空间中具有指定名称的特性设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="a07e7-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a07e7-111">要求</span><span class="sxs-lookup"><span data-stu-id="a07e7-111">Requirements</span></span>  
 <span data-ttu-id="a07e7-112">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a07e7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a07e7-113">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="a07e7-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a07e7-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a07e7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a07e7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a07e7-115">See also</span></span>

- [<span data-ttu-id="a07e7-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="a07e7-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
