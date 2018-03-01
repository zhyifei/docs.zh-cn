---
title: "IMetaDataAssemblyEmit::DefineAssemblyRef 方法"
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
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 123bd37d189477eade72e3b0e74f923fecce57a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="350f3-102">IMetaDataAssemblyEmit::DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="350f3-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="350f3-103">创建包含此程序集引用的程序集的元数据的 `AssemblyRef` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="350f3-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="350f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="350f3-104">Syntax</span></span>  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="350f3-105">参数</span><span class="sxs-lookup"><span data-stu-id="350f3-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="350f3-106">[in]引用的程序集的发布者的公钥。</span><span class="sxs-lookup"><span data-stu-id="350f3-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="350f3-107">Helper 函数[StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)可以用于获取作为此参数进行传递的公钥的哈希。</span><span class="sxs-lookup"><span data-stu-id="350f3-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="350f3-108">[in]以字节为单位的大小`pbPublicKeyOrToken`。</span><span class="sxs-lookup"><span data-stu-id="350f3-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="350f3-109">[in]程序集的用户可读文本名称。</span><span class="sxs-lookup"><span data-stu-id="350f3-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="350f3-110">此值不得超过 1024年个字符。</span><span class="sxs-lookup"><span data-stu-id="350f3-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="350f3-111">[in]ASSEMBLYMETADATA 实例包含引用的程序集的版本、 平台和区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="350f3-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="350f3-112">[in]与引用的程序集关联的哈希数据。</span><span class="sxs-lookup"><span data-stu-id="350f3-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="350f3-113">可选。</span><span class="sxs-lookup"><span data-stu-id="350f3-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="350f3-114">[in]以字节为单位的大小`pbHashValue`。</span><span class="sxs-lookup"><span data-stu-id="350f3-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="350f3-115">[in]按位组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)影响执行引擎的行为的值。</span><span class="sxs-lookup"><span data-stu-id="350f3-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="350f3-116">[out]指向返回的指针`AssemblyRef`元数据标记。</span><span class="sxs-lookup"><span data-stu-id="350f3-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="350f3-117">备注</span><span class="sxs-lookup"><span data-stu-id="350f3-117">Remarks</span></span>  
 <span data-ttu-id="350f3-118">一个`AssemblyRef`必须为此程序集引用每个程序集定义元数据结构。</span><span class="sxs-lookup"><span data-stu-id="350f3-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="350f3-119">在运行时，引用的程序集的详细信息传递给它们表示"按生成"信息指示此程序集冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="350f3-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="350f3-120">此程序集冲突解决程序然后将应用策略。</span><span class="sxs-lookup"><span data-stu-id="350f3-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="350f3-121">惠?</span><span class="sxs-lookup"><span data-stu-id="350f3-121">Requirements</span></span>  
 <span data-ttu-id="350f3-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="350f3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="350f3-123">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="350f3-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="350f3-124">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="350f3-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="350f3-125">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="350f3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350f3-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="350f3-126">See Also</span></span>  
 [<span data-ttu-id="350f3-127">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="350f3-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
