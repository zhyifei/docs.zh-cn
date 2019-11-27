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
ms.openlocfilehash: 8e9e08ac903423b2e121f22cc9e43a660ccfac7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450081"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="22335-102">IMetaDataImport::EnumMethods 方法</span><span class="sxs-lookup"><span data-stu-id="22335-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="22335-103">枚举表示指定类型的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="22335-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22335-104">语法</span><span class="sxs-lookup"><span data-stu-id="22335-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22335-105">参数</span><span class="sxs-lookup"><span data-stu-id="22335-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="22335-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="22335-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="22335-107">第一次调用此方法时，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="22335-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="22335-108">中一个 TypeDef 标记，它表示具有要枚举的方法的类型。</span><span class="sxs-lookup"><span data-stu-id="22335-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="22335-109">弄用于存储 MethodDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="22335-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="22335-110">中`rMethods` 数组的 MethodDef 的最大大小。</span><span class="sxs-lookup"><span data-stu-id="22335-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="22335-111">弄`rMethods`中返回的 MethodDef 标记的数目。</span><span class="sxs-lookup"><span data-stu-id="22335-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22335-112">返回值</span><span class="sxs-lookup"><span data-stu-id="22335-112">Return Value</span></span>  
  
|<span data-ttu-id="22335-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22335-113">HRESULT</span></span>|<span data-ttu-id="22335-114">说明</span><span class="sxs-lookup"><span data-stu-id="22335-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="22335-115">`EnumMethods` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="22335-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="22335-116">没有要枚举的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="22335-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="22335-117">在这种情况下，`pcTokens` 为零。</span><span class="sxs-lookup"><span data-stu-id="22335-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22335-118">要求</span><span class="sxs-lookup"><span data-stu-id="22335-118">Requirements</span></span>  
 <span data-ttu-id="22335-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22335-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22335-120">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="22335-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22335-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="22335-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22335-122">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22335-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22335-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22335-123">See also</span></span>

- [<span data-ttu-id="22335-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="22335-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="22335-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="22335-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
