---
title: IMetaDataImport::GetTypeDefProps 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a482c7a06efe888408206f2de569e0a8739b85b8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121506"
---
# <a name="imetadataimportgettypedefprops-method"></a><span data-ttu-id="1af2f-102">IMetaDataImport::GetTypeDefProps 方法</span><span class="sxs-lookup"><span data-stu-id="1af2f-102">IMetaDataImport::GetTypeDefProps Method</span></span>
<span data-ttu-id="1af2f-103">返回元数据信息<xref:System.Type>由指定的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="1af2f-103">Returns metadata information for the <xref:System.Type> represented by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1af2f-104">语法</span><span class="sxs-lookup"><span data-stu-id="1af2f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1af2f-105">参数</span><span class="sxs-lookup"><span data-stu-id="1af2f-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1af2f-106">[in]表示要返回的元数据的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="1af2f-106">[in] The TypeDef token that represents the type to return metadata for.</span></span>  
  
 `szTypeDef`  
 <span data-ttu-id="1af2f-107">[out]包含类型名称的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1af2f-107">[out] A buffer containing the type name.</span></span>  
  
 `cchTypeDef`  
 <span data-ttu-id="1af2f-108">[in]在宽字符为单位的大小`szTypeDef`。</span><span class="sxs-lookup"><span data-stu-id="1af2f-108">[in] The size in wide characters of `szTypeDef`.</span></span>  
  
 `pchTypeDef`  
 <span data-ttu-id="1af2f-109">[out]在中返回的宽字符数`szTypeDef`。</span><span class="sxs-lookup"><span data-stu-id="1af2f-109">[out] The number of wide characters returned in `szTypeDef`.</span></span>  
  
 `pdwTypeDefFlags`  
 <span data-ttu-id="1af2f-110">[out]一个指向任何修改的类型定义的标志。</span><span class="sxs-lookup"><span data-stu-id="1af2f-110">[out] A pointer to any flags that modify the type definition.</span></span> <span data-ttu-id="1af2f-111">此值是从一个位掩码[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="1af2f-111">This value is a bitmask from the [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration.</span></span>  
  
 `ptkExtends`  
 <span data-ttu-id="1af2f-112">[out]TypeDef 或 TypeRef 元数据标记，表示所请求类型的基类型。</span><span class="sxs-lookup"><span data-stu-id="1af2f-112">[out] A TypeDef or TypeRef metadata token that represents the base type of the requested type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1af2f-113">要求</span><span class="sxs-lookup"><span data-stu-id="1af2f-113">Requirements</span></span>  
 <span data-ttu-id="1af2f-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1af2f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1af2f-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1af2f-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1af2f-116">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1af2f-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1af2f-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="1af2f-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1af2f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1af2f-118">See also</span></span>

- [<span data-ttu-id="1af2f-119">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="1af2f-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1af2f-120">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="1af2f-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
