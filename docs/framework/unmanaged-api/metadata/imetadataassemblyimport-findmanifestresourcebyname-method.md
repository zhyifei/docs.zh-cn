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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf61da362251577acadb83915404eba7508b3099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141565"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="28391-102">IMetaDataAssemblyImport::FindManifestResourceByName 方法</span><span class="sxs-lookup"><span data-stu-id="28391-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="28391-103">获取一个指针指向清单资源具有指定名称。</span><span class="sxs-lookup"><span data-stu-id="28391-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28391-104">语法</span><span class="sxs-lookup"><span data-stu-id="28391-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="28391-105">参数</span><span class="sxs-lookup"><span data-stu-id="28391-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="28391-106">[in]资源的名称。</span><span class="sxs-lookup"><span data-stu-id="28391-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="28391-107">[out]用于存储数组`mdManifestResource`元数据标记，其中每个表示清单资源。</span><span class="sxs-lookup"><span data-stu-id="28391-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28391-108">备注</span><span class="sxs-lookup"><span data-stu-id="28391-108">Remarks</span></span>  
 <span data-ttu-id="28391-109">`FindManifestResourceByName`方法使用由公共语言运行时解析引用的标准规则。</span><span class="sxs-lookup"><span data-stu-id="28391-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28391-110">要求</span><span class="sxs-lookup"><span data-stu-id="28391-110">Requirements</span></span>  
 <span data-ttu-id="28391-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28391-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28391-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="28391-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28391-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="28391-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="28391-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="28391-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28391-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="28391-115">See also</span></span>

- [<span data-ttu-id="28391-116">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="28391-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="28391-117">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="28391-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
