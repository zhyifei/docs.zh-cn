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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abfa8a3f58d3e9f7c80762c1faf2bc51514d71b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113810"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="05203-102">IMetaDataEmit::SetEventProps 方法</span><span class="sxs-lookup"><span data-stu-id="05203-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="05203-103">设置或更新的定义通过以前调用的事件指定的功能[imetadataemit:: Defineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)。</span><span class="sxs-lookup"><span data-stu-id="05203-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05203-104">语法</span><span class="sxs-lookup"><span data-stu-id="05203-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="05203-105">参数</span><span class="sxs-lookup"><span data-stu-id="05203-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="05203-106">[in]事件标记中。</span><span class="sxs-lookup"><span data-stu-id="05203-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="05203-107">[in]事件的标志。</span><span class="sxs-lookup"><span data-stu-id="05203-107">[in] Event flags.</span></span> <span data-ttu-id="05203-108">这是一个位掩码的`CorEventAttr`值。</span><span class="sxs-lookup"><span data-stu-id="05203-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="05203-109">[in]事件类标记。</span><span class="sxs-lookup"><span data-stu-id="05203-109">[in] The token for the event class.</span></span> <span data-ttu-id="05203-110">这可以是`mdTypeDef`或`mdTypeRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="05203-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="05203-111">[in]用来订阅事件或为 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="05203-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="05203-112">[in]用于取消订阅事件，则为 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="05203-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="05203-113">[in]（由派生类） 用于引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="05203-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="05203-114">[in]有关其他方法与事件关联的标记的数组。</span><span class="sxs-lookup"><span data-stu-id="05203-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="05203-115">数组的最后一个元素必须是`mdMethodDefNil`。</span><span class="sxs-lookup"><span data-stu-id="05203-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05203-116">要求</span><span class="sxs-lookup"><span data-stu-id="05203-116">Requirements</span></span>  
 <span data-ttu-id="05203-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05203-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05203-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="05203-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05203-119">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="05203-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05203-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05203-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05203-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="05203-121">See also</span></span>

- [<span data-ttu-id="05203-122">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="05203-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="05203-123">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="05203-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
