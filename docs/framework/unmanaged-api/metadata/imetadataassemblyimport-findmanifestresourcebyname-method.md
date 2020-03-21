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
ms.openlocfilehash: ae9097725aecd21e910e49a78d81951df39e9b2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177774"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="5de77-102">IMetaDataAssemblyImport::FindManifestResourceByName 方法</span><span class="sxs-lookup"><span data-stu-id="5de77-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="5de77-103">获取指向具有指定名称的清单资源的指针。</span><span class="sxs-lookup"><span data-stu-id="5de77-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de77-104">语法</span><span class="sxs-lookup"><span data-stu-id="5de77-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="5de77-105">parameters</span><span class="sxs-lookup"><span data-stu-id="5de77-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5de77-106">[在]资源的名称。</span><span class="sxs-lookup"><span data-stu-id="5de77-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="5de77-107">[出]用于存储元数据令牌的`mdManifestResource`数组，每个令牌都表示一个清单资源。</span><span class="sxs-lookup"><span data-stu-id="5de77-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5de77-108">备注</span><span class="sxs-lookup"><span data-stu-id="5de77-108">Remarks</span></span>  
 <span data-ttu-id="5de77-109">该方法`FindManifestResourceByName`使用通用语言运行时采用的标准规则来解决引用。</span><span class="sxs-lookup"><span data-stu-id="5de77-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de77-110">要求</span><span class="sxs-lookup"><span data-stu-id="5de77-110">Requirements</span></span>  
 <span data-ttu-id="5de77-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5de77-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de77-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="5de77-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5de77-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5de77-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5de77-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de77-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de77-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5de77-115">See also</span></span>

- [<span data-ttu-id="5de77-116">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="5de77-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="5de77-117">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="5de77-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
