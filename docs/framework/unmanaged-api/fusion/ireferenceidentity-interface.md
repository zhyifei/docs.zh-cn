---
title: IReferenceIdentity 接口
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd46ea26532074c9ea42da4d07a38ed583aad076
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220157"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="2d396-102">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="2d396-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="2d396-103">表示代码对象的唯一签名的引用。</span><span class="sxs-lookup"><span data-stu-id="2d396-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d396-104">方法</span><span class="sxs-lookup"><span data-stu-id="2d396-104">Methods</span></span>  
  
|<span data-ttu-id="2d396-105">方法</span><span class="sxs-lookup"><span data-stu-id="2d396-105">Method</span></span>|<span data-ttu-id="2d396-106">描述</span><span class="sxs-lookup"><span data-stu-id="2d396-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="2d396-107">为新获取的接口指针`IReferenceIdentity`是否与此实例`IReferenceIdentity`，除了指定的属性更改。</span><span class="sxs-lookup"><span data-stu-id="2d396-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="2d396-108">获取到的接口指针`IEnumIDENTITY_ATTRIBUTE`实例，它包含与此相关联的属性`IReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="2d396-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="2d396-109">获取具有指定名称的指定命名空间中的属性的值。</span><span class="sxs-lookup"><span data-stu-id="2d396-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="2d396-110">设置具有指定的命名空间和指定的值将指定的名称的特性。</span><span class="sxs-lookup"><span data-stu-id="2d396-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d396-111">要求</span><span class="sxs-lookup"><span data-stu-id="2d396-111">Requirements</span></span>  
 <span data-ttu-id="2d396-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d396-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d396-113">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="2d396-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="2d396-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d396-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d396-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d396-115">See also</span></span>

- [<span data-ttu-id="2d396-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="2d396-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="2d396-117">IEnumIDENTITY_ATTRIBUTE 接口</span><span class="sxs-lookup"><span data-stu-id="2d396-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
