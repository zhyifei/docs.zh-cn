---
title: IMetaDataEmit::DefineEvent 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 26fd4c89838912e4e07c1d9a8b84aa22f54adeff
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501625"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="6d06e-102">IMetaDataEmit::DefineEvent 方法</span><span class="sxs-lookup"><span data-stu-id="6d06e-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="6d06e-103">使用指定的元数据签名中，创建一个事件的定义并获取该事件定义的标记。</span><span class="sxs-lookup"><span data-stu-id="6d06e-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d06e-104">语法</span><span class="sxs-lookup"><span data-stu-id="6d06e-104">Syntax</span></span>  
  
```  
HRESULT DefineEvent (   
    [in]  mdTypeDef    td,   
    [in]  LPCWSTR      szEvent,   
    [in]  DWORD        dwEventFlags,   
    [in]  mdToken      tkEventType,   
    [in]  mdMethodDef  mdAddOn,   
    [in]  mdMethodDef  mdRemoveOn,   
    [in]  mdMethodDef  mdFire,   
    [in]  mdMethodDef  rmdOtherMethods[],   
    [out] mdEvent      *pmdEvent   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d06e-105">参数</span><span class="sxs-lookup"><span data-stu-id="6d06e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6d06e-106">[in]目标类或接口的标记。</span><span class="sxs-lookup"><span data-stu-id="6d06e-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="6d06e-107">这可以是`mdTypeDef`或`mdTypeDefNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="6d06e-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="6d06e-108">[in]事件的名称。</span><span class="sxs-lookup"><span data-stu-id="6d06e-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="6d06e-109">[in]事件的标志。</span><span class="sxs-lookup"><span data-stu-id="6d06e-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="6d06e-110">[in]事件类标记。</span><span class="sxs-lookup"><span data-stu-id="6d06e-110">[in] The token for the event class.</span></span> <span data-ttu-id="6d06e-111">这是`mdTypeDef`、 一个`mdTypeRef`，或`mdTokenNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="6d06e-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="6d06e-112">[in]用来订阅事件或为 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="6d06e-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="6d06e-113">[in]用于取消订阅事件，则为 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="6d06e-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="6d06e-114">[in]（由派生类） 用于引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="6d06e-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="6d06e-115">[in]有关其他方法与事件关联的标记的数组。</span><span class="sxs-lookup"><span data-stu-id="6d06e-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="6d06e-116">数组结尾`mdMethodDefNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="6d06e-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="6d06e-117">[out]分配到的事件的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="6d06e-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d06e-118">要求</span><span class="sxs-lookup"><span data-stu-id="6d06e-118">Requirements</span></span>  
 <span data-ttu-id="6d06e-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6d06e-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d06e-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d06e-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d06e-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6d06e-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6d06e-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d06e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d06e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d06e-123">See also</span></span>
- [<span data-ttu-id="6d06e-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="6d06e-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6d06e-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="6d06e-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
