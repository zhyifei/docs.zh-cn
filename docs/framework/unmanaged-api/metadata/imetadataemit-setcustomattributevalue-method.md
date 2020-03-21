---
title: IMetaDataEmit::SetCustomAttributeValue 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: 25b7f478ae0bd05b82fa960561fb8534efe2b4db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175663"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="0d6f2-102">IMetaDataEmit::SetCustomAttributeValue 方法</span><span class="sxs-lookup"><span data-stu-id="0d6f2-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="0d6f2-103">设置或更新以前调用[IMetaDataEmit：:DefineCustom属性](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)）定义的自定义属性的值。</span><span class="sxs-lookup"><span data-stu-id="0d6f2-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d6f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="0d6f2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d6f2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="0d6f2-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="0d6f2-106">[在]目标自定义属性的令牌。</span><span class="sxs-lookup"><span data-stu-id="0d6f2-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="0d6f2-107">[在]指向包含自定义属性的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="0d6f2-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="0d6f2-108">[在]自定义属性的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="0d6f2-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d6f2-109">要求</span><span class="sxs-lookup"><span data-stu-id="0d6f2-109">Requirements</span></span>  
 <span data-ttu-id="0d6f2-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d6f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d6f2-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="0d6f2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d6f2-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0d6f2-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d6f2-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d6f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d6f2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d6f2-114">See also</span></span>

- [<span data-ttu-id="0d6f2-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="0d6f2-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0d6f2-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="0d6f2-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
