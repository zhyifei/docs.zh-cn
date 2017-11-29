---
title: "IMetaDataAssemblyImport::GetAssemblyProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f3ff9c66d483392823a1cc95163e4d5e7e81a364
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="5cf72-102">IMetaDataAssemblyImport::GetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="5cf72-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="5cf72-103">获取具有指定的元数据签名的程序集的属性集。</span><span class="sxs-lookup"><span data-stu-id="5cf72-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf72-104">语法</span><span class="sxs-lookup"><span data-stu-id="5cf72-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cf72-105">参数</span><span class="sxs-lookup"><span data-stu-id="5cf72-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="5cf72-106">[in]。</span><span class="sxs-lookup"><span data-stu-id="5cf72-106">[in].</span></span> <span data-ttu-id="5cf72-107">`mdAssembly`表示要为其获取属性的程序集的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5cf72-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="5cf72-108">[out]公钥或元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="5cf72-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="5cf72-109">[out]返回公钥中的字节数。</span><span class="sxs-lookup"><span data-stu-id="5cf72-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="5cf72-110">[out]指向用于在程序集中的文件执行哈希算法的指针。</span><span class="sxs-lookup"><span data-stu-id="5cf72-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="5cf72-111">[out]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="5cf72-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5cf72-112">[in]大小，以宽字符为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="5cf72-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5cf72-113">[out]中实际返回的宽字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="5cf72-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5cf72-114">[out]指向包含程序集元数据的 ASSEMBLYMETADATA 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="5cf72-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="5cf72-115">[out]描述应用于程序集的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="5cf72-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="5cf72-116">此值是一个或多个组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="5cf72-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cf72-117">要求</span><span class="sxs-lookup"><span data-stu-id="5cf72-117">Requirements</span></span>  
 <span data-ttu-id="5cf72-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5cf72-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cf72-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5cf72-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cf72-120">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5cf72-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5cf72-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cf72-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf72-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cf72-122">See Also</span></span>  
 [<span data-ttu-id="5cf72-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="5cf72-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
