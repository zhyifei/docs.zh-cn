---
title: IMetaDataFilter::MarkToken 方法
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fdd50f0de014aa68b14303e9e22924b0790fa55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085111"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="840ab-102">IMetaDataFilter::MarkToken 方法</span><span class="sxs-lookup"><span data-stu-id="840ab-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="840ab-103">设置一个值，该值指定元数据标记已处理。</span><span class="sxs-lookup"><span data-stu-id="840ab-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="840ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="840ab-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="840ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="840ab-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="840ab-106">[in]要将标记为已处理的标记。</span><span class="sxs-lookup"><span data-stu-id="840ab-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="840ab-107">要求</span><span class="sxs-lookup"><span data-stu-id="840ab-107">Requirements</span></span>  
 <span data-ttu-id="840ab-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="840ab-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="840ab-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="840ab-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="840ab-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="840ab-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="840ab-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="840ab-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="840ab-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="840ab-112">See also</span></span>

- [<span data-ttu-id="840ab-113">IMetaDataFilter 接口</span><span class="sxs-lookup"><span data-stu-id="840ab-113">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
