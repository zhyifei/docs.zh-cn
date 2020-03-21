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
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177892"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="ec4f0-102">IMetaDataAssemblyEmit::DefineAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="ec4f0-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="ec4f0-103">创建包含`Assembly`指定程序集元数据的结构并返回关联的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec4f0-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec4f0-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="ec4f0-105">parameters</span><span class="sxs-lookup"><span data-stu-id="ec4f0-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="ec4f0-106">[在]标识程序集的发布者的公共密钥，如果程序集未强命名，则为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="ec4f0-107">[在]的大小（以字节为单位）。 `pbPublicKey`</span><span class="sxs-lookup"><span data-stu-id="ec4f0-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="ec4f0-108">[在]用于加密程序集中的文件的哈希算法的标识符，或用于指定 SHA-1 算法的 NULL。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="ec4f0-109">[在]程序集的人类可读文本名称。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="ec4f0-110">此值不得超过 1024 个字符。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="ec4f0-111">[在]指向 ASSEMBLYMETADATA 实例的指针，其中包含程序集的版本、平台和区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="ec4f0-112">[在]描述程序集功能的[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="ec4f0-113">[出]指向元数据令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec4f0-114">备注</span><span class="sxs-lookup"><span data-stu-id="ec4f0-114">Remarks</span></span>  
 <span data-ttu-id="ec4f0-115">只能在清单`Assembly`中定义一个元数据结构。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec4f0-116">要求</span><span class="sxs-lookup"><span data-stu-id="ec4f0-116">Requirements</span></span>  
 <span data-ttu-id="ec4f0-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ec4f0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec4f0-118">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="ec4f0-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec4f0-119">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="ec4f0-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec4f0-120">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec4f0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec4f0-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec4f0-121">See also</span></span>

- [<span data-ttu-id="ec4f0-122">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="ec4f0-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
