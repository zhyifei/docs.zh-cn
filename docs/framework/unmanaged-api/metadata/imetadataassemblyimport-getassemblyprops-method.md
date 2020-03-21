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
ms.openlocfilehash: dfa900e2184a8c415d75f5702c572b14c4018749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177787"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="0a0b9-102">IMetaDataAssemblyImport::GetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="0a0b9-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="0a0b9-103">使用指定的元数据签名获取程序集的属性集。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a0b9-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="0a0b9-105">parameters</span><span class="sxs-lookup"><span data-stu-id="0a0b9-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="0a0b9-106">[在]。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-106">[in].</span></span> <span data-ttu-id="0a0b9-107">表示`mdAssembly`要为其获取属性的程序集的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="0a0b9-108">[出]指向公钥或元数据令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="0a0b9-109">[出]返回的公钥中的字节数。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="0a0b9-110">[出]指向用于哈希程序集中文件的算法的指针。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="0a0b9-111">[出]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0a0b9-112">[在]大字符的大小`szName`。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="0a0b9-113">[出]中实际返回的宽字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="0a0b9-114">[出]指向包含程序集元数据的装配元数据结构的指针。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="0a0b9-115">[出]描述应用于程序集的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="0a0b9-116">此值是一个或多个[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a0b9-117">要求</span><span class="sxs-lookup"><span data-stu-id="0a0b9-117">Requirements</span></span>  
 <span data-ttu-id="0a0b9-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0b9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a0b9-119">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="0a0b9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a0b9-120">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0a0b9-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a0b9-121">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a0b9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0b9-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a0b9-122">See also</span></span>

- [<span data-ttu-id="0a0b9-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="0a0b9-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
