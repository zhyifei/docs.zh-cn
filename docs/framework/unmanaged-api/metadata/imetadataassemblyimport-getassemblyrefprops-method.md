---
title: "IMetaDataAssemblyImport::GetAssemblyRefProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9159352c4f7f338c6b9b82ea579ad3cb36c19007
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="159cc-102">IMetaDataAssemblyImport::GetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="159cc-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="159cc-103">获取与指定的元数据签名的程序集引用的属性集。</span><span class="sxs-lookup"><span data-stu-id="159cc-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="159cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="159cc-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="159cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="159cc-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="159cc-106">[in]`mdAssemblyRef`表示要为其获取属性的程序集引用的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="159cc-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="159cc-107">[out]公钥或元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="159cc-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="159cc-108">[out]返回公钥或标记中的字节数。</span><span class="sxs-lookup"><span data-stu-id="159cc-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="159cc-109">[out]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="159cc-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="159cc-110">[in]大小，以宽字符为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="159cc-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="159cc-111">[out]指向的宽字符中实际返回数的指针`szName`。</span><span class="sxs-lookup"><span data-stu-id="159cc-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="159cc-112">[out]指向包含程序集元数据的 ASSEMBLYMETADATA 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="159cc-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="159cc-113">[out]指向哈希值的指针。</span><span class="sxs-lookup"><span data-stu-id="159cc-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="159cc-114">这是使用 sha-1 算法，哈希`PublicKey`引用，除非 arfFullOriginator 标志的程序集的属性[AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)枚举设置。</span><span class="sxs-lookup"><span data-stu-id="159cc-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="159cc-115">[out]返回的哈希值中的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="159cc-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="159cc-116">[out]指向描述应用于程序集的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="159cc-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="159cc-117">标志值是一个或多个组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="159cc-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="159cc-118">返回值</span><span class="sxs-lookup"><span data-stu-id="159cc-118">Return Value</span></span>  
 <span data-ttu-id="159cc-119">此方法返回成功; 如果，则为 S_OK否则，它将返回一个在 Winerror.h 标头文件中定义的错误代码。</span><span class="sxs-lookup"><span data-stu-id="159cc-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="159cc-120">要求</span><span class="sxs-lookup"><span data-stu-id="159cc-120">Requirements</span></span>  
 <span data-ttu-id="159cc-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="159cc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="159cc-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="159cc-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="159cc-123">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="159cc-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="159cc-124">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="159cc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159cc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="159cc-125">See Also</span></span>  
 [<span data-ttu-id="159cc-126">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="159cc-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
