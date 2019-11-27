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
ms.openlocfilehash: 4149db74adfa26df221eed5c590766a023bb105e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448222"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="9cef7-102">IMetaDataAssemblyImport::GetAssemblyRefProps 方法</span><span class="sxs-lookup"><span data-stu-id="9cef7-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="9cef7-103">获取具有指定元数据签名的程序集引用的属性集。</span><span class="sxs-lookup"><span data-stu-id="9cef7-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cef7-104">语法</span><span class="sxs-lookup"><span data-stu-id="9cef7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9cef7-105">参数</span><span class="sxs-lookup"><span data-stu-id="9cef7-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="9cef7-106">中`mdAssemblyRef` 元数据标记，它表示要获取其属性的程序集引用。</span><span class="sxs-lookup"><span data-stu-id="9cef7-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="9cef7-107">弄指向公钥或元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="9cef7-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="9cef7-108">弄返回的公钥或令牌中的字节数。</span><span class="sxs-lookup"><span data-stu-id="9cef7-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="9cef7-109">弄程序集的简单名称。</span><span class="sxs-lookup"><span data-stu-id="9cef7-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9cef7-110">中`szName`的大小（宽字符）。</span><span class="sxs-lookup"><span data-stu-id="9cef7-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="9cef7-111">弄一个指针，指向 `szName`中实际返回的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="9cef7-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="9cef7-112">弄指向 ASSEMBLYMETADATA 结构的指针，该结构包含程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="9cef7-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="9cef7-113">弄指向哈希值的指针。</span><span class="sxs-lookup"><span data-stu-id="9cef7-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="9cef7-114">这是所引用程序集的 `PublicKey` 属性的哈希，使用 SHA-1 算法，除非已设置[AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)枚举的 arfFullOriginator 标志。</span><span class="sxs-lookup"><span data-stu-id="9cef7-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="9cef7-115">弄返回的哈希值中的宽字符数。</span><span class="sxs-lookup"><span data-stu-id="9cef7-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="9cef7-116">弄一个指针，指向用于描述应用于程序集的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="9cef7-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="9cef7-117">Flags 值是一个或多个[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值的组合。</span><span class="sxs-lookup"><span data-stu-id="9cef7-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cef7-118">返回值</span><span class="sxs-lookup"><span data-stu-id="9cef7-118">Return Value</span></span>  
 <span data-ttu-id="9cef7-119">如果成功，则此方法返回 S_OK;否则，它将返回在 Winerror.h 头文件中定义的错误代码之一。</span><span class="sxs-lookup"><span data-stu-id="9cef7-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cef7-120">要求</span><span class="sxs-lookup"><span data-stu-id="9cef7-120">Requirements</span></span>  
 <span data-ttu-id="9cef7-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cef7-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cef7-122">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="9cef7-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9cef7-123">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9cef7-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9cef7-124">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cef7-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cef7-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cef7-125">See also</span></span>

- [<span data-ttu-id="9cef7-126">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="9cef7-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
