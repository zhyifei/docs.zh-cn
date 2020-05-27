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
ms.openlocfilehash: a90deaf3e9ddf326c6fca558cbb4681fc40e022d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009049"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="3f027-102">IMetaDataAssemblyImport::GetAssemblyProps 方法</span><span class="sxs-lookup"><span data-stu-id="3f027-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="3f027-103">获取具有指定元数据签名的程序集的属性集。</span><span class="sxs-lookup"><span data-stu-id="3f027-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f027-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f027-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3f027-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f027-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="3f027-106">[in]。</span><span class="sxs-lookup"><span data-stu-id="3f027-106">[in].</span></span> <span data-ttu-id="3f027-107">`mdAssembly`表示要获取其属性的程序集的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3f027-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="3f027-108">弄指向公钥或元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="3f027-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="3f027-109">弄返回的公钥中的字节数。</span><span class="sxs-lookup"><span data-stu-id="3f027-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="3f027-110">弄一个指针，指向用于对程序集中的文件进行哈希处理的算法。</span><span class="sxs-lookup"><span data-stu-id="3f027-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="3f027-111">弄程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="3f027-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3f027-112">中的大小（宽字符） `szName` 。</span><span class="sxs-lookup"><span data-stu-id="3f027-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="3f027-113">弄中实际返回的宽字符数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="3f027-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="3f027-114">弄指向 ASSEMBLYMETADATA 结构的指针，该结构包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="3f027-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="3f027-115">弄描述应用于程序集的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="3f027-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="3f027-116">此值是一个或多个[CorAssemblyFlags](corassemblyflags-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="3f027-116">This value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f027-117">要求</span><span class="sxs-lookup"><span data-stu-id="3f027-117">Requirements</span></span>  
 <span data-ttu-id="3f027-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f027-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f027-119">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="3f027-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f027-120">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3f027-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f027-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f027-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f027-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f027-122">See also</span></span>

- [<span data-ttu-id="3f027-123">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="3f027-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
