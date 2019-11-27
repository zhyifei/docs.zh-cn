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
ms.openlocfilehash: e8b15f478eb3b94b7cdcab3b69d54e7cc99be13b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440164"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="a4671-102">IMetaDataFilter 接口</span><span class="sxs-lookup"><span data-stu-id="a4671-102">IMetaDataFilter Interface</span></span>
<span data-ttu-id="a4671-103">提供用于标记和筛选元数据标记以避免重复已进行的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="a4671-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4671-104">方法</span><span class="sxs-lookup"><span data-stu-id="a4671-104">Methods</span></span>  
  
|<span data-ttu-id="a4671-105">方法</span><span class="sxs-lookup"><span data-stu-id="a4671-105">Method</span></span>|<span data-ttu-id="a4671-106">说明</span><span class="sxs-lookup"><span data-stu-id="a4671-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4671-107">IsTokenMarked 方法</span><span class="sxs-lookup"><span data-stu-id="a4671-107">IsTokenMarked Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="a4671-108">获取一个值，该值指示是否已处理指定的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="a4671-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="a4671-109">MarkToken 方法</span><span class="sxs-lookup"><span data-stu-id="a4671-109">MarkToken Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-marktoken-method.md)|<span data-ttu-id="a4671-110">设置一个值，该值指示已处理指定的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="a4671-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="a4671-111">UnmarkAll 方法</span><span class="sxs-lookup"><span data-stu-id="a4671-111">UnmarkAll Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-unmarkall-method.md)|<span data-ttu-id="a4671-112">从当前元数据范围内的所有标记中删除处理标记。</span><span class="sxs-lookup"><span data-stu-id="a4671-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4671-113">要求</span><span class="sxs-lookup"><span data-stu-id="a4671-113">Requirements</span></span>  
 <span data-ttu-id="a4671-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4671-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4671-115">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="a4671-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4671-116">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a4671-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4671-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4671-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4671-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4671-118">See also</span></span>

- [<span data-ttu-id="a4671-119">元数据接口</span><span class="sxs-lookup"><span data-stu-id="a4671-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
