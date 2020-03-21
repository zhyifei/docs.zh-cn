---
title: IMetaDataEmit::SetEventProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177530"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="20c01-102">IMetaDataEmit::SetEventProps 方法</span><span class="sxs-lookup"><span data-stu-id="20c01-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="20c01-103">设置或更新由之前调用[IMetaDataEmit：:DefineEvent）](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)定义的事件的指定功能。</span><span class="sxs-lookup"><span data-stu-id="20c01-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c01-104">语法</span><span class="sxs-lookup"><span data-stu-id="20c01-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20c01-105">parameters</span><span class="sxs-lookup"><span data-stu-id="20c01-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="20c01-106">[在]事件令牌。</span><span class="sxs-lookup"><span data-stu-id="20c01-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="20c01-107">[在]事件标志。</span><span class="sxs-lookup"><span data-stu-id="20c01-107">[in] Event flags.</span></span> <span data-ttu-id="20c01-108">这是值的`CorEventAttr`位掩码。</span><span class="sxs-lookup"><span data-stu-id="20c01-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="20c01-109">[在]事件类的令牌。</span><span class="sxs-lookup"><span data-stu-id="20c01-109">[in] The token for the event class.</span></span> <span data-ttu-id="20c01-110">这是 或`mdTypeDef``mdTypeRef`标记。</span><span class="sxs-lookup"><span data-stu-id="20c01-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="20c01-111">[在]用于订阅事件或 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="20c01-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="20c01-112">[在]用于取消订阅事件或 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="20c01-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="20c01-113">[在]用于（由派生类）引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="20c01-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="20c01-114">[在]与事件关联的其他方法的令牌数组。</span><span class="sxs-lookup"><span data-stu-id="20c01-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="20c01-115">数组的最后一个元素必须是`mdMethodDefNil`。</span><span class="sxs-lookup"><span data-stu-id="20c01-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20c01-116">要求</span><span class="sxs-lookup"><span data-stu-id="20c01-116">Requirements</span></span>  
 <span data-ttu-id="20c01-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20c01-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20c01-118">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="20c01-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20c01-119">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="20c01-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20c01-120">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20c01-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c01-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20c01-121">See also</span></span>

- [<span data-ttu-id="20c01-122">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="20c01-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="20c01-123">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="20c01-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
