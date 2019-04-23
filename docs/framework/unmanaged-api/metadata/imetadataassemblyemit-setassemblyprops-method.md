---
title: IMetaDataAssemblyEmit::SetAssemblyProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3361212f9a7f7ff0739e8544419a2b67abc8f457
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214645"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="3a7d3-102">IMetaDataAssemblyEmit::SetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="3a7d3-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="3a7d3-103">修改指定的 `Assembly` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a7d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a7d3-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a7d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="3a7d3-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="3a7d3-106">[in]指定的元数据标记`Assembly`要修改的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="3a7d3-107">[in]指向程序集的发布服务器的公钥的指针。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="3a7d3-108">[in]以字节为单位的大小`pbPublicKey`。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="3a7d3-109">[in]使用程序集文件进行哈希的哈希算法标识符。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="3a7d3-110">[in]用户可读文本的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="3a7d3-111">[in]指向包含程序集的版本、 平台和区域设置信息 ASSEMBLYMETADATA 的指针。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="3a7d3-112">[in]按位组合[AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)指定程序集的各种属性的值。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a7d3-113">备注</span><span class="sxs-lookup"><span data-stu-id="3a7d3-113">Remarks</span></span>  
 <span data-ttu-id="3a7d3-114">若要创建`Assembly`元数据结构，使用[imetadataassemblyemit:: Defineassembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a7d3-115">要求</span><span class="sxs-lookup"><span data-stu-id="3a7d3-115">Requirements</span></span>  
 <span data-ttu-id="3a7d3-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a7d3-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a7d3-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a7d3-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a7d3-118">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3a7d3-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a7d3-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a7d3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a7d3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a7d3-120">See also</span></span>

- [<span data-ttu-id="3a7d3-121">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="3a7d3-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
