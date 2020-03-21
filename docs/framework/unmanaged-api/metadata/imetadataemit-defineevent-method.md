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
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175845"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="6dfa3-102">IMetaDataEmit::DefineEvent 方法</span><span class="sxs-lookup"><span data-stu-id="6dfa3-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="6dfa3-103">为具有指定元数据签名的事件创建定义，并获取该事件定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dfa3-104">语法</span><span class="sxs-lookup"><span data-stu-id="6dfa3-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="6dfa3-105">parameters</span><span class="sxs-lookup"><span data-stu-id="6dfa3-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6dfa3-106">[在]目标类或接口的令牌。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="6dfa3-107">这是 或`mdTypeDef``mdTypeDefNil`标记。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="6dfa3-108">[在]事件的名称。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="6dfa3-109">[在]事件标志。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="6dfa3-110">[在]事件类的令牌。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-110">[in] The token for the event class.</span></span> <span data-ttu-id="6dfa3-111">这是 一`mdTypeDef`个`mdTypeRef`、或`mdTokenNil`标记。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="6dfa3-112">[在]用于订阅事件或 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="6dfa3-113">[在]用于取消订阅事件或 null 的方法。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="6dfa3-114">[在]用于（由派生类）引发事件的方法。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="6dfa3-115">[在]与事件关联的其他方法的令牌数组。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="6dfa3-116">数组用`mdMethodDefNil`令牌终止。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="6dfa3-117">[出]分配给事件的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dfa3-118">要求</span><span class="sxs-lookup"><span data-stu-id="6dfa3-118">Requirements</span></span>  
 <span data-ttu-id="6dfa3-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6dfa3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dfa3-120">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="6dfa3-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6dfa3-121">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6dfa3-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dfa3-122">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dfa3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dfa3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dfa3-123">See also</span></span>

- [<span data-ttu-id="6dfa3-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="6dfa3-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6dfa3-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="6dfa3-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
