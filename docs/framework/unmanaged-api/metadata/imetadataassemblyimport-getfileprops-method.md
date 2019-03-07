---
title: IMetaDataAssemblyImport::GetFileProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f42928e21ef04a7a0f030b1b9eee159ec6b0af4f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473950"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="486ca-102">IMetaDataAssemblyImport::GetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="486ca-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="486ca-103">获取具有指定的元数据签名文件的属性。</span><span class="sxs-lookup"><span data-stu-id="486ca-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="486ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="486ca-104">Syntax</span></span>  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="486ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="486ca-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="486ca-106">[in]`mdFile`表示要为其获取属性的文件的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="486ca-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="486ca-107">[out]简单文件的名称。</span><span class="sxs-lookup"><span data-stu-id="486ca-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="486ca-108">[in]大小，以宽字符为单位的`szName`。</span><span class="sxs-lookup"><span data-stu-id="486ca-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="486ca-109">[out]中实际返回的宽字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="486ca-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="486ca-110">[out]指向哈希值的指针。</span><span class="sxs-lookup"><span data-stu-id="486ca-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="486ca-111">这是使用 sha-1 算法，该文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="486ca-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="486ca-112">[out]中返回的哈希值的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="486ca-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="486ca-113">[out]指向描述应用于文件的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="486ca-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="486ca-114">标志值是一个或多个组合[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="486ca-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="486ca-115">要求</span><span class="sxs-lookup"><span data-stu-id="486ca-115">Requirements</span></span>  
 <span data-ttu-id="486ca-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="486ca-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="486ca-117">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="486ca-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="486ca-118">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="486ca-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="486ca-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="486ca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486ca-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="486ca-120">See also</span></span>
- [<span data-ttu-id="486ca-121">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="486ca-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
