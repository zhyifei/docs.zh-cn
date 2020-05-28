---
title: IMetaDataAssemblyImport::FindManifestResourceByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
ms.openlocfilehash: ef6f7a1a6e86b45acce91792385bc3761dfb4c39
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009075"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="b917a-102">IMetaDataAssemblyImport::FindManifestResourceByName 方法</span><span class="sxs-lookup"><span data-stu-id="b917a-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="b917a-103">获取一个指针，该指针指向具有指定名称的清单资源。</span><span class="sxs-lookup"><span data-stu-id="b917a-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b917a-104">语法</span><span class="sxs-lookup"><span data-stu-id="b917a-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="b917a-105">参数</span><span class="sxs-lookup"><span data-stu-id="b917a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="b917a-106">中资源的名称。</span><span class="sxs-lookup"><span data-stu-id="b917a-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="b917a-107">弄用于存储 `mdManifestResource` 元数据标记的数组，其中每个标记表示一个清单资源。</span><span class="sxs-lookup"><span data-stu-id="b917a-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b917a-108">备注</span><span class="sxs-lookup"><span data-stu-id="b917a-108">Remarks</span></span>  
 <span data-ttu-id="b917a-109">`FindManifestResourceByName`方法使用公共语言运行时所使用的标准规则来解析引用。</span><span class="sxs-lookup"><span data-stu-id="b917a-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b917a-110">要求</span><span class="sxs-lookup"><span data-stu-id="b917a-110">Requirements</span></span>  
 <span data-ttu-id="b917a-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b917a-111">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b917a-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="b917a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b917a-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b917a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b917a-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b917a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b917a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b917a-115">See also</span></span>

- [<span data-ttu-id="b917a-116">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="b917a-116">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="b917a-117">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="b917a-117">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
