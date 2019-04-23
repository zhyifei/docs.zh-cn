---
title: IMetaDataFilter::IsTokenMarked 方法
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6969f2c1df9b5b04122ed6aef550697171123cf5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229012"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="efa5b-102">IMetaDataFilter::IsTokenMarked 方法</span><span class="sxs-lookup"><span data-stu-id="efa5b-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="efa5b-103">获取一个值，该值指示指定的元数据令牌是否已标记为已处理。</span><span class="sxs-lookup"><span data-stu-id="efa5b-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="efa5b-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efa5b-105">参数</span><span class="sxs-lookup"><span data-stu-id="efa5b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="efa5b-106">[in]要检查其处理标记的标记。</span><span class="sxs-lookup"><span data-stu-id="efa5b-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="efa5b-107">[out]一个值，则该值`true`如果`tk`处理; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="efa5b-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efa5b-108">要求</span><span class="sxs-lookup"><span data-stu-id="efa5b-108">Requirements</span></span>  
 <span data-ttu-id="efa5b-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efa5b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa5b-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="efa5b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efa5b-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="efa5b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="efa5b-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efa5b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa5b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="efa5b-113">See also</span></span>

- [<span data-ttu-id="efa5b-114">IMetaDataFilter 接口</span><span class="sxs-lookup"><span data-stu-id="efa5b-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
