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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221396"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="8c406-102">IMetaDataImport::EnumParams 方法</span><span class="sxs-lookup"><span data-stu-id="8c406-102">IMetaDataImport::EnumParams Method</span></span>
<span data-ttu-id="8c406-103">枚举 ParamDef 标记，这些标记表示指定的 MethodDef 标记所引用的方法的参数。</span><span class="sxs-lookup"><span data-stu-id="8c406-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c406-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c406-104">Syntax</span></span>  
  
```  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c406-105">参数</span><span class="sxs-lookup"><span data-stu-id="8c406-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8c406-106">[in、 out]一个指向枚举器。</span><span class="sxs-lookup"><span data-stu-id="8c406-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8c406-107">对于首次调用此方法，这必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8c406-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="8c406-108">[in]表示与要枚举的参数的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="8c406-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="8c406-109">[out]用于存储 ParamDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="8c406-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8c406-110">[in] `rParams` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="8c406-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8c406-111">[out]在中返回的 ParamDef 标记数`rParams`。</span><span class="sxs-lookup"><span data-stu-id="8c406-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c406-112">返回值</span><span class="sxs-lookup"><span data-stu-id="8c406-112">Return Value</span></span>  
  
|<span data-ttu-id="8c406-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c406-113">HRESULT</span></span>|<span data-ttu-id="8c406-114">描述</span><span class="sxs-lookup"><span data-stu-id="8c406-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumParams` <span data-ttu-id="8c406-115">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="8c406-115">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8c406-116">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="8c406-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="8c406-117">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="8c406-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c406-118">要求</span><span class="sxs-lookup"><span data-stu-id="8c406-118">Requirements</span></span>  
 <span data-ttu-id="8c406-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c406-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c406-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8c406-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c406-121">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8c406-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8c406-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="8c406-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c406-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c406-123">See also</span></span>

- [<span data-ttu-id="8c406-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="8c406-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8c406-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="8c406-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
