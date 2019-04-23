---
title: IMetaDataAssemblyEmit::DefineAssembly 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b95a583aec87e3ba3e247d1ef800302b62657837
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176002"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="d90eb-102">IMetaDataAssemblyEmit::DefineAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="d90eb-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="d90eb-103">创建`Assembly`结构包含元数据，为指定的程序集并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d90eb-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d90eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="d90eb-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d90eb-105">参数</span><span class="sxs-lookup"><span data-stu-id="d90eb-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="d90eb-106">[in]如果该程序集没有强名称标识的程序集或为 NULL 的发布者公钥。</span><span class="sxs-lookup"><span data-stu-id="d90eb-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="d90eb-107">[in]以字节为单位的大小`pbPublicKey`。</span><span class="sxs-lookup"><span data-stu-id="d90eb-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="d90eb-108">[in]要用于加密的程序集或为 NULL，以指定 sha-1 算法中的文件的哈希算法的标识符。</span><span class="sxs-lookup"><span data-stu-id="d90eb-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="d90eb-109">[in]用户可读文本的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="d90eb-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="d90eb-110">此值不得超过 1024年个字符。</span><span class="sxs-lookup"><span data-stu-id="d90eb-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="d90eb-111">[in]指向包含程序集的版本、 平台和区域设置信息的 ASSEMBLYMETADATA 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="d90eb-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="d90eb-112">[in]组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值，用于描述程序集的功能。</span><span class="sxs-lookup"><span data-stu-id="d90eb-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="d90eb-113">[out]指向元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="d90eb-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d90eb-114">备注</span><span class="sxs-lookup"><span data-stu-id="d90eb-114">Remarks</span></span>  
 <span data-ttu-id="d90eb-115">只有一个`Assembly`元数据结构可定义一个清单内。</span><span class="sxs-lookup"><span data-stu-id="d90eb-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d90eb-116">要求</span><span class="sxs-lookup"><span data-stu-id="d90eb-116">Requirements</span></span>  
 <span data-ttu-id="d90eb-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d90eb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d90eb-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d90eb-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d90eb-119">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d90eb-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d90eb-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d90eb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d90eb-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="d90eb-121">See also</span></span>

- [<span data-ttu-id="d90eb-122">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="d90eb-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
