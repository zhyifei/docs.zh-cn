---
title: IMetaDataImport::EnumParams 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ed5ddd74e61e63426871f659aa1c962d38fd534
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042586"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="11ad5-102">IMetaDataImport::EnumParams 方法</span><span class="sxs-lookup"><span data-stu-id="11ad5-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="11ad5-103">枚举 ParamDef 标记，这些标记表示指定的 MethodDef 标记所引用的方法的参数。</span><span class="sxs-lookup"><span data-stu-id="11ad5-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11ad5-104">语法</span><span class="sxs-lookup"><span data-stu-id="11ad5-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11ad5-105">参数</span><span class="sxs-lookup"><span data-stu-id="11ad5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="11ad5-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="11ad5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="11ad5-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="11ad5-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="11ad5-108">[in]表示与要枚举的参数的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="11ad5-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="11ad5-109">[out]用于存储 ParamDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="11ad5-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="11ad5-110">[in] `rParams` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="11ad5-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="11ad5-111">[out]在中返回的 ParamDef 标记数`rParams`。</span><span class="sxs-lookup"><span data-stu-id="11ad5-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11ad5-112">返回值</span><span class="sxs-lookup"><span data-stu-id="11ad5-112">Return Value</span></span>  
  
|<span data-ttu-id="11ad5-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="11ad5-113">HRESULT</span></span>|<span data-ttu-id="11ad5-114">描述</span><span class="sxs-lookup"><span data-stu-id="11ad5-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="11ad5-115">`EnumParams` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="11ad5-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="11ad5-116">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="11ad5-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="11ad5-117">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="11ad5-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11ad5-118">要求</span><span class="sxs-lookup"><span data-stu-id="11ad5-118">Requirements</span></span>  
 <span data-ttu-id="11ad5-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11ad5-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11ad5-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11ad5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11ad5-121">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="11ad5-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11ad5-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11ad5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ad5-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="11ad5-123">See also</span></span>

- [<span data-ttu-id="11ad5-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="11ad5-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="11ad5-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="11ad5-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
