---
title: IMetaDataImport::EnumMethods 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 218b65b5899692774c434ae136a3976ecb97ea2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177308"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="df4d4-102">IMetaDataImport::EnumMethods 方法</span><span class="sxs-lookup"><span data-stu-id="df4d4-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="df4d4-103">枚举表示指定类型的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="df4d4-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df4d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="df4d4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df4d4-105">parameters</span><span class="sxs-lookup"><span data-stu-id="df4d4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="df4d4-106">[进出]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="df4d4-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="df4d4-107">对于此方法的第一次调用，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="df4d4-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="df4d4-108">[在]表示具有要枚举的方法的类型的 TypeDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="df4d4-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="df4d4-109">[出]要存储方法Def令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="df4d4-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="df4d4-110">[在]方法Def`rMethods`数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="df4d4-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="df4d4-111">[出]在 中`rMethods`返回的 MethodDef 令牌数。</span><span class="sxs-lookup"><span data-stu-id="df4d4-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df4d4-112">返回值</span><span class="sxs-lookup"><span data-stu-id="df4d4-112">Return Value</span></span>  
  
|<span data-ttu-id="df4d4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df4d4-113">HRESULT</span></span>|<span data-ttu-id="df4d4-114">说明</span><span class="sxs-lookup"><span data-stu-id="df4d4-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="df4d4-115">`EnumMethods`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="df4d4-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="df4d4-116">没有要枚举的 MethodDef 令牌。</span><span class="sxs-lookup"><span data-stu-id="df4d4-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="df4d4-117">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="df4d4-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="df4d4-118">要求</span><span class="sxs-lookup"><span data-stu-id="df4d4-118">Requirements</span></span>  
 <span data-ttu-id="df4d4-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df4d4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df4d4-120">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="df4d4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df4d4-121">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="df4d4-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df4d4-122">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df4d4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df4d4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df4d4-123">See also</span></span>

- [<span data-ttu-id="df4d4-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="df4d4-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="df4d4-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="df4d4-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
