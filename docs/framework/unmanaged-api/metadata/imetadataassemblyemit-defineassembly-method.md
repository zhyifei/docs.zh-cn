---
title: "IMetaDataAssemblyEmit::DefineAssembly 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 86002eb38d72ee628dbf54d0b5691f0816e6f996
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="1180b-102">IMetaDataAssemblyEmit::DefineAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="1180b-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="1180b-103">创建`Assembly`结构指定的程序集包含的元数据，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="1180b-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1180b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1180b-104">Syntax</span></span>  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1180b-105">参数</span><span class="sxs-lookup"><span data-stu-id="1180b-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="1180b-106">[in]如果程序集没有强名称标识的程序集或为 NULL 的发布者公钥。</span><span class="sxs-lookup"><span data-stu-id="1180b-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="1180b-107">[in]以字节为单位的大小`pbPublicKey`。</span><span class="sxs-lookup"><span data-stu-id="1180b-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="1180b-108">[in]要使用加密文件中的程序集或为 NULL，以指定 sha-1 算法的哈希算法标识符。</span><span class="sxs-lookup"><span data-stu-id="1180b-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="1180b-109">[in]程序集的用户可读文本名称。</span><span class="sxs-lookup"><span data-stu-id="1180b-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="1180b-110">此值不得超过 1024年个字符。</span><span class="sxs-lookup"><span data-stu-id="1180b-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="1180b-111">[in]指向包含程序集的版本、 平台和区域设置信息的 ASSEMBLYMETADATA 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="1180b-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="1180b-112">[in]组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值，用于描述程序集的功能。</span><span class="sxs-lookup"><span data-stu-id="1180b-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="1180b-113">[out]指向元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="1180b-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1180b-114">备注</span><span class="sxs-lookup"><span data-stu-id="1180b-114">Remarks</span></span>  
 <span data-ttu-id="1180b-115">只有一个`Assembly`元数据结构可定义一个清单内。</span><span class="sxs-lookup"><span data-stu-id="1180b-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1180b-116">要求</span><span class="sxs-lookup"><span data-stu-id="1180b-116">Requirements</span></span>  
 <span data-ttu-id="1180b-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1180b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1180b-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1180b-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1180b-119">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1180b-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1180b-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1180b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1180b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1180b-121">See Also</span></span>  
 [<span data-ttu-id="1180b-122">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="1180b-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
