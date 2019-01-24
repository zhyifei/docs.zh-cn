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
ms.openlocfilehash: b05c9a75bf870dd3b2316d2df7c50932b26894f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702738"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="4cd21-102">IMetaDataAssemblyImport::FindManifestResourceByName 方法</span><span class="sxs-lookup"><span data-stu-id="4cd21-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="4cd21-103">获取一个指针指向清单资源具有指定名称。</span><span class="sxs-lookup"><span data-stu-id="4cd21-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd21-104">语法</span><span class="sxs-lookup"><span data-stu-id="4cd21-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cd21-105">参数</span><span class="sxs-lookup"><span data-stu-id="4cd21-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="4cd21-106">[in]资源的名称。</span><span class="sxs-lookup"><span data-stu-id="4cd21-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="4cd21-107">[out]用于存储数组`mdManifestResource`元数据标记，其中每个表示清单资源。</span><span class="sxs-lookup"><span data-stu-id="4cd21-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4cd21-108">备注</span><span class="sxs-lookup"><span data-stu-id="4cd21-108">Remarks</span></span>  
 <span data-ttu-id="4cd21-109">`FindManifestResourceByName`方法使用由公共语言运行时解析引用的标准规则。</span><span class="sxs-lookup"><span data-stu-id="4cd21-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cd21-110">要求</span><span class="sxs-lookup"><span data-stu-id="4cd21-110">Requirements</span></span>  
 <span data-ttu-id="4cd21-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd21-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cd21-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4cd21-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4cd21-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4cd21-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4cd21-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cd21-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd21-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cd21-115">See also</span></span>
- [<span data-ttu-id="4cd21-116">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="4cd21-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="4cd21-117">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="4cd21-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
