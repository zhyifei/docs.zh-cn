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
ms.openlocfilehash: 2bb151d7c77104d8e24acefaac2e1f109b67f168
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796356"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="b5bd1-102">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="b5bd1-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="b5bd1-103">表示对代码对象的唯一签名的引用。</span><span class="sxs-lookup"><span data-stu-id="b5bd1-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b5bd1-104">方法</span><span class="sxs-lookup"><span data-stu-id="b5bd1-104">Methods</span></span>  
  
|<span data-ttu-id="b5bd1-105">方法</span><span class="sxs-lookup"><span data-stu-id="b5bd1-105">Method</span></span>|<span data-ttu-id="b5bd1-106">描述</span><span class="sxs-lookup"><span data-stu-id="b5bd1-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="b5bd1-107">获取一个指向与此`IReferenceIdentity` `IReferenceIdentity`相同的新实例的接口指针，指定的特性更改除外。</span><span class="sxs-lookup"><span data-stu-id="b5bd1-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="b5bd1-108">获取一个接口指针，该`IEnumIDENTITY_ATTRIBUTE`指针指向包含与此`IReferenceIdentity`关联的特性的实例。</span><span class="sxs-lookup"><span data-stu-id="b5bd1-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="b5bd1-109">获取指定命名空间中具有指定名称的特性的值。</span><span class="sxs-lookup"><span data-stu-id="b5bd1-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="b5bd1-110">将具有指定命名空间和指定名称的特性设置为指定值。</span><span class="sxs-lookup"><span data-stu-id="b5bd1-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5bd1-111">要求</span><span class="sxs-lookup"><span data-stu-id="b5bd1-111">Requirements</span></span>  
 <span data-ttu-id="b5bd1-112">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5bd1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5bd1-113">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="b5bd1-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b5bd1-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5bd1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5bd1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5bd1-115">See also</span></span>

- [<span data-ttu-id="b5bd1-116">合成接口</span><span class="sxs-lookup"><span data-stu-id="b5bd1-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="b5bd1-117">IEnumIDENTITY_ATTRIBUTE 接口</span><span class="sxs-lookup"><span data-stu-id="b5bd1-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
