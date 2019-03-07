---
title: IMetaDataAssemblyImport::GetAssemblyRefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 471f4837ff8aee725020f52c09a57d8f3652013c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489860"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="ae071-102">IMetaDataAssemblyImport::GetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="ae071-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="ae071-103">获取具有指定的元数据签名的程序集引用的属性集。</span><span class="sxs-lookup"><span data-stu-id="ae071-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae071-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae071-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ae071-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae071-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="ae071-106">[in]`mdAssemblyRef`表示要为其获取属性的程序集引用的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="ae071-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="ae071-107">[out]公钥或元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="ae071-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="ae071-108">[out]返回公钥或标记中的字节数。</span><span class="sxs-lookup"><span data-stu-id="ae071-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="ae071-109">[out]程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="ae071-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ae071-110">[in]大小，以宽字符为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="ae071-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ae071-111">[out]指向的宽字符中实际返回数的`szName`。</span><span class="sxs-lookup"><span data-stu-id="ae071-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="ae071-112">[out]指向包含程序集元数据的 ASSEMBLYMETADATA 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="ae071-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="ae071-113">[out]指向哈希值的指针。</span><span class="sxs-lookup"><span data-stu-id="ae071-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="ae071-114">这是使用 sha-1 算法，哈希`PublicKey`除非 arfFullOriginator 标记所引用的程序集的属性[AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)枚举设置。</span><span class="sxs-lookup"><span data-stu-id="ae071-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="ae071-115">[out]中返回的哈希值的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="ae071-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="ae071-116">[out]指向描述应用于程序集的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="ae071-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="ae071-117">标志值是一个或多个组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="ae071-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae071-118">返回值</span><span class="sxs-lookup"><span data-stu-id="ae071-118">Return Value</span></span>  
 <span data-ttu-id="ae071-119">此方法返回时如果它成功，则为 S_OK否则，它返回一个在 Winerror.h 标头文件中定义的错误代码。</span><span class="sxs-lookup"><span data-stu-id="ae071-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae071-120">要求</span><span class="sxs-lookup"><span data-stu-id="ae071-120">Requirements</span></span>  
 <span data-ttu-id="ae071-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae071-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae071-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ae071-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae071-123">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ae071-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae071-124">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae071-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae071-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae071-125">See also</span></span>
- [<span data-ttu-id="ae071-126">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="ae071-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
