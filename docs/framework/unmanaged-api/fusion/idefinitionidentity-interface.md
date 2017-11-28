---
title: "IDefinitionIdentity 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionIdentity
helpviewer_keywords: IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a63436f107a2604fd5620854339447a4af254e52
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="0f897-102">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="0f897-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="0f897-103">表示在当前范围内定义应用程序的代码的唯一签名。</span><span class="sxs-lookup"><span data-stu-id="0f897-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f897-104">方法</span><span class="sxs-lookup"><span data-stu-id="0f897-104">Methods</span></span>  
  
|<span data-ttu-id="0f897-105">方法</span><span class="sxs-lookup"><span data-stu-id="0f897-105">Method</span></span>|<span data-ttu-id="0f897-106">描述</span><span class="sxs-lookup"><span data-stu-id="0f897-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="0f897-107">到新获取的接口指针`IDefinitionIdentity`对象，它等同于此`IDefinitionIdentity`，除指定的属性更改外。</span><span class="sxs-lookup"><span data-stu-id="0f897-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="0f897-108">获取到的接口指针[IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)对象，其中包含与此关联的特性`IDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="0f897-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="0f897-109">获取具有指定名称的属性的值中指定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0f897-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="0f897-110">设置为指定的值指定的命名空间中具有指定的名称的属性。</span><span class="sxs-lookup"><span data-stu-id="0f897-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f897-111">要求</span><span class="sxs-lookup"><span data-stu-id="0f897-111">Requirements</span></span>  
 <span data-ttu-id="0f897-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0f897-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f897-113">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="0f897-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0f897-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f897-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f897-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f897-115">See Also</span></span>  
 [<span data-ttu-id="0f897-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="0f897-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
