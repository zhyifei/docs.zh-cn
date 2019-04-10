---
title: IHostFilter::MarkToken 方法
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3214a21dda27fda01054e96400997b15d11f71b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194430"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="08a78-102">IHostFilter::MarkToken 方法</span><span class="sxs-lookup"><span data-stu-id="08a78-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="08a78-103">指示将处理指定的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="08a78-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a78-104">语法</span><span class="sxs-lookup"><span data-stu-id="08a78-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08a78-105">参数</span><span class="sxs-lookup"><span data-stu-id="08a78-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="08a78-106">[in]要处理的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="08a78-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08a78-107">备注</span><span class="sxs-lookup"><span data-stu-id="08a78-107">Remarks</span></span>  
 <span data-ttu-id="08a78-108">通常情况下，所需的令牌，如果在元数据范围内进行处理。</span><span class="sxs-lookup"><span data-stu-id="08a78-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="08a78-109">`MarkToken`方法将传递给元数据引擎通过[imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="08a78-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08a78-110">要求</span><span class="sxs-lookup"><span data-stu-id="08a78-110">Requirements</span></span>  
 <span data-ttu-id="08a78-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08a78-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08a78-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="08a78-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08a78-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="08a78-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="08a78-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="08a78-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08a78-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="08a78-115">See also</span></span>

- [<span data-ttu-id="08a78-116">元数据接口</span><span class="sxs-lookup"><span data-stu-id="08a78-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="08a78-117">IHostFilter 接口</span><span class="sxs-lookup"><span data-stu-id="08a78-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
