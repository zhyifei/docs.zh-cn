---
title: "IMetaDataAssemblyImport::FindManifestResourceByName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindManifestResourceByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 492f8a50c421df56d1b2f79d15d86ef3251b401e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="5f691-102">IMetaDataAssemblyImport::FindManifestResourceByName 方法</span><span class="sxs-lookup"><span data-stu-id="5f691-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="5f691-103">获取具有指定名称的清单资源的指针。</span><span class="sxs-lookup"><span data-stu-id="5f691-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f691-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f691-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f691-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f691-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5f691-106">[in]资源的名称。</span><span class="sxs-lookup"><span data-stu-id="5f691-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="5f691-107">[out]用于存储数组`mdManifestResource`元数据标记，其中每个表示清单资源。</span><span class="sxs-lookup"><span data-stu-id="5f691-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f691-108">备注</span><span class="sxs-lookup"><span data-stu-id="5f691-108">Remarks</span></span>  
 <span data-ttu-id="5f691-109">`FindManifestResourceByName`方法使用由解析的引用的公共语言运行时的标准规则。</span><span class="sxs-lookup"><span data-stu-id="5f691-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f691-110">要求</span><span class="sxs-lookup"><span data-stu-id="5f691-110">Requirements</span></span>  
 <span data-ttu-id="5f691-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f691-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f691-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f691-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f691-113">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5f691-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f691-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f691-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f691-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f691-115">See Also</span></span>  
 [<span data-ttu-id="5f691-116">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="5f691-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="5f691-117">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="5f691-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
