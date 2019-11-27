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
ms.openlocfilehash: 6966d0ad2fefd8401b19d8e8dcf7776799a066b2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432564"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="420c5-102">IMetaDataEmit::DefineEvent 方法</span><span class="sxs-lookup"><span data-stu-id="420c5-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="420c5-103">使用指定的元数据签名创建事件的定义，并获取该事件定义的标记。</span><span class="sxs-lookup"><span data-stu-id="420c5-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="420c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="420c5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="420c5-105">参数</span><span class="sxs-lookup"><span data-stu-id="420c5-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="420c5-106">中目标类或接口的标记。</span><span class="sxs-lookup"><span data-stu-id="420c5-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="420c5-107">这是 `mdTypeDef` 或 `mdTypeDefNil` 令牌。</span><span class="sxs-lookup"><span data-stu-id="420c5-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="420c5-108">中事件的名称。</span><span class="sxs-lookup"><span data-stu-id="420c5-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="420c5-109">中事件标志。</span><span class="sxs-lookup"><span data-stu-id="420c5-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="420c5-110">中事件类的标记。</span><span class="sxs-lookup"><span data-stu-id="420c5-110">[in] The token for the event class.</span></span> <span data-ttu-id="420c5-111">这是 `mdTypeDef`、`mdTypeRef`或 `mdTokenNil` 标记。</span><span class="sxs-lookup"><span data-stu-id="420c5-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="420c5-112">中用于订阅事件的方法，或为 null。</span><span class="sxs-lookup"><span data-stu-id="420c5-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="420c5-113">中用于取消订阅事件的方法，或为 null。</span><span class="sxs-lookup"><span data-stu-id="420c5-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="420c5-114">中使用的方法（由派生类）引发事件。</span><span class="sxs-lookup"><span data-stu-id="420c5-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="420c5-115">中与事件关联的其他方法的标记数组。</span><span class="sxs-lookup"><span data-stu-id="420c5-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="420c5-116">使用 `mdMethodDefNil` 标记终止数组。</span><span class="sxs-lookup"><span data-stu-id="420c5-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="420c5-117">弄分配给事件的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="420c5-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="420c5-118">要求</span><span class="sxs-lookup"><span data-stu-id="420c5-118">Requirements</span></span>  
 <span data-ttu-id="420c5-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="420c5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="420c5-120">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="420c5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="420c5-121">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="420c5-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="420c5-122">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="420c5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="420c5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="420c5-123">See also</span></span>

- [<span data-ttu-id="420c5-124">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="420c5-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="420c5-125">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="420c5-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
