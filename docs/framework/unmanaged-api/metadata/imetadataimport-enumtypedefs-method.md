---
title: IMetaDataImport::EnumTypeDefs 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 2d6e86a7f5a93b900e79907f8ee0762869d7f737
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177288"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="56cda-102">IMetaDataImport::EnumTypeDefs 方法</span><span class="sxs-lookup"><span data-stu-id="56cda-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="56cda-103">枚举表示当前范围内的所有类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="56cda-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56cda-104">语法</span><span class="sxs-lookup"><span data-stu-id="56cda-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56cda-105">parameters</span><span class="sxs-lookup"><span data-stu-id="56cda-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="56cda-106">[出]指向新枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="56cda-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="56cda-107">对于此方法的第一次调用，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="56cda-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="56cda-108">[在]用于存储 TypeDef 令牌的数组。</span><span class="sxs-lookup"><span data-stu-id="56cda-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="56cda-109">[in] `rTypeDefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="56cda-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="56cda-110">[出]在 中`rTypeDefs`返回的 TypeDef 令牌数。</span><span class="sxs-lookup"><span data-stu-id="56cda-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56cda-111">返回值</span><span class="sxs-lookup"><span data-stu-id="56cda-111">Return Value</span></span>  
  
|<span data-ttu-id="56cda-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56cda-112">HRESULT</span></span>|<span data-ttu-id="56cda-113">说明</span><span class="sxs-lookup"><span data-stu-id="56cda-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="56cda-114">`EnumTypeDefs`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="56cda-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="56cda-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="56cda-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="56cda-116">在这种情况下，`pcTypeDefs`为零。</span><span class="sxs-lookup"><span data-stu-id="56cda-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56cda-117">备注</span><span class="sxs-lookup"><span data-stu-id="56cda-117">Remarks</span></span>  
 <span data-ttu-id="56cda-118">TypeDef 令牌表示类或接口的类型，以及通过扩展机制添加的任何类型。</span><span class="sxs-lookup"><span data-stu-id="56cda-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56cda-119">要求</span><span class="sxs-lookup"><span data-stu-id="56cda-119">Requirements</span></span>  
 <span data-ttu-id="56cda-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="56cda-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56cda-121">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="56cda-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="56cda-122">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="56cda-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="56cda-123">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56cda-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cda-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56cda-124">See also</span></span>

- [<span data-ttu-id="56cda-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="56cda-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="56cda-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="56cda-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
