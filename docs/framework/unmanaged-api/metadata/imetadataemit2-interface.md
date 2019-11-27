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
# <a name="imetadataemit2-interface"></a><span data-ttu-id="f10df-102">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="f10df-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="f10df-103">扩展[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口，主要用于提供使用泛型类型的能力。</span><span class="sxs-lookup"><span data-stu-id="f10df-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f10df-104">方法</span><span class="sxs-lookup"><span data-stu-id="f10df-104">Methods</span></span>  
  
|<span data-ttu-id="f10df-105">方法</span><span class="sxs-lookup"><span data-stu-id="f10df-105">Method</span></span>|<span data-ttu-id="f10df-106">说明</span><span class="sxs-lookup"><span data-stu-id="f10df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f10df-107">DefineGenericParam 方法</span><span class="sxs-lookup"><span data-stu-id="f10df-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="f10df-108">创建泛型类型参数的定义，并获取该泛型类型参数的令牌。</span><span class="sxs-lookup"><span data-stu-id="f10df-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="f10df-109">DefineMethodSpec 方法</span><span class="sxs-lookup"><span data-stu-id="f10df-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="f10df-110">创建方法的泛型实例，并获取定义的标记。</span><span class="sxs-lookup"><span data-stu-id="f10df-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="f10df-111">GetDeltaSaveSize 方法</span><span class="sxs-lookup"><span data-stu-id="f10df-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="f10df-112">获取一个值，该值指示为当前的 "编辑并继续" 会话表示更改所需的数据的大小差异。</span><span class="sxs-lookup"><span data-stu-id="f10df-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="f10df-113">ResetENCLog 方法</span><span class="sxs-lookup"><span data-stu-id="f10df-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="f10df-114">重置编辑并继续日志并启动新的会话。</span><span class="sxs-lookup"><span data-stu-id="f10df-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="f10df-115">SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="f10df-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="f10df-116">将当前的 "编辑并继续" 会话中的更改保存到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="f10df-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="f10df-117">SaveDeltaToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="f10df-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="f10df-118">将当前的 "编辑并继续" 会话中的更改保存到内存。</span><span class="sxs-lookup"><span data-stu-id="f10df-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="f10df-119">SaveDeltaToStream 方法</span><span class="sxs-lookup"><span data-stu-id="f10df-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="f10df-120">将当前的 "编辑并继续" 会话中的更改保存到指定的流。</span><span class="sxs-lookup"><span data-stu-id="f10df-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="f10df-121">SetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="f10df-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="f10df-122">设置指定的标记所引用的泛型参数定义的属性值。</span><span class="sxs-lookup"><span data-stu-id="f10df-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f10df-123">要求</span><span class="sxs-lookup"><span data-stu-id="f10df-123">Requirements</span></span>  
 <span data-ttu-id="f10df-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f10df-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f10df-125">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f10df-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f10df-126">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f10df-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f10df-127">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f10df-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10df-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f10df-128">See also</span></span>

- [<span data-ttu-id="f10df-129">元数据接口</span><span class="sxs-lookup"><span data-stu-id="f10df-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="f10df-130">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f10df-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
