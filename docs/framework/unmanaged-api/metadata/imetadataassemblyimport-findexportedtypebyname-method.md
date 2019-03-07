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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7575659441b2eae37365c10050bca53e0cfdef6f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473911"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="1f929-102">IMetaDataAssemblyImport::FindExportedTypeByName 方法</span><span class="sxs-lookup"><span data-stu-id="1f929-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="1f929-103">获取一个指针指向导出的类型，在给定其名称和封闭类型。</span><span class="sxs-lookup"><span data-stu-id="1f929-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f929-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f929-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f929-105">参数</span><span class="sxs-lookup"><span data-stu-id="1f929-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="1f929-106">[in]导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="1f929-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="1f929-107">[in]用于导出的类型在封闭类的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="1f929-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="1f929-108">此值是`mdExportedTypeNil`如果请求的导出类型不是嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="1f929-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="1f929-109">[out]一个指向`mdExportedType`表示导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="1f929-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f929-110">备注</span><span class="sxs-lookup"><span data-stu-id="1f929-110">Remarks</span></span>  
 <span data-ttu-id="1f929-111">`FindExportedTypeByName`方法使用由公共语言运行时解析引用的标准规则。</span><span class="sxs-lookup"><span data-stu-id="1f929-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f929-112">要求</span><span class="sxs-lookup"><span data-stu-id="1f929-112">Requirements</span></span>  
 <span data-ttu-id="1f929-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1f929-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f929-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1f929-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1f929-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1f929-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1f929-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f929-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f929-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f929-117">See also</span></span>
- [<span data-ttu-id="1f929-118">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="1f929-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="1f929-119">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="1f929-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
