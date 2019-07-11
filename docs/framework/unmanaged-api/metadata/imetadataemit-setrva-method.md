---
title: IMetaDataEmit::SetRVA 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02331bb3b0c70b946eaa28c9cd316f109ac927b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777234"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="8ec23-102">IMetaDataEmit::SetRVA 方法</span><span class="sxs-lookup"><span data-stu-id="8ec23-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="8ec23-103">设置指定的方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="8ec23-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec23-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ec23-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ec23-105">参数</span><span class="sxs-lookup"><span data-stu-id="8ec23-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="8ec23-106">[in]目标方法或方法的实现标记。</span><span class="sxs-lookup"><span data-stu-id="8ec23-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="8ec23-107">[in]在代码或数据区域的地址。</span><span class="sxs-lookup"><span data-stu-id="8ec23-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ec23-108">要求</span><span class="sxs-lookup"><span data-stu-id="8ec23-108">Requirements</span></span>  
 <span data-ttu-id="8ec23-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ec23-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ec23-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ec23-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ec23-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8ec23-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ec23-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ec23-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ec23-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ec23-113">See also</span></span>

- [<span data-ttu-id="8ec23-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="8ec23-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8ec23-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="8ec23-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
