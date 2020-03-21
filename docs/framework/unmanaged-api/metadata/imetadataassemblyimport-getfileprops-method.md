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
ms.openlocfilehash: dae4a36537eeac58ffb17ebc1b78d935ec807cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175975"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="b5bd3-102">IMetaDataAssemblyImport::GetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="b5bd3-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="b5bd3-103">使用指定的元数据签名获取文件的属性。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5bd3-104">语法</span><span class="sxs-lookup"><span data-stu-id="b5bd3-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="b5bd3-105">parameters</span><span class="sxs-lookup"><span data-stu-id="b5bd3-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="b5bd3-106">[在]表示`mdFile`要为其获取属性的文件的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="b5bd3-107">[出]文件的简单名称。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b5bd3-108">[在]大字符的大小`szName`。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b5bd3-109">[出]中实际返回的宽字符数`szName`。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="b5bd3-110">[出]指向哈希值的指针。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="b5bd3-111">这是使用 SHA-1 算法的文件哈希。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="b5bd3-112">[出]返回的哈希值中的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="b5bd3-113">[出]指向描述应用于文件的元数据的标志的指针。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="b5bd3-114">标志值是一个或多个[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5bd3-115">要求</span><span class="sxs-lookup"><span data-stu-id="b5bd3-115">Requirements</span></span>  
 <span data-ttu-id="b5bd3-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b5bd3-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5bd3-117">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="b5bd3-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5bd3-118">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b5bd3-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5bd3-119">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5bd3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5bd3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5bd3-120">See also</span></span>

- [<span data-ttu-id="b5bd3-121">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="b5bd3-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
