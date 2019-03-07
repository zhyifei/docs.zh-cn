---
title: IMetaDataEmit::DefineSecurityAttributeSet 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineSecurityAttributeSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet
helpviewer_keywords:
- IMetaDataEmit::DefineSecurityAttributeSet method [.NET Framework metadata]
- DefineSecurityAttributeSet method [.NET Framework metadata]
ms.assetid: 27064ca2-4186-4433-90a7-3b297785e891
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43009a81298fa5414df94e0664306859f0c9b851
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478734"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="1bac8-102">IMetaDataEmit::DefineSecurityAttributeSet 方法</span><span class="sxs-lookup"><span data-stu-id="1bac8-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="1bac8-103">创建一组安全权限才能将附加到指定的标记所引用的对象。</span><span class="sxs-lookup"><span data-stu-id="1bac8-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bac8-104">语法</span><span class="sxs-lookup"><span data-stu-id="1bac8-104">Syntax</span></span>  
  
```  
HRESULT DefineSecurityAttributeSet (   
    [in]  mdToken       tkObj,   
    [in]  COR_SECATTR   rSecAttrs[],   
    [in]  ULONG         cSecAttrs,   
    [out] ULONG         *pulErrorAttr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bac8-105">参数</span><span class="sxs-lookup"><span data-stu-id="1bac8-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="1bac8-106">[in]向其附加的安全信息的令牌。</span><span class="sxs-lookup"><span data-stu-id="1bac8-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="1bac8-107">[in]一个数组`COR_SECATTR`结构。</span><span class="sxs-lookup"><span data-stu-id="1bac8-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="1bac8-108">[in]中的元素数`rSecAttrs`。</span><span class="sxs-lookup"><span data-stu-id="1bac8-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="1bac8-109">[out]如果方法失败，指定在索引`rSecAttrs`导致问题的元素。</span><span class="sxs-lookup"><span data-stu-id="1bac8-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bac8-110">要求</span><span class="sxs-lookup"><span data-stu-id="1bac8-110">Requirements</span></span>  
 <span data-ttu-id="1bac8-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1bac8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bac8-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1bac8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1bac8-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1bac8-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bac8-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bac8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bac8-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1bac8-115">See also</span></span>
- [<span data-ttu-id="1bac8-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="1bac8-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1bac8-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="1bac8-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
