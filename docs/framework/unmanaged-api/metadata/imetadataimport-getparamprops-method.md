---
title: "IMetaDataImport::GetParamProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f36282df52b316bfa32c50c3fa9f55f829aa04e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="577b9-102">IMetaDataImport::GetParamProps 方法</span><span class="sxs-lookup"><span data-stu-id="577b9-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="577b9-103">获取指定的 ParamDef 标记所引用的参数的元数据值。</span><span class="sxs-lookup"><span data-stu-id="577b9-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="577b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="577b9-104">Syntax</span></span>  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="577b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="577b9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="577b9-106">[in]表示要返回的元数据的参数的 ParamDef 标记。</span><span class="sxs-lookup"><span data-stu-id="577b9-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="577b9-107">[out]指向表示采用参数的方法的 MethodDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="577b9-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="577b9-108">[out]参数的方法自变量列表中的序号位置。</span><span class="sxs-lookup"><span data-stu-id="577b9-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="577b9-109">[out]一个缓冲区来存放参数的名称。</span><span class="sxs-lookup"><span data-stu-id="577b9-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="577b9-110">[in]请求的大小以宽字符为单位`szName`。</span><span class="sxs-lookup"><span data-stu-id="577b9-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="577b9-111">[out]在宽字符为单位返回的大小`szName`。</span><span class="sxs-lookup"><span data-stu-id="577b9-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="577b9-112">[out]指向任何与参数相关联的属性标志的指针。</span><span class="sxs-lookup"><span data-stu-id="577b9-112">[out] A pointer to any attribute flags associated with the parameter.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="577b9-113">[out]该参数是指向该标志指定的指针<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="577b9-113">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="577b9-114">[out]指向返回由参数的常量字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="577b9-114">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="577b9-115">[out]大小`ppValue`以宽字符数或为零`ppValue`不包含一个字符串。</span><span class="sxs-lookup"><span data-stu-id="577b9-115">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="577b9-116">要求</span><span class="sxs-lookup"><span data-stu-id="577b9-116">Requirements</span></span>  
 <span data-ttu-id="577b9-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="577b9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="577b9-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="577b9-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="577b9-119">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="577b9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="577b9-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="577b9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577b9-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="577b9-121">See Also</span></span>  
 [<span data-ttu-id="577b9-122">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="577b9-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="577b9-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="577b9-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
