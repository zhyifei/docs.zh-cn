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
ms.openlocfilehash: 47377e892aaf2bdd96a297630c47fe52215b0564
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177384"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="9de63-102">IMetaDataFilter::IsTokenMarked 方法</span><span class="sxs-lookup"><span data-stu-id="9de63-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="9de63-103">获取指示指定元数据令牌是否已标记为已处理的值。</span><span class="sxs-lookup"><span data-stu-id="9de63-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9de63-104">语法</span><span class="sxs-lookup"><span data-stu-id="9de63-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9de63-105">parameters</span><span class="sxs-lookup"><span data-stu-id="9de63-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9de63-106">[在]要检查处理标记的令牌。</span><span class="sxs-lookup"><span data-stu-id="9de63-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="9de63-107">[出]`true`已处理的值`tk`;如果已处理，则为否则`false`。</span><span class="sxs-lookup"><span data-stu-id="9de63-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9de63-108">要求</span><span class="sxs-lookup"><span data-stu-id="9de63-108">Requirements</span></span>  
 <span data-ttu-id="9de63-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9de63-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9de63-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="9de63-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9de63-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9de63-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9de63-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9de63-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de63-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9de63-113">See also</span></span>

- [<span data-ttu-id="9de63-114">IMetaDataFilter 接口</span><span class="sxs-lookup"><span data-stu-id="9de63-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
