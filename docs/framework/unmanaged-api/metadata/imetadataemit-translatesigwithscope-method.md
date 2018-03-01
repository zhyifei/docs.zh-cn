---
title: "IMetaDataEmit::TranslateSigWithScope 方法"
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
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ceb6a8bfbee5823e7080d8c98647da93a10a5b79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="8dc94-102">IMetaDataEmit::TranslateSigWithScope 方法</span><span class="sxs-lookup"><span data-stu-id="8dc94-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="8dc94-103">将程序集导入当前作用域和为合并的作用域中获取新的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="8dc94-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc94-104">语法</span><span class="sxs-lookup"><span data-stu-id="8dc94-104">Syntax</span></span>  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8dc94-105">参数</span><span class="sxs-lookup"><span data-stu-id="8dc94-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="8dc94-106">[in]用于导入程序集 （其中定义签名） 的接口。</span><span class="sxs-lookup"><span data-stu-id="8dc94-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="8dc94-107">[in]程序集哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="8dc94-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="8dc94-108">[in]中的字节计数`pbHashValue`。</span><span class="sxs-lookup"><span data-stu-id="8dc94-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="8dc94-109">[in]用于导入元数据范围的接口。</span><span class="sxs-lookup"><span data-stu-id="8dc94-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="8dc94-110">[in]要导入的签名。</span><span class="sxs-lookup"><span data-stu-id="8dc94-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="8dc94-111">[in]大小，以字节为单位的`pbSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="8dc94-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="8dc94-112">[in]用于导出程序集的接口。</span><span class="sxs-lookup"><span data-stu-id="8dc94-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="8dc94-113">[in]用于导出元数据范围的接口。</span><span class="sxs-lookup"><span data-stu-id="8dc94-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="8dc94-114">[out]要保存已翻译的签名 blob 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8dc94-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="8dc94-115">[in]容量，以字节为单位的`pvTranslatedSig`。</span><span class="sxs-lookup"><span data-stu-id="8dc94-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="8dc94-116">[out]已翻译的签名中的实际字节数。</span><span class="sxs-lookup"><span data-stu-id="8dc94-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dc94-117">惠?</span><span class="sxs-lookup"><span data-stu-id="8dc94-117">Requirements</span></span>  
 <span data-ttu-id="8dc94-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc94-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dc94-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8dc94-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8dc94-120">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8dc94-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8dc94-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc94-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc94-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8dc94-122">See Also</span></span>  
 [<span data-ttu-id="8dc94-123">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="8dc94-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="8dc94-124">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="8dc94-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="8dc94-125">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="8dc94-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="8dc94-126">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="8dc94-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="8dc94-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="8dc94-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
