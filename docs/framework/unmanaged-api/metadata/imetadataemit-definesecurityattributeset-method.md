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
ms.openlocfilehash: fadd1974cd4fa8a51a06700835f46df24e37d7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175767"
---
# <a name="imetadataemitdefinesecurityattributeset-method"></a><span data-ttu-id="061ec-102">IMetaDataEmit::DefineSecurityAttributeSet 方法</span><span class="sxs-lookup"><span data-stu-id="061ec-102">IMetaDataEmit::DefineSecurityAttributeSet Method</span></span>
<span data-ttu-id="061ec-103">创建一组安全权限以附加到指定令牌引用的对象。</span><span class="sxs-lookup"><span data-stu-id="061ec-103">Creates a set of security permissions to attach to the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="061ec-104">语法</span><span class="sxs-lookup"><span data-stu-id="061ec-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineSecurityAttributeSet (
    [in]  mdToken       tkObj,
    [in]  COR_SECATTR   rSecAttrs[],
    [in]  ULONG         cSecAttrs,
    [out] ULONG         *pulErrorAttr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="061ec-105">parameters</span><span class="sxs-lookup"><span data-stu-id="061ec-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="061ec-106">[在]附加安全信息的令牌。</span><span class="sxs-lookup"><span data-stu-id="061ec-106">[in] The token to which the security information is attached.</span></span>  
  
 `rSecAttrs`  
 <span data-ttu-id="061ec-107">[在]结构数组`COR_SECATTR`。</span><span class="sxs-lookup"><span data-stu-id="061ec-107">[in] An array of `COR_SECATTR` structures.</span></span>  
  
 `cSecAttrs`  
 <span data-ttu-id="061ec-108">[在]中`rSecAttrs`的元素数。</span><span class="sxs-lookup"><span data-stu-id="061ec-108">[in] The number of elements in `rSecAttrs`.</span></span>  
  
 `pulErrorAttr`  
 <span data-ttu-id="061ec-109">[出]如果方法失败，则指定导致问题的元素`rSecAttrs`中的索引。</span><span class="sxs-lookup"><span data-stu-id="061ec-109">[out] If the method fails, specifies the index in `rSecAttrs` of the element that caused the problem.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="061ec-110">要求</span><span class="sxs-lookup"><span data-stu-id="061ec-110">Requirements</span></span>  
 <span data-ttu-id="061ec-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="061ec-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="061ec-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="061ec-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="061ec-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="061ec-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="061ec-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="061ec-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="061ec-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="061ec-115">See also</span></span>

- [<span data-ttu-id="061ec-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="061ec-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="061ec-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="061ec-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
