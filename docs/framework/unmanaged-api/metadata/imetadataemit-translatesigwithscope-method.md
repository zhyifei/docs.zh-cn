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
ms.openlocfilehash: 2662af41fbd2cdc3ce8a6df1e036dfc5b22ff6a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175544"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="46a5a-102">IMetaDataEmit::TranslateSigWithScope 方法</span><span class="sxs-lookup"><span data-stu-id="46a5a-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="46a5a-103">将程序集导入当前作用域，并为合并作用域获取新的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="46a5a-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="46a5a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="46a5a-105">parameters</span><span class="sxs-lookup"><span data-stu-id="46a5a-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="46a5a-106">[在]导入程序集的接口（定义签名的位置）。</span><span class="sxs-lookup"><span data-stu-id="46a5a-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="46a5a-107">[在]程序集的哈希 blob。</span><span class="sxs-lookup"><span data-stu-id="46a5a-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="46a5a-108">[在]中的`pbHashValue`字节计数。</span><span class="sxs-lookup"><span data-stu-id="46a5a-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="46a5a-109">[在]导入元数据作用域的接口。</span><span class="sxs-lookup"><span data-stu-id="46a5a-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="46a5a-110">[在]要导入的签名。</span><span class="sxs-lookup"><span data-stu-id="46a5a-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="46a5a-111">[在]的大小（以字节为单位）的大小`pbSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="46a5a-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="46a5a-112">[在]导出程序集的接口。</span><span class="sxs-lookup"><span data-stu-id="46a5a-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="46a5a-113">[在]导出元数据作用域的接口。</span><span class="sxs-lookup"><span data-stu-id="46a5a-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="46a5a-114">[出]用于保存已翻译的签名 blob 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="46a5a-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="46a5a-115">[在]的容量（以字节为单位`pvTranslatedSig`）。</span><span class="sxs-lookup"><span data-stu-id="46a5a-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="46a5a-116">[出]翻译签名中的实际字节数。</span><span class="sxs-lookup"><span data-stu-id="46a5a-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46a5a-117">要求</span><span class="sxs-lookup"><span data-stu-id="46a5a-117">Requirements</span></span>  
 <span data-ttu-id="46a5a-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46a5a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46a5a-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="46a5a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46a5a-120">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="46a5a-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46a5a-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46a5a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46a5a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46a5a-122">See also</span></span>

- [<span data-ttu-id="46a5a-123">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="46a5a-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="46a5a-124">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="46a5a-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="46a5a-125">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="46a5a-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="46a5a-126">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="46a5a-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="46a5a-127">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="46a5a-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
