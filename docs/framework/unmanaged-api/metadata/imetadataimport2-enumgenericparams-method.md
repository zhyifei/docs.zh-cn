---
title: IMetaDataImport2::EnumGenericParams 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 39e3e71185051435afcf03d51ec62742c080b02a
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855710"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="2e4ab-102">IMetaDataImport2::EnumGenericParams 方法</span><span class="sxs-lookup"><span data-stu-id="2e4ab-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="2e4ab-103">获取与指定的 TypeDef 或 MethodDef 标记相关联的泛型参数标记数组的枚举器。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e4ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e4ab-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e4ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e4ab-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2e4ab-106">[in，out]指向枚举器的指针。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="2e4ab-107">中要枚举其泛型参数的 TypeDef 或 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="2e4ab-108">弄要枚举的泛型参数的数组。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2e4ab-109">中要放入`rGenericParams`的请求的最大数量。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="2e4ab-110">弄放入的标记数`rGenericParams`。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e4ab-111">返回值</span><span class="sxs-lookup"><span data-stu-id="2e4ab-111">Return Value</span></span>  
  
|<span data-ttu-id="2e4ab-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e4ab-112">HRESULT</span></span>|<span data-ttu-id="2e4ab-113">描述</span><span class="sxs-lookup"><span data-stu-id="2e4ab-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2e4ab-114">`EnumGenericParams`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2e4ab-115">`phEnum`没有成员元素。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="2e4ab-116">在这种情况`pcGenericParams`下，设置为0（零）。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e4ab-117">要求</span><span class="sxs-lookup"><span data-stu-id="2e4ab-117">Requirements</span></span>  
 <span data-ttu-id="2e4ab-118">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e4ab-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e4ab-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="2e4ab-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e4ab-120">**类库**用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2e4ab-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e4ab-121">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e4ab-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e4ab-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e4ab-122">See also</span></span>

- [<span data-ttu-id="2e4ab-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="2e4ab-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="2e4ab-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="2e4ab-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
