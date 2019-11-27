---
title: IMetaDataAssemblyImport::GetExportedTypeProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 82302124828a2dab73b445128d7d847e112edd36
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448217"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="2968c-102">IMetaDataAssemblyImport::GetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="2968c-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="2968c-103">获取具有指定元数据签名的导出类型的属性集。</span><span class="sxs-lookup"><span data-stu-id="2968c-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2968c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2968c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2968c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2968c-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="2968c-106">中一个 `mdExportedType` 元数据标记，它表示导出的类型。</span><span class="sxs-lookup"><span data-stu-id="2968c-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="2968c-107">弄导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="2968c-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2968c-108">中`szName`的大小（以宽字符为大小）。</span><span class="sxs-lookup"><span data-stu-id="2968c-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="2968c-109">弄`szName` 中实际返回的宽字符数</span><span class="sxs-lookup"><span data-stu-id="2968c-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="2968c-110">弄一个 `mdFile`、`mdAssemblyRef`或 `mdExportedType` 元数据标记，其中包含或允许访问导出的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="2968c-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="2968c-111">弄一个指针，指向表示文件中的类型的 `mdTypeDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="2968c-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="2968c-112">弄一个指针，指向用于描述应用于导出类型的元数据的标志。</span><span class="sxs-lookup"><span data-stu-id="2968c-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="2968c-113">Flags 值可以是一个或多个[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="2968c-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2968c-114">要求</span><span class="sxs-lookup"><span data-stu-id="2968c-114">Requirements</span></span>  
 <span data-ttu-id="2968c-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2968c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2968c-116">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="2968c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2968c-117">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2968c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2968c-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2968c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2968c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2968c-119">See also</span></span>

- [<span data-ttu-id="2968c-120">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="2968c-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
