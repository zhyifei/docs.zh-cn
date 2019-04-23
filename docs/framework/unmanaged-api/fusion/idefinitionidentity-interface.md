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
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192662"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="fc86b-102">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="fc86b-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="fc86b-103">表示在当前范围内定义的应用程序的代码的唯一签名。</span><span class="sxs-lookup"><span data-stu-id="fc86b-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fc86b-104">方法</span><span class="sxs-lookup"><span data-stu-id="fc86b-104">Methods</span></span>  
  
|<span data-ttu-id="fc86b-105">方法</span><span class="sxs-lookup"><span data-stu-id="fc86b-105">Method</span></span>|<span data-ttu-id="fc86b-106">描述</span><span class="sxs-lookup"><span data-stu-id="fc86b-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="fc86b-107">为新获取的接口指针`IDefinitionIdentity`对象，它等同于此`IDefinitionIdentity`，除了指定的属性更改。</span><span class="sxs-lookup"><span data-stu-id="fc86b-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="fc86b-108">获取到的接口指针[IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)对象，其中包含与此相关联的属性`IDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="fc86b-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="fc86b-109">获取具有指定名称的属性的值中指定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="fc86b-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="fc86b-110">设置为指定的值指定的命名空间中具有指定的名称的特性。</span><span class="sxs-lookup"><span data-stu-id="fc86b-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc86b-111">要求</span><span class="sxs-lookup"><span data-stu-id="fc86b-111">Requirements</span></span>  
 <span data-ttu-id="fc86b-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc86b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc86b-113">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="fc86b-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="fc86b-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc86b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc86b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc86b-115">See also</span></span>

- [<span data-ttu-id="fc86b-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="fc86b-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
