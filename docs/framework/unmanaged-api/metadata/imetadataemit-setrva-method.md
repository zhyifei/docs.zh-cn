---
title: "IMetaDataEmit::SetRVA 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetRVA
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a9ea1fe9afdb16f956ff8a0019a9bb607aa87f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="a0a40-102">IMetaDataEmit::SetRVA 方法</span><span class="sxs-lookup"><span data-stu-id="a0a40-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="a0a40-103">设置指定的方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="a0a40-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0a40-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0a40-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0a40-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0a40-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="a0a40-106">[in]为目标方法或方法实现令牌。</span><span class="sxs-lookup"><span data-stu-id="a0a40-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="a0a40-107">[in]代码或数据区域的地址。</span><span class="sxs-lookup"><span data-stu-id="a0a40-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0a40-108">惠?</span><span class="sxs-lookup"><span data-stu-id="a0a40-108">Requirements</span></span>  
 <span data-ttu-id="a0a40-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0a40-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0a40-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0a40-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0a40-111">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a0a40-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0a40-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0a40-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a40-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0a40-113">See Also</span></span>  
 [<span data-ttu-id="a0a40-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="a0a40-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a0a40-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="a0a40-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
