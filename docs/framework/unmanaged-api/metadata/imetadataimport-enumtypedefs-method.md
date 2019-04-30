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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 20913d1cfa258036e8c20e826415f96a8984fdb4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042479"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="0e926-102">IMetaDataImport::EnumTypeDefs 方法</span><span class="sxs-lookup"><span data-stu-id="0e926-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="0e926-103">枚举表示当前范围内的所有类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="0e926-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e926-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e926-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e926-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e926-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0e926-106">[out]指向新枚举数的指针。</span><span class="sxs-lookup"><span data-stu-id="0e926-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="0e926-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="0e926-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="0e926-108">[in]用于存储 TypeDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="0e926-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0e926-109">[in] `rTypeDefs` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="0e926-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="0e926-110">[out]在中返回的 TypeDef 标记数`rTypeDefs`。</span><span class="sxs-lookup"><span data-stu-id="0e926-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e926-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0e926-111">Return Value</span></span>  
  
|<span data-ttu-id="0e926-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e926-112">HRESULT</span></span>|<span data-ttu-id="0e926-113">描述</span><span class="sxs-lookup"><span data-stu-id="0e926-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0e926-114">`EnumTypeDefs` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0e926-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0e926-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="0e926-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="0e926-116">在这种情况下，`pcTypeDefs`为零。</span><span class="sxs-lookup"><span data-stu-id="0e926-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e926-117">备注</span><span class="sxs-lookup"><span data-stu-id="0e926-117">Remarks</span></span>  
 <span data-ttu-id="0e926-118">TypeDef 标记表示一个类或接口，如类型以及可扩展性机制通过添加任何类型。</span><span class="sxs-lookup"><span data-stu-id="0e926-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e926-119">要求</span><span class="sxs-lookup"><span data-stu-id="0e926-119">Requirements</span></span>  
 <span data-ttu-id="0e926-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e926-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e926-121">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0e926-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e926-122">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0e926-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e926-123">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e926-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e926-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e926-124">See also</span></span>

- [<span data-ttu-id="0e926-125">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="0e926-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0e926-126">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="0e926-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
