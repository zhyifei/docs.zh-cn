---
title: IMetaDataAssemblyImport::GetAssemblyProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4817a62d276bfdb50bfcbf658f40f5568673bea0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163210"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="5366a-102">IMetaDataAssemblyImport::GetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="5366a-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="5366a-103">获取具有指定的元数据签名的程序集的属性集。</span><span class="sxs-lookup"><span data-stu-id="5366a-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5366a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5366a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5366a-105">参数</span><span class="sxs-lookup"><span data-stu-id="5366a-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="5366a-106">[in].</span><span class="sxs-lookup"><span data-stu-id="5366a-106">[in].</span></span> <span data-ttu-id="5366a-107">`mdAssembly`表示要为其获取属性的程序集的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="5366a-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="5366a-108">[out]公钥或元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="5366a-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="5366a-109">[out]中返回的公钥的字节数。</span><span class="sxs-lookup"><span data-stu-id="5366a-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="5366a-110">[out]一个指向用于在程序集中的文件执行哈希的算法。</span><span class="sxs-lookup"><span data-stu-id="5366a-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="5366a-111">[out]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="5366a-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5366a-112">[in]大小，以宽字符为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="5366a-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5366a-113">[out]中实际返回的宽字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="5366a-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5366a-114">[out]指向包含程序集元数据的 ASSEMBLYMETADATA 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="5366a-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="5366a-115">[out]描述应用于程序集的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="5366a-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="5366a-116">此值是一个或多个组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="5366a-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5366a-117">要求</span><span class="sxs-lookup"><span data-stu-id="5366a-117">Requirements</span></span>  
 <span data-ttu-id="5366a-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5366a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5366a-119">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5366a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5366a-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5366a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5366a-121">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5366a-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5366a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5366a-122">See also</span></span>

- [<span data-ttu-id="5366a-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="5366a-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
