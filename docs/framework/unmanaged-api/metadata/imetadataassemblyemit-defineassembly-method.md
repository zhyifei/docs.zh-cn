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
ms.openlocfilehash: 20628e708261076c6e172ff30c366a0d69c2e0f2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432119"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="f8c91-102">IMetaDataAssemblyEmit::DefineAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="f8c91-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="f8c91-103">创建包含指定程序集的元数据的 `Assembly` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f8c91-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8c91-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8c91-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f8c91-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8c91-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="f8c91-106">中标识程序集发行者的公钥; 如果程序集没有强名称，则为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8c91-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="f8c91-107">中`pbPublicKey`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f8c91-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="f8c91-108">中用于对程序集中的文件进行加密的哈希算法的标识符; 如果为 NULL，则指定 SHA-1 算法。</span><span class="sxs-lookup"><span data-stu-id="f8c91-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="f8c91-109">中程序集的用户可读文本名称。</span><span class="sxs-lookup"><span data-stu-id="f8c91-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="f8c91-110">此值不能超过1024个字符。</span><span class="sxs-lookup"><span data-stu-id="f8c91-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="f8c91-111">中指向 ASSEMBLYMETADATA 实例的指针，其中包含程序集的版本、平台和区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="f8c91-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="f8c91-112">中[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值的组合，用于描述程序集的功能。</span><span class="sxs-lookup"><span data-stu-id="f8c91-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="f8c91-113">弄指向元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="f8c91-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8c91-114">备注</span><span class="sxs-lookup"><span data-stu-id="f8c91-114">Remarks</span></span>  
 <span data-ttu-id="f8c91-115">清单中只能定义一个 `Assembly` 的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="f8c91-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8c91-116">要求</span><span class="sxs-lookup"><span data-stu-id="f8c91-116">Requirements</span></span>  
 <span data-ttu-id="f8c91-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f8c91-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8c91-118">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f8c91-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8c91-119">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f8c91-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8c91-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8c91-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c91-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8c91-121">See also</span></span>

- [<span data-ttu-id="f8c91-122">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f8c91-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
