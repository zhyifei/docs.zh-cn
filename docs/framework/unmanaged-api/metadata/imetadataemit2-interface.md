---
title: IMetaDataEmit2 接口
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
ms.openlocfilehash: 7ceae6f7713ab0eb1feff550838325df0ea52de2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447912"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="4364d-102">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="4364d-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="4364d-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span><span class="sxs-lookup"><span data-stu-id="4364d-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4364d-104">方法</span><span class="sxs-lookup"><span data-stu-id="4364d-104">Methods</span></span>  
  
|<span data-ttu-id="4364d-105">方法</span><span class="sxs-lookup"><span data-stu-id="4364d-105">Method</span></span>|<span data-ttu-id="4364d-106">描述</span><span class="sxs-lookup"><span data-stu-id="4364d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4364d-107">DefineGenericParam 方法</span><span class="sxs-lookup"><span data-stu-id="4364d-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="4364d-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span><span class="sxs-lookup"><span data-stu-id="4364d-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="4364d-109">DefineMethodSpec 方法</span><span class="sxs-lookup"><span data-stu-id="4364d-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="4364d-110">Creates a generic instance of a method, and gets a token to the definition.</span><span class="sxs-lookup"><span data-stu-id="4364d-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="4364d-111">GetDeltaSaveSize 方法</span><span class="sxs-lookup"><span data-stu-id="4364d-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="4364d-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span><span class="sxs-lookup"><span data-stu-id="4364d-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="4364d-113">ResetENCLog 方法</span><span class="sxs-lookup"><span data-stu-id="4364d-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="4364d-114">Resets the edit-and-continue log and starts a new session.</span><span class="sxs-lookup"><span data-stu-id="4364d-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="4364d-115">SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="4364d-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="4364d-116">Saves changes from the current edit-and-continue session to the specified file.</span><span class="sxs-lookup"><span data-stu-id="4364d-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="4364d-117">SaveDeltaToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="4364d-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="4364d-118">Saves changes from the current edit-and-continue session to memory.</span><span class="sxs-lookup"><span data-stu-id="4364d-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="4364d-119">SaveDeltaToStream 方法</span><span class="sxs-lookup"><span data-stu-id="4364d-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="4364d-120">Saves changes from the current edit-and-continue session to the specified stream.</span><span class="sxs-lookup"><span data-stu-id="4364d-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="4364d-121">SetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="4364d-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="4364d-122">Sets property values for the generic parameter definition referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="4364d-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4364d-123">要求</span><span class="sxs-lookup"><span data-stu-id="4364d-123">Requirements</span></span>  
 <span data-ttu-id="4364d-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4364d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4364d-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4364d-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4364d-126">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4364d-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4364d-127">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4364d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4364d-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="4364d-128">See also</span></span>

- [<span data-ttu-id="4364d-129">元数据接口</span><span class="sxs-lookup"><span data-stu-id="4364d-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="4364d-130">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="4364d-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
