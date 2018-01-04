---
title: "IHostFilter::MarkToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostFilter.MarkToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca342e04f554d070546c6c6d82d5ad56a4dad8cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="753f6-102">IHostFilter::MarkToken 方法</span><span class="sxs-lookup"><span data-stu-id="753f6-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="753f6-103">指示将处理指定元数据标记。</span><span class="sxs-lookup"><span data-stu-id="753f6-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="753f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="753f6-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="753f6-105">参数</span><span class="sxs-lookup"><span data-stu-id="753f6-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="753f6-106">[in]要处理的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="753f6-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="753f6-107">备注</span><span class="sxs-lookup"><span data-stu-id="753f6-107">Remarks</span></span>  
 <span data-ttu-id="753f6-108">通常情况下，你想要处理如果在元数据范围内的令牌。</span><span class="sxs-lookup"><span data-stu-id="753f6-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="753f6-109">`MarkToken`方法传递给元数据引擎通过[imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="753f6-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="753f6-110">惠?</span><span class="sxs-lookup"><span data-stu-id="753f6-110">Requirements</span></span>  
 <span data-ttu-id="753f6-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="753f6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="753f6-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="753f6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="753f6-113">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="753f6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="753f6-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="753f6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="753f6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="753f6-115">See Also</span></span>  
 [<span data-ttu-id="753f6-116">元数据接口</span><span class="sxs-lookup"><span data-stu-id="753f6-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="753f6-117">IHostFilter 方法</span><span class="sxs-lookup"><span data-stu-id="753f6-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
