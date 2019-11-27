---
title: IMetaDataAssemblyImport::GetAssemblyProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: c3c57074ae53e2e1d8d41aa04cb6eb6089db58b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449442"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="558ba-102">IMetaDataAssemblyImport::GetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="558ba-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="558ba-103">获取具有指定元数据签名的程序集的属性集。</span><span class="sxs-lookup"><span data-stu-id="558ba-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558ba-104">语法</span><span class="sxs-lookup"><span data-stu-id="558ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="558ba-105">参数</span><span class="sxs-lookup"><span data-stu-id="558ba-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="558ba-106">[in]。</span><span class="sxs-lookup"><span data-stu-id="558ba-106">[in].</span></span> <span data-ttu-id="558ba-107">`mdAssembly` 元数据标记，它表示要获取其属性的程序集。</span><span class="sxs-lookup"><span data-stu-id="558ba-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="558ba-108">弄指向公钥或元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="558ba-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="558ba-109">弄返回的公钥中的字节数。</span><span class="sxs-lookup"><span data-stu-id="558ba-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="558ba-110">弄一个指针，指向用于对程序集中的文件进行哈希处理的算法。</span><span class="sxs-lookup"><span data-stu-id="558ba-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="558ba-111">弄程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="558ba-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="558ba-112">中`szName`的大小（宽字符）。</span><span class="sxs-lookup"><span data-stu-id="558ba-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="558ba-113">弄`szName`中实际返回的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="558ba-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="558ba-114">弄指向 ASSEMBLYMETADATA 结构的指针，该结构包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="558ba-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="558ba-115">弄描述应用于程序集的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="558ba-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="558ba-116">此值是一个或多个[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="558ba-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="558ba-117">要求</span><span class="sxs-lookup"><span data-stu-id="558ba-117">Requirements</span></span>  
 <span data-ttu-id="558ba-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="558ba-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="558ba-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="558ba-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="558ba-120">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="558ba-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="558ba-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="558ba-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558ba-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="558ba-122">See also</span></span>

- [<span data-ttu-id="558ba-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="558ba-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
