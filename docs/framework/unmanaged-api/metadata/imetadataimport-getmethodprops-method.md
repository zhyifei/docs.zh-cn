---
title: "IMetaDataImport::GetMethodProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e4e0ae7dfed4b13ea83e16d6380443c9d1b72b06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="30c2a-102">IMetaDataImport::GetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="30c2a-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="30c2a-103">获取与指定的 MethodDef 标记引用的方法关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="30c2a-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c2a-104">语法</span><span class="sxs-lookup"><span data-stu-id="30c2a-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30c2a-105">参数</span><span class="sxs-lookup"><span data-stu-id="30c2a-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="30c2a-106">[in]表示要返回的元数据的方法的 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="30c2a-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="30c2a-107">[out]指向表示实现方法的类型的 TypeDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="30c2a-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="30c2a-108">[out]指向具有该方法的名称的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="30c2a-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="30c2a-109">[in]请求的大小的`szMethod`。</span><span class="sxs-lookup"><span data-stu-id="30c2a-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="30c2a-110">[out]指向的大小以宽字符为单位的`szMethod`，或发生截断时，实际方法名称中的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="30c2a-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="30c2a-111">[out]指向与该方法关联的任何标志的指针。</span><span class="sxs-lookup"><span data-stu-id="30c2a-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="30c2a-112">[out]指向方法的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="30c2a-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="30c2a-113">[out]指向以字节为单位的大小的`ppvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="30c2a-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="30c2a-114">[out]指向方法的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="30c2a-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="30c2a-115">[out]指向任何实现标志的方法的指针。</span><span class="sxs-lookup"><span data-stu-id="30c2a-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30c2a-116">惠?</span><span class="sxs-lookup"><span data-stu-id="30c2a-116">Requirements</span></span>  
 <span data-ttu-id="30c2a-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30c2a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c2a-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="30c2a-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30c2a-119">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="30c2a-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30c2a-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c2a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c2a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="30c2a-121">See Also</span></span>  
 [<span data-ttu-id="30c2a-122">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="30c2a-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="30c2a-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="30c2a-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
