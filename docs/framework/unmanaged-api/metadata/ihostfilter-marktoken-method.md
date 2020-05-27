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
ms.openlocfilehash: 11529ce896f265f2b200fa6e511d4b913e9147c8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008217"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="9aac5-102">IHostFilter::MarkToken 方法</span><span class="sxs-lookup"><span data-stu-id="9aac5-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="9aac5-103">指示将处理指定的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="9aac5-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aac5-104">语法</span><span class="sxs-lookup"><span data-stu-id="9aac5-104">Syntax</span></span>  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aac5-105">参数</span><span class="sxs-lookup"><span data-stu-id="9aac5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9aac5-106">中要处理的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="9aac5-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9aac5-107">备注</span><span class="sxs-lookup"><span data-stu-id="9aac5-107">Remarks</span></span>  
 <span data-ttu-id="9aac5-108">通常，如果令牌在元数据范围内，则需要对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="9aac5-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="9aac5-109">`MarkToken`方法通过[IMetaDataEmit：： SetHandler](imetadataemit-sethandler-method.md)方法传递给元数据引擎。</span><span class="sxs-lookup"><span data-stu-id="9aac5-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aac5-110">要求</span><span class="sxs-lookup"><span data-stu-id="9aac5-110">Requirements</span></span>  
 <span data-ttu-id="9aac5-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9aac5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aac5-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="9aac5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9aac5-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9aac5-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9aac5-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aac5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aac5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9aac5-115">See also</span></span>

- [<span data-ttu-id="9aac5-116">元数据接口</span><span class="sxs-lookup"><span data-stu-id="9aac5-116">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="9aac5-117">IHostFilter 接口</span><span class="sxs-lookup"><span data-stu-id="9aac5-117">IHostFilter Interface</span></span>](ihostfilter-interface.md)
