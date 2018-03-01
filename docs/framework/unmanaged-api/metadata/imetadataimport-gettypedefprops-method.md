---
title: "IMetaDataImport::GetTypeDefProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f3e7f2c2fe602ef3464766b62ef12e8f83767bf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="9c6c7-102">IMetaDataImport::GetTypeDefProps 方法</span><span class="sxs-lookup"><span data-stu-id="9c6c7-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="9c6c7-103">返回元数据信息<xref:System.Type>由指定的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c6c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="9c6c7-104">Syntax</span></span>  
  
```  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c6c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="9c6c7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9c6c7-106">[in]表示要返回的元数据的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="9c6c7-107">[out]包含的类型名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="9c6c7-108">[in]在宽字符为单位的大小`szTypeDef`。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="9c6c7-109">[out]在中返回的宽字符数`szTypeDef`。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="9c6c7-110">[out]指向任何修改的类型定义的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="9c6c7-111">此值是从一个位掩码[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="9c6c7-112">[out]TypeDef 或 TypeRef 元数据标记，用于表示所请求类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c6c7-113">惠?</span><span class="sxs-lookup"><span data-stu-id="9c6c7-113">Requirements</span></span>  
 <span data-ttu-id="9c6c7-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9c6c7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c6c7-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9c6c7-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c6c7-116">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9c6c7-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c6c7-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c6c7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c6c7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c6c7-118">See Also</span></span>  
 [<span data-ttu-id="9c6c7-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="9c6c7-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="9c6c7-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="9c6c7-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
