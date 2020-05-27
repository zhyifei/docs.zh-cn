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
ms.openlocfilehash: 720133e64c02aa09c9ff7e43a20630b0d55c1acf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008750"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="be121-102">IMetaDataEmit::SetEventProps 方法</span><span class="sxs-lookup"><span data-stu-id="be121-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="be121-103">设置或更新通过之前对 IMetaDataEmit 的调用定义的事件的指定功能[：:D efineevent](imetadataemit-defineevent-method.md)。</span><span class="sxs-lookup"><span data-stu-id="be121-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be121-104">语法</span><span class="sxs-lookup"><span data-stu-id="be121-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="be121-105">参数</span><span class="sxs-lookup"><span data-stu-id="be121-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="be121-106">中事件标记。</span><span class="sxs-lookup"><span data-stu-id="be121-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="be121-107">中事件标志。</span><span class="sxs-lookup"><span data-stu-id="be121-107">[in] Event flags.</span></span> <span data-ttu-id="be121-108">这是一个值的位掩码 `CorEventAttr` 。</span><span class="sxs-lookup"><span data-stu-id="be121-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="be121-109">中事件类的标记。</span><span class="sxs-lookup"><span data-stu-id="be121-109">[in] The token for the event class.</span></span> <span data-ttu-id="be121-110">这是 `mdTypeDef` 或 `mdTypeRef` 令牌。</span><span class="sxs-lookup"><span data-stu-id="be121-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="be121-111">中用于订阅事件的方法，或为 null。</span><span class="sxs-lookup"><span data-stu-id="be121-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="be121-112">中用于取消订阅事件的方法，或为 null。</span><span class="sxs-lookup"><span data-stu-id="be121-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="be121-113">中使用的方法（由派生类）引发事件。</span><span class="sxs-lookup"><span data-stu-id="be121-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="be121-114">中与事件关联的其他方法的标记数组。</span><span class="sxs-lookup"><span data-stu-id="be121-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="be121-115">数组的最后一个元素必须是 `mdMethodDefNil` 。</span><span class="sxs-lookup"><span data-stu-id="be121-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be121-116">要求</span><span class="sxs-lookup"><span data-stu-id="be121-116">Requirements</span></span>  
 <span data-ttu-id="be121-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="be121-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be121-118">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="be121-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be121-119">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="be121-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be121-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be121-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be121-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be121-121">See also</span></span>

- [<span data-ttu-id="be121-122">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="be121-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="be121-123">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="be121-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
