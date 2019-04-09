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
ms.openlocfilehash: 48055103b49b4c61bb7561f2d4aa6c8daae07ae2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128903"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="2f2aa-102">IMetaDataEmit::DefineEvent 方法</span><span class="sxs-lookup"><span data-stu-id="2f2aa-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="2f2aa-103">使用指定的元数据签名中，创建一个事件的定义并获取该事件定义的标记。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f2aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="2f2aa-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2f2aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="2f2aa-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2f2aa-106">[in]目标类或接口的标记。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="2f2aa-107">这可以是`mdTypeDef`或`mdTypeDefNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="2f2aa-108">[in]事件的名称。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="2f2aa-109">[in]事件的标志。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="2f2aa-110">[in]事件类标记。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-110">[in] The token for the event class.</span></span> <span data-ttu-id="2f2aa-111">这是`mdTypeDef`、 一个`mdTypeRef`，或`mdTokenNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="2f2aa-112">[in]用来订阅事件或为 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="2f2aa-113">[in]用于取消订阅事件，则为 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="2f2aa-114">[in]（由派生类） 用于引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="2f2aa-115">[in]有关其他方法与事件关联的标记的数组。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="2f2aa-116">数组结尾`mdMethodDefNil`令牌。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="2f2aa-117">[out]分配到的事件的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f2aa-118">要求</span><span class="sxs-lookup"><span data-stu-id="2f2aa-118">Requirements</span></span>  
 <span data-ttu-id="2f2aa-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2f2aa-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f2aa-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f2aa-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f2aa-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2f2aa-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2f2aa-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2f2aa-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f2aa-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f2aa-123">See also</span></span>

- [<span data-ttu-id="2f2aa-124">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="2f2aa-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2f2aa-125">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="2f2aa-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
