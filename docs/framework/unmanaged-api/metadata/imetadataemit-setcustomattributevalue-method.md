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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f9e684b90dcc7f0ff83962361486caf7e991568
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050072"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="ca90c-102">IMetaDataEmit::SetCustomAttributeValue 方法</span><span class="sxs-lookup"><span data-stu-id="ca90c-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="ca90c-103">设置或更新由调用之前定义的自定义属性的值[imetadataemit:: Definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ca90c-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca90c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca90c-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca90c-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca90c-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="ca90c-106">[in]目标自定义特性的标记。</span><span class="sxs-lookup"><span data-stu-id="ca90c-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="ca90c-107">[in]指向包含自定义特性的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ca90c-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="ca90c-108">[in]以字节为单位的自定义特性的大小。</span><span class="sxs-lookup"><span data-stu-id="ca90c-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca90c-109">要求</span><span class="sxs-lookup"><span data-stu-id="ca90c-109">Requirements</span></span>  
 <span data-ttu-id="ca90c-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca90c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca90c-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ca90c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca90c-112">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ca90c-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca90c-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca90c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca90c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca90c-114">See also</span></span>

- [<span data-ttu-id="ca90c-115">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="ca90c-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ca90c-116">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="ca90c-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
