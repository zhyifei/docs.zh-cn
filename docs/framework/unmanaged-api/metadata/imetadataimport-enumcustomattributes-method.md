---
title: IMetaDataImport::EnumCustomAttributes 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b549c6eacad63b165d26c203817f1a2adac57bca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448633"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="602ae-102">IMetaDataImport::EnumCustomAttributes 方法</span><span class="sxs-lookup"><span data-stu-id="602ae-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="602ae-103">枚举与指定的类型或成员相关联的自定义特性定义标记。</span><span class="sxs-lookup"><span data-stu-id="602ae-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="602ae-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes (   
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,   
   [in]  mdToken            tkType,   
   [out] mdCustomAttribute  rCustomAttributes[],   
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="602ae-105">参数</span><span class="sxs-lookup"><span data-stu-id="602ae-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="602ae-106">[在中，out]返回的枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="602ae-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="602ae-107">[in]用于枚举，则为零的所有自定义属性的作用域的令牌。</span><span class="sxs-lookup"><span data-stu-id="602ae-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="602ae-108">[in]要枚举的属性的类型的构造函数的令牌或`null`对于所有类型。</span><span class="sxs-lookup"><span data-stu-id="602ae-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="602ae-109">[out]自定义特性标记的数组。</span><span class="sxs-lookup"><span data-stu-id="602ae-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="602ae-110">[in] `rCustomAttributes` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="602ae-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="602ae-111">[out，optional]在中返回的令牌值的实际数目`rCustomAttributes`。</span><span class="sxs-lookup"><span data-stu-id="602ae-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="602ae-112">返回值</span><span class="sxs-lookup"><span data-stu-id="602ae-112">Return Value</span></span>  
  
|<span data-ttu-id="602ae-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="602ae-113">HRESULT</span></span>|<span data-ttu-id="602ae-114">描述</span><span class="sxs-lookup"><span data-stu-id="602ae-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="602ae-115">`EnumCustomAttributes` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="602ae-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="602ae-116">没有自定义属性来枚举。</span><span class="sxs-lookup"><span data-stu-id="602ae-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="602ae-117">在这种情况下，`pcCustomAttributes`为零。</span><span class="sxs-lookup"><span data-stu-id="602ae-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="602ae-118">要求</span><span class="sxs-lookup"><span data-stu-id="602ae-118">Requirements</span></span>  
 <span data-ttu-id="602ae-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="602ae-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="602ae-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="602ae-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="602ae-121">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="602ae-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="602ae-122">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="602ae-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602ae-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="602ae-123">See Also</span></span>  
 [<span data-ttu-id="602ae-124">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="602ae-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="602ae-125">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="602ae-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
