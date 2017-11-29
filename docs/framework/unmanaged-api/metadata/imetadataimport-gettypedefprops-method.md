---
title: "IMetaDataImport::GetTypeDefProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1025ffde2bd066c81c4c562c0dd86e829fc2aef3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="7c8b4-102">IMetaDataImport::GetTypeDefProps 方法</span><span class="sxs-lookup"><span data-stu-id="7c8b4-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="7c8b4-103">返回元数据信息<xref:System.Type>由指定的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c8b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c8b4-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="7c8b4-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c8b4-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="7c8b4-106">[in]表示要返回的元数据的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="7c8b4-107">[out]包含的类型名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="7c8b4-108">[in]在宽字符为单位的大小`szTypeDef`。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="7c8b4-109">[out]在中返回的宽字符数`szTypeDef`。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="7c8b4-110">[out]指向任何修改的类型定义的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="7c8b4-111">此值是从一个位掩码[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="7c8b4-112">[out]TypeDef 或 TypeRef 元数据标记，用于表示所请求类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c8b4-113">要求</span><span class="sxs-lookup"><span data-stu-id="7c8b4-113">Requirements</span></span>  
 <span data-ttu-id="7c8b4-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c8b4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c8b4-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c8b4-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c8b4-116">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7c8b4-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c8b4-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c8b4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c8b4-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c8b4-118">See Also</span></span>  
 [<span data-ttu-id="7c8b4-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7c8b4-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7c8b4-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7c8b4-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
