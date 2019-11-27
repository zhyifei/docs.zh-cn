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
ms.openlocfilehash: 506e13ad956a01b16e36d8c71737fe0efce4c01b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450317"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="f10c1-102">IMetaDataEmit::SetEventProps 方法</span><span class="sxs-lookup"><span data-stu-id="f10c1-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="f10c1-103">设置或更新通过之前对 IMetaDataEmit 的调用定义的事件的指定功能[：:D efineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)。</span><span class="sxs-lookup"><span data-stu-id="f10c1-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="f10c1-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f10c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="f10c1-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="f10c1-106">中事件标记。</span><span class="sxs-lookup"><span data-stu-id="f10c1-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="f10c1-107">中事件标志。</span><span class="sxs-lookup"><span data-stu-id="f10c1-107">[in] Event flags.</span></span> <span data-ttu-id="f10c1-108">这是 `CorEventAttr` 值的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f10c1-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="f10c1-109">中事件类的标记。</span><span class="sxs-lookup"><span data-stu-id="f10c1-109">[in] The token for the event class.</span></span> <span data-ttu-id="f10c1-110">这是 `mdTypeDef` 或 `mdTypeRef` 令牌。</span><span class="sxs-lookup"><span data-stu-id="f10c1-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="f10c1-111">中用于订阅事件的方法，或为 null。</span><span class="sxs-lookup"><span data-stu-id="f10c1-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="f10c1-112">中用于取消订阅事件的方法，或为 null。</span><span class="sxs-lookup"><span data-stu-id="f10c1-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="f10c1-113">中使用的方法（由派生类）引发事件。</span><span class="sxs-lookup"><span data-stu-id="f10c1-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="f10c1-114">中与事件关联的其他方法的标记数组。</span><span class="sxs-lookup"><span data-stu-id="f10c1-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="f10c1-115">数组的最后一个元素必须是 `mdMethodDefNil`。</span><span class="sxs-lookup"><span data-stu-id="f10c1-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f10c1-116">要求</span><span class="sxs-lookup"><span data-stu-id="f10c1-116">Requirements</span></span>  
 <span data-ttu-id="f10c1-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f10c1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f10c1-118">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f10c1-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f10c1-119">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f10c1-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f10c1-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f10c1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10c1-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f10c1-121">See also</span></span>

- [<span data-ttu-id="f10c1-122">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f10c1-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f10c1-123">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f10c1-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
