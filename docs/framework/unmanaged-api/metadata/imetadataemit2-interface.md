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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 87b5b60d75d5d28e100ec75192d0cacf51765927
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042961"
---
# <a name="imetadataemit2-interface"></a><span data-ttu-id="98633-102">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="98633-102">IMetaDataEmit2 Interface</span></span>
<span data-ttu-id="98633-103">扩展了[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口主要用于提供使用泛型类型的功能。</span><span class="sxs-lookup"><span data-stu-id="98633-103">Extends the [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface primarily to provide the ability to work with generic types.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98633-104">方法</span><span class="sxs-lookup"><span data-stu-id="98633-104">Methods</span></span>  
  
|<span data-ttu-id="98633-105">方法</span><span class="sxs-lookup"><span data-stu-id="98633-105">Method</span></span>|<span data-ttu-id="98633-106">描述</span><span class="sxs-lookup"><span data-stu-id="98633-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98633-107">DefineGenericParam 方法</span><span class="sxs-lookup"><span data-stu-id="98633-107">DefineGenericParam Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|<span data-ttu-id="98633-108">创建泛型类型参数的定义并获取该泛型类型参数的令牌。</span><span class="sxs-lookup"><span data-stu-id="98633-108">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>|  
|[<span data-ttu-id="98633-109">DefineMethodSpec 方法</span><span class="sxs-lookup"><span data-stu-id="98633-109">DefineMethodSpec Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|<span data-ttu-id="98633-110">创建一个方法的泛型实例并获取定义的标记。</span><span class="sxs-lookup"><span data-stu-id="98633-110">Creates a generic instance of a method, and gets a token to the definition.</span></span>|  
|[<span data-ttu-id="98633-111">GetDeltaSaveSize 方法</span><span class="sxs-lookup"><span data-stu-id="98633-111">GetDeltaSaveSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|<span data-ttu-id="98633-112">获取一个值，该值指示当前的编辑并继续会话 express 所做的更改所需的数据大小中的差异。</span><span class="sxs-lookup"><span data-stu-id="98633-112">Gets a value indicating the difference in size of the data that is required to express the changes for the current edit-and-continue session.</span></span>|  
|[<span data-ttu-id="98633-113">ResetENCLog 方法</span><span class="sxs-lookup"><span data-stu-id="98633-113">ResetENCLog Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|<span data-ttu-id="98633-114">重置编辑并继续日志并启动新会话。</span><span class="sxs-lookup"><span data-stu-id="98633-114">Resets the edit-and-continue log and starts a new session.</span></span>|  
|[<span data-ttu-id="98633-115">SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="98633-115">SaveDelta Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|<span data-ttu-id="98633-116">将更改从当前会话中编辑和继续保存到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="98633-116">Saves changes from the current edit-and-continue session to the specified file.</span></span>|  
|[<span data-ttu-id="98633-117">SaveDeltaToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="98633-117">SaveDeltaToMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|<span data-ttu-id="98633-118">将更改从当前会话中编辑和继续保存到内存中。</span><span class="sxs-lookup"><span data-stu-id="98633-118">Saves changes from the current edit-and-continue session to memory.</span></span>|  
|[<span data-ttu-id="98633-119">SaveDeltaToStream 方法</span><span class="sxs-lookup"><span data-stu-id="98633-119">SaveDeltaToStream Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|<span data-ttu-id="98633-120">将更改从当前会话中编辑和继续保存到指定的流。</span><span class="sxs-lookup"><span data-stu-id="98633-120">Saves changes from the current edit-and-continue session to the specified stream.</span></span>|  
|[<span data-ttu-id="98633-121">SetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="98633-121">SetGenericParamProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|<span data-ttu-id="98633-122">设置指定标记所引用的泛型参数定义的属性值。</span><span class="sxs-lookup"><span data-stu-id="98633-122">Sets property values for the generic parameter definition referenced by the specified token.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98633-123">要求</span><span class="sxs-lookup"><span data-stu-id="98633-123">Requirements</span></span>  
 <span data-ttu-id="98633-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98633-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98633-125">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="98633-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98633-126">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="98633-126">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98633-127">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98633-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98633-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="98633-128">See also</span></span>

- [<span data-ttu-id="98633-129">元数据接口</span><span class="sxs-lookup"><span data-stu-id="98633-129">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="98633-130">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="98633-130">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
