---
title: IMetaDataImport2::GetGenericParamProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55a765fe3942cbf71a8460187e829dc7f3ca877e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59082329"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="42f22-102">IMetaDataImport2::GetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="42f22-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="42f22-103">获取与指定的标记表示的泛型参数相关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="42f22-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42f22-104">语法</span><span class="sxs-lookup"><span data-stu-id="42f22-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42f22-105">参数</span><span class="sxs-lookup"><span data-stu-id="42f22-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="42f22-106">[in]表示要为其返回的元数据的泛型参数的标记。</span><span class="sxs-lookup"><span data-stu-id="42f22-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="42f22-107">[out]序号位置`Type`父构造函数或方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="42f22-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="42f22-108">[out]值为[CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)枚举，用于描述`Type`泛型形参。</span><span class="sxs-lookup"><span data-stu-id="42f22-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="42f22-109">[out]TypeDef 或 MethodDef 标记表示的参数的所有者。</span><span class="sxs-lookup"><span data-stu-id="42f22-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="42f22-110">[out]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="42f22-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="42f22-111">[out]泛型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="42f22-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="42f22-112">[in]大小`wzName`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="42f22-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="42f22-113">[out]该名称，以宽字符为单位返回的大小。</span><span class="sxs-lookup"><span data-stu-id="42f22-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42f22-114">要求</span><span class="sxs-lookup"><span data-stu-id="42f22-114">Requirements</span></span>  
 <span data-ttu-id="42f22-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42f22-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42f22-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="42f22-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42f22-117">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="42f22-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42f22-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42f22-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42f22-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="42f22-119">See also</span></span>

- [<span data-ttu-id="42f22-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="42f22-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="42f22-121">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="42f22-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
