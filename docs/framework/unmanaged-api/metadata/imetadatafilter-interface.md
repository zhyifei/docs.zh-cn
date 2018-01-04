---
title: "IMetaDataFilter 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataFilter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataFilter
helpviewer_keywords: IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0918802a146940fb7579279e56f752bd114c746c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="1ceef-102">IMetaDataFilter 接口</span><span class="sxs-lookup"><span data-stu-id="1ceef-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="1ceef-103">提供用于标记和筛选元数据标记以避免重复已进行的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="1ceef-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ceef-104">方法</span><span class="sxs-lookup"><span data-stu-id="1ceef-104">Methods</span></span>  
  
|<span data-ttu-id="1ceef-105">方法</span><span class="sxs-lookup"><span data-stu-id="1ceef-105">Method</span></span>|<span data-ttu-id="1ceef-106">描述</span><span class="sxs-lookup"><span data-stu-id="1ceef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ceef-107">IsTokenMarked 方法</span><span class="sxs-lookup"><span data-stu-id="1ceef-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="1ceef-108">获取一个值，该值指示是否已处理的指定元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1ceef-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="1ceef-109">MarkToken 方法</span><span class="sxs-lookup"><span data-stu-id="1ceef-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="1ceef-110">设置一个值，该值指定元数据标记已被处理。</span><span class="sxs-lookup"><span data-stu-id="1ceef-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="1ceef-111">UnmarkAll 方法</span><span class="sxs-lookup"><span data-stu-id="1ceef-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="1ceef-112">从当前的元数据范围内的所有令牌中移除处理标记。</span><span class="sxs-lookup"><span data-stu-id="1ceef-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ceef-113">惠?</span><span class="sxs-lookup"><span data-stu-id="1ceef-113">Requirements</span></span>  
 <span data-ttu-id="1ceef-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ceef-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ceef-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1ceef-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ceef-116">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1ceef-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ceef-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ceef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ceef-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ceef-118">See Also</span></span>  
 [<span data-ttu-id="1ceef-119">元数据接口</span><span class="sxs-lookup"><span data-stu-id="1ceef-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
