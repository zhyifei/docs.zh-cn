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
ms.openlocfilehash: 10f31d56a9727e99157f49038c19781f12cd9958
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440427"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="01842-102">IMetaDataFilter::IsTokenMarked 方法</span><span class="sxs-lookup"><span data-stu-id="01842-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="01842-103">获取一个值，该值指示指定的元数据标记是否已标记为已处理。</span><span class="sxs-lookup"><span data-stu-id="01842-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01842-104">语法</span><span class="sxs-lookup"><span data-stu-id="01842-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01842-105">参数</span><span class="sxs-lookup"><span data-stu-id="01842-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="01842-106">中要检查处理标记的标记。</span><span class="sxs-lookup"><span data-stu-id="01842-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="01842-107">弄如果已处理 `tk`，则为 `true` 的值;否则 `false`。</span><span class="sxs-lookup"><span data-stu-id="01842-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01842-108">要求</span><span class="sxs-lookup"><span data-stu-id="01842-108">Requirements</span></span>  
 <span data-ttu-id="01842-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="01842-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01842-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="01842-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01842-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="01842-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="01842-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01842-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01842-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01842-113">See also</span></span>

- [<span data-ttu-id="01842-114">IMetaDataFilter 接口</span><span class="sxs-lookup"><span data-stu-id="01842-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
