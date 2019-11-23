---
title: IMetaDataAssemblyEmit::DefineAssemblyRef 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: c88b7a401a19b1bd0e02edab7ef7bbee1372199e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432076"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="898f7-102">IMetaDataAssemblyEmit::DefineAssemblyRef 方法</span><span class="sxs-lookup"><span data-stu-id="898f7-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="898f7-103">创建包含此程序集引用的程序集的元数据的 `AssemblyRef` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="898f7-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="898f7-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="898f7-105">参数</span><span class="sxs-lookup"><span data-stu-id="898f7-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="898f7-106">[in] The public key of the publisher of the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="898f7-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="898f7-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span><span class="sxs-lookup"><span data-stu-id="898f7-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="898f7-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="898f7-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="898f7-109">[in] The human-readable text name of the assembly.</span><span class="sxs-lookup"><span data-stu-id="898f7-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="898f7-110">This value must not exceed 1024 characters.</span><span class="sxs-lookup"><span data-stu-id="898f7-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="898f7-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="898f7-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="898f7-112">[in] The hash data associated with the referenced assembly.</span><span class="sxs-lookup"><span data-stu-id="898f7-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="898f7-113">可选。</span><span class="sxs-lookup"><span data-stu-id="898f7-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="898f7-114">[in] The size in bytes of `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="898f7-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="898f7-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span><span class="sxs-lookup"><span data-stu-id="898f7-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="898f7-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span><span class="sxs-lookup"><span data-stu-id="898f7-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="898f7-117">备注</span><span class="sxs-lookup"><span data-stu-id="898f7-117">Remarks</span></span>  
 <span data-ttu-id="898f7-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span><span class="sxs-lookup"><span data-stu-id="898f7-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="898f7-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span><span class="sxs-lookup"><span data-stu-id="898f7-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="898f7-120">The assembly resolver then applies policy.</span><span class="sxs-lookup"><span data-stu-id="898f7-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="898f7-121">要求</span><span class="sxs-lookup"><span data-stu-id="898f7-121">Requirements</span></span>  
 <span data-ttu-id="898f7-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="898f7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="898f7-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="898f7-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="898f7-124">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="898f7-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="898f7-125">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="898f7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898f7-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="898f7-126">See also</span></span>

- [<span data-ttu-id="898f7-127">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="898f7-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
