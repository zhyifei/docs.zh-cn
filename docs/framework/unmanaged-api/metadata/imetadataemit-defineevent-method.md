---
title: "IMetaDataEmit::DefineEvent 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf790ce270565abaf1d91e54c9e3569a50ab3435
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="1eb18-102">IMetaDataEmit::DefineEvent 方法</span><span class="sxs-lookup"><span data-stu-id="1eb18-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="1eb18-103">使用指定的元数据签名中，创建事件的定义并获取该事件定义的标记。</span><span class="sxs-lookup"><span data-stu-id="1eb18-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb18-104">语法</span><span class="sxs-lookup"><span data-stu-id="1eb18-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="1eb18-105">参数</span><span class="sxs-lookup"><span data-stu-id="1eb18-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1eb18-106">[in]为目标类或接口标记。</span><span class="sxs-lookup"><span data-stu-id="1eb18-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="1eb18-107">这可以是`mdTypeDef`或`mdTypeDefNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="1eb18-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="1eb18-108">[in]事件的名称。</span><span class="sxs-lookup"><span data-stu-id="1eb18-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="1eb18-109">[in]事件的标志。</span><span class="sxs-lookup"><span data-stu-id="1eb18-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="1eb18-110">[in]Event 类令牌。</span><span class="sxs-lookup"><span data-stu-id="1eb18-110">[in] The token for the event class.</span></span> <span data-ttu-id="1eb18-111">这是`mdTypeDef`、 `mdTypeRef`，或`mdTokenNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="1eb18-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="1eb18-112">[in]用于订阅的事件或为 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="1eb18-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="1eb18-113">[in]用于取消订阅事件，或者为 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="1eb18-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="1eb18-114">[in]（由派生类） 中用于引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="1eb18-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="1eb18-115">[in]有关其他方法与事件关联的令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="1eb18-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="1eb18-116">数组终止于`mdMethodDefNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="1eb18-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="1eb18-117">[out]分配给事件元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1eb18-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eb18-118">要求</span><span class="sxs-lookup"><span data-stu-id="1eb18-118">Requirements</span></span>  
 <span data-ttu-id="1eb18-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1eb18-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eb18-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1eb18-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1eb18-121">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1eb18-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1eb18-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eb18-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb18-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1eb18-123">See Also</span></span>  
 [<span data-ttu-id="1eb18-124">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="1eb18-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="1eb18-125">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="1eb18-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
