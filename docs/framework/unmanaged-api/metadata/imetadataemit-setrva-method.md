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
ms.openlocfilehash: 371eed84883e2816892c0a6a212a4a89a287cc58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445268"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="0c827-102">IMetaDataEmit::SetRVA 方法</span><span class="sxs-lookup"><span data-stu-id="0c827-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="0c827-103">设置指定的方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="0c827-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c827-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c827-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c827-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c827-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="0c827-106">[in]为目标方法或方法实现令牌。</span><span class="sxs-lookup"><span data-stu-id="0c827-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="0c827-107">[in]代码或数据区域的地址。</span><span class="sxs-lookup"><span data-stu-id="0c827-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c827-108">要求</span><span class="sxs-lookup"><span data-stu-id="0c827-108">Requirements</span></span>  
 <span data-ttu-id="0c827-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c827-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c827-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c827-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c827-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0c827-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c827-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c827-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c827-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c827-113">See Also</span></span>  
 [<span data-ttu-id="0c827-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="0c827-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0c827-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="0c827-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
