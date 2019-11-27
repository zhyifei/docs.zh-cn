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
ms.openlocfilehash: 3854cb4aa3d229c87466c0a35a72447ceb235624
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449990"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="a4f1b-102">IMetaDataImport::EnumTypeDefs 方法</span><span class="sxs-lookup"><span data-stu-id="a4f1b-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="a4f1b-103">枚举表示当前范围内的所有类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4f1b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4f1b-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4f1b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a4f1b-106">弄指向新枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="a4f1b-107">第一次调用此方法时，此值必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="a4f1b-108">中用于存储 TypeDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a4f1b-109">[in] `rTypeDefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="a4f1b-110">弄`rTypeDefs`中返回的 TypeDef 标记的数目。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4f1b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a4f1b-111">Return Value</span></span>  
  
|<span data-ttu-id="a4f1b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4f1b-112">HRESULT</span></span>|<span data-ttu-id="a4f1b-113">说明</span><span class="sxs-lookup"><span data-stu-id="a4f1b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a4f1b-114">`EnumTypeDefs` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a4f1b-115">没有要枚举的令牌。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a4f1b-116">在这种情况下，`pcTypeDefs` 为零。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4f1b-117">备注</span><span class="sxs-lookup"><span data-stu-id="a4f1b-117">Remarks</span></span>  
 <span data-ttu-id="a4f1b-118">TypeDef 标记表示一种类型，如类或接口，以及通过扩展性机制添加的任何类型。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4f1b-119">要求</span><span class="sxs-lookup"><span data-stu-id="a4f1b-119">Requirements</span></span>  
 <span data-ttu-id="a4f1b-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4f1b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4f1b-121">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="a4f1b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4f1b-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="a4f1b-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4f1b-123">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4f1b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f1b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4f1b-124">See also</span></span>

- [<span data-ttu-id="a4f1b-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a4f1b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a4f1b-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="a4f1b-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
