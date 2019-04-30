---
title: IMetaDataFilter 接口
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4196ff2cb2d4ebc401076f603a8a7fdc9b9c76ea
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049955"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="53695-102">IMetaDataFilter 接口</span><span class="sxs-lookup"><span data-stu-id="53695-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="53695-103">提供用于标记和筛选元数据标记以避免重复已进行的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="53695-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53695-104">方法</span><span class="sxs-lookup"><span data-stu-id="53695-104">Methods</span></span>  
  
|<span data-ttu-id="53695-105">方法</span><span class="sxs-lookup"><span data-stu-id="53695-105">Method</span></span>|<span data-ttu-id="53695-106">描述</span><span class="sxs-lookup"><span data-stu-id="53695-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53695-107">IsTokenMarked 方法</span><span class="sxs-lookup"><span data-stu-id="53695-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="53695-108">获取一个值，该值指示是否已处理的指定元数据标记。</span><span class="sxs-lookup"><span data-stu-id="53695-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="53695-109">MarkToken 方法</span><span class="sxs-lookup"><span data-stu-id="53695-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="53695-110">设置一个值，该值指定元数据标记已处理。</span><span class="sxs-lookup"><span data-stu-id="53695-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="53695-111">UnmarkAll 方法</span><span class="sxs-lookup"><span data-stu-id="53695-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="53695-112">从当前的元数据范围内的所有令牌中删除处理标记。</span><span class="sxs-lookup"><span data-stu-id="53695-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53695-113">要求</span><span class="sxs-lookup"><span data-stu-id="53695-113">Requirements</span></span>  
 <span data-ttu-id="53695-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53695-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53695-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="53695-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53695-116">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="53695-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="53695-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53695-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53695-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="53695-118">See also</span></span>

- [<span data-ttu-id="53695-119">元数据接口</span><span class="sxs-lookup"><span data-stu-id="53695-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
