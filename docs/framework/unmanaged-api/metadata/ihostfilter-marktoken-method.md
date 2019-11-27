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
ms.openlocfilehash: 6f8df824ed36b7793d5f07e5b5cf51f65f9c8e24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432244"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="ab4a5-102">IHostFilter::MarkToken 方法</span><span class="sxs-lookup"><span data-stu-id="ab4a5-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="ab4a5-103">指示将处理指定的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="ab4a5-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab4a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab4a5-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab4a5-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab4a5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ab4a5-106">中要处理的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="ab4a5-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab4a5-107">备注</span><span class="sxs-lookup"><span data-stu-id="ab4a5-107">Remarks</span></span>  
 <span data-ttu-id="ab4a5-108">通常，如果令牌在元数据范围内，则需要对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="ab4a5-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="ab4a5-109">通过[IMetaDataEmit：： SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)方法将 `MarkToken` 方法传递给元数据引擎。</span><span class="sxs-lookup"><span data-stu-id="ab4a5-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab4a5-110">要求</span><span class="sxs-lookup"><span data-stu-id="ab4a5-110">Requirements</span></span>  
 <span data-ttu-id="ab4a5-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4a5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab4a5-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ab4a5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab4a5-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ab4a5-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab4a5-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab4a5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab4a5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab4a5-115">See also</span></span>

- [<span data-ttu-id="ab4a5-116">元数据接口</span><span class="sxs-lookup"><span data-stu-id="ab4a5-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="ab4a5-117">IHostFilter 方法</span><span class="sxs-lookup"><span data-stu-id="ab4a5-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
