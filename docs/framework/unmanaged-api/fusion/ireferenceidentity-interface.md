---
title: "IReferenceIdentity 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceIdentity
helpviewer_keywords: IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35c6152836adf02d541bacd149ed9ac053765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="0b075-102">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="0b075-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="0b075-103">表示对代码对象的唯一签名的引用。</span><span class="sxs-lookup"><span data-stu-id="0b075-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b075-104">方法</span><span class="sxs-lookup"><span data-stu-id="0b075-104">Methods</span></span>  
  
|<span data-ttu-id="0b075-105">方法</span><span class="sxs-lookup"><span data-stu-id="0b075-105">Method</span></span>|<span data-ttu-id="0b075-106">描述</span><span class="sxs-lookup"><span data-stu-id="0b075-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="0b075-107">到新获取的接口指针`IReferenceIdentity`是否与此实例`IReferenceIdentity`，除指定的属性更改外。</span><span class="sxs-lookup"><span data-stu-id="0b075-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="0b075-108">获取到的接口指针`IEnumIDENTITY_ATTRIBUTE`实例，其中包含与此关联的特性`IReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="0b075-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="0b075-109">获取属性的值中指定的命名空间，具有指定名称。</span><span class="sxs-lookup"><span data-stu-id="0b075-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="0b075-110">设置具有指定的命名空间和指定的名称与指定的值的属性。</span><span class="sxs-lookup"><span data-stu-id="0b075-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b075-111">要求</span><span class="sxs-lookup"><span data-stu-id="0b075-111">Requirements</span></span>  
 <span data-ttu-id="0b075-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b075-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b075-113">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="0b075-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="0b075-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b075-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b075-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b075-115">See Also</span></span>  
 [<span data-ttu-id="0b075-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="0b075-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="0b075-117">IEnumIDENTITY_ATTRIBUTE 接口</span><span class="sxs-lookup"><span data-stu-id="0b075-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
