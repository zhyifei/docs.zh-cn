---
title: IMetaDataAssemblyImport::FindExportedTypeByName 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
ms.openlocfilehash: ac6de9a16fad6ba9d14f3960ddd28c42c111f254
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009387"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="7d004-102">IMetaDataAssemblyImport::FindExportedTypeByName 方法</span><span class="sxs-lookup"><span data-stu-id="7d004-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="7d004-103">获取一个指针，该指针指向导出的类型（给定其名称和封闭类型）。</span><span class="sxs-lookup"><span data-stu-id="7d004-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d004-104">语法</span><span class="sxs-lookup"><span data-stu-id="7d004-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d004-105">参数</span><span class="sxs-lookup"><span data-stu-id="7d004-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="7d004-106">中导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="7d004-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="7d004-107">中导出类型的封闭类的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="7d004-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="7d004-108">`mdExportedTypeNil`如果请求的导出类型不是嵌套类型，则此值为。</span><span class="sxs-lookup"><span data-stu-id="7d004-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="7d004-109">弄一个指针，指向 `mdExportedType` 表示导出类型的标记。</span><span class="sxs-lookup"><span data-stu-id="7d004-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d004-110">备注</span><span class="sxs-lookup"><span data-stu-id="7d004-110">Remarks</span></span>  
 <span data-ttu-id="7d004-111">`FindExportedTypeByName`方法使用公共语言运行时所使用的标准规则来解析引用。</span><span class="sxs-lookup"><span data-stu-id="7d004-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d004-112">要求</span><span class="sxs-lookup"><span data-stu-id="7d004-112">Requirements</span></span>  
 <span data-ttu-id="7d004-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d004-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d004-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="7d004-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d004-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7d004-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d004-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d004-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d004-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d004-117">See also</span></span>

- [<span data-ttu-id="7d004-118">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="7d004-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="7d004-119">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="7d004-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
