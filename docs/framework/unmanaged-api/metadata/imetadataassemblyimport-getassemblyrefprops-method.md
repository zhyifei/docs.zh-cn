---
title: IMetaDataAssemblyImport::GetAssemblyRefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 2858e924ab6effe192955ce53dad9d333d2d244d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009062"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="fe006-102">IMetaDataAssemblyImport::GetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="fe006-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="fe006-103">获取具有指定元数据签名的程序集引用的属性集。</span><span class="sxs-lookup"><span data-stu-id="fe006-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe006-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe006-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe006-105">参数</span><span class="sxs-lookup"><span data-stu-id="fe006-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="fe006-106">中`mdAssemblyRef`表示要获取其属性的程序集引用的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="fe006-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="fe006-107">弄指向公钥或元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="fe006-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="fe006-108">弄返回的公钥或令牌中的字节数。</span><span class="sxs-lookup"><span data-stu-id="fe006-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="fe006-109">弄程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="fe006-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fe006-110">中的大小（宽字符） `szName` 。</span><span class="sxs-lookup"><span data-stu-id="fe006-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="fe006-111">弄一个指针，指向在中实际返回的宽字符数 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="fe006-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="fe006-112">弄指向 ASSEMBLYMETADATA 结构的指针，该结构包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="fe006-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="fe006-113">弄指向哈希值的指针。</span><span class="sxs-lookup"><span data-stu-id="fe006-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="fe006-114">这是所引用程序集的属性的哈希，使用 SHA-1 算法， `PublicKey` 除非已设置[AssemblyRefFlags](assemblyrefflags-enumeration.md)枚举的 arfFullOriginator 标志。</span><span class="sxs-lookup"><span data-stu-id="fe006-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="fe006-115">弄返回的哈希值中的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="fe006-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="fe006-116">弄一个指针，指向用于描述应用于程序集的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="fe006-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="fe006-117">Flags 值是一个或多个[CorAssemblyFlags](corassemblyflags-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="fe006-117">The flags value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe006-118">返回值</span><span class="sxs-lookup"><span data-stu-id="fe006-118">Return Value</span></span>  
 <span data-ttu-id="fe006-119">如果成功，则此方法返回 S_OK;否则，它将返回在 Winerror.h 头文件中定义的错误代码之一。</span><span class="sxs-lookup"><span data-stu-id="fe006-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe006-120">要求</span><span class="sxs-lookup"><span data-stu-id="fe006-120">Requirements</span></span>  
 <span data-ttu-id="fe006-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe006-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe006-122">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="fe006-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe006-123">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fe006-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe006-124">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe006-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe006-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe006-125">See also</span></span>

- [<span data-ttu-id="fe006-126">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="fe006-126">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
