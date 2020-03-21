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
ms.openlocfilehash: edfe5de9c9d7ef9607a2eea5146194bbd4393a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175988"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="42e07-102">IMetaDataAssemblyImport::FindExportedTypeByName 方法</span><span class="sxs-lookup"><span data-stu-id="42e07-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="42e07-103">获取指向导出类型的指针，给定其名称和封闭类型。</span><span class="sxs-lookup"><span data-stu-id="42e07-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e07-104">语法</span><span class="sxs-lookup"><span data-stu-id="42e07-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42e07-105">parameters</span><span class="sxs-lookup"><span data-stu-id="42e07-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="42e07-106">[在]导出类型的名称。</span><span class="sxs-lookup"><span data-stu-id="42e07-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="42e07-107">[在]导出类型的封闭类的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="42e07-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="42e07-108">此值是`mdExportedTypeNil`请求的导出类型不是嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="42e07-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="42e07-109">[出]指向表示导出类型的`mdExportedType`令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="42e07-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42e07-110">备注</span><span class="sxs-lookup"><span data-stu-id="42e07-110">Remarks</span></span>  
 <span data-ttu-id="42e07-111">该方法`FindExportedTypeByName`使用通用语言运行时采用的标准规则来解决引用。</span><span class="sxs-lookup"><span data-stu-id="42e07-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e07-112">要求</span><span class="sxs-lookup"><span data-stu-id="42e07-112">Requirements</span></span>  
 <span data-ttu-id="42e07-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="42e07-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e07-114">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="42e07-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42e07-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="42e07-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42e07-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e07-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e07-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42e07-117">See also</span></span>

- [<span data-ttu-id="42e07-118">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="42e07-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="42e07-119">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="42e07-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
