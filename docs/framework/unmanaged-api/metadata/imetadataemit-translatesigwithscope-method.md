---
title: IMetaDataEmit::TranslateSigWithScope 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: cea84f47a5289df4bc9c50381e18d7077b3b8dad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440473"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="37efb-102">IMetaDataEmit::TranslateSigWithScope 方法</span><span class="sxs-lookup"><span data-stu-id="37efb-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="37efb-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span><span class="sxs-lookup"><span data-stu-id="37efb-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37efb-104">语法</span><span class="sxs-lookup"><span data-stu-id="37efb-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="37efb-105">参数</span><span class="sxs-lookup"><span data-stu-id="37efb-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="37efb-106">[in] The interface for import assembly (where the signature is defined).</span><span class="sxs-lookup"><span data-stu-id="37efb-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="37efb-107">[in] The hash blob for the assembly.</span><span class="sxs-lookup"><span data-stu-id="37efb-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="37efb-108">[in] The count of bytes in `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="37efb-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="37efb-109">[in] The interface for import metadata scope.</span><span class="sxs-lookup"><span data-stu-id="37efb-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="37efb-110">[in] The signature to be imported.</span><span class="sxs-lookup"><span data-stu-id="37efb-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="37efb-111">[in] The size, in bytes, of `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="37efb-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="37efb-112">[in] The interface for export assembly.</span><span class="sxs-lookup"><span data-stu-id="37efb-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="37efb-113">[in] The interface for export metadata scope.</span><span class="sxs-lookup"><span data-stu-id="37efb-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="37efb-114">[out] The buffer to hold the translated signature blob.</span><span class="sxs-lookup"><span data-stu-id="37efb-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="37efb-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="37efb-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="37efb-116">[out] The number of actual bytes in the translated signature.</span><span class="sxs-lookup"><span data-stu-id="37efb-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37efb-117">要求</span><span class="sxs-lookup"><span data-stu-id="37efb-117">Requirements</span></span>  
 <span data-ttu-id="37efb-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37efb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37efb-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="37efb-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="37efb-120">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="37efb-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37efb-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37efb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37efb-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="37efb-122">See also</span></span>

- [<span data-ttu-id="37efb-123">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="37efb-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="37efb-124">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="37efb-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="37efb-125">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="37efb-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="37efb-126">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="37efb-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="37efb-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="37efb-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
