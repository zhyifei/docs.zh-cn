---
title: "IMetaDataImport2::GetGenericParamProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70a9669e2f47c3b56f7b50dc96ed2d3ba8314c4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="f6523-102">IMetaDataImport2::GetGenericParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="f6523-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="f6523-103">获取与指定标记所表示的泛型参数关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="f6523-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6523-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6523-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f6523-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6523-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="f6523-106">[in]表示用于返回元数据的泛型参数标记。</span><span class="sxs-lookup"><span data-stu-id="f6523-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="f6523-107">[out]序号位置`Type`父构造函数或方法中的参数。</span><span class="sxs-lookup"><span data-stu-id="f6523-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="f6523-108">[out]值为[CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md)描述枚举`Type`为泛型参数。</span><span class="sxs-lookup"><span data-stu-id="f6523-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="f6523-109">[out]TypeDef 或 MethodDef 标记表示的参数的所有者。</span><span class="sxs-lookup"><span data-stu-id="f6523-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="f6523-110">[out]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="f6523-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="f6523-111">[out]泛型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="f6523-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f6523-112">[in]大小`wzName`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="f6523-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f6523-113">[out]返回的名称，以宽字符为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="f6523-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6523-114">惠?</span><span class="sxs-lookup"><span data-stu-id="f6523-114">Requirements</span></span>  
 <span data-ttu-id="f6523-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6523-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6523-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6523-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6523-117">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f6523-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6523-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6523-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6523-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6523-119">See Also</span></span>  
 [<span data-ttu-id="f6523-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f6523-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="f6523-121">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f6523-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
