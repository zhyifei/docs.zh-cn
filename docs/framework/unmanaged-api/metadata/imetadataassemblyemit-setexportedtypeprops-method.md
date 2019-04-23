---
title: IMetaDataAssemblyEmit::SetExportedTypeProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c09140488730179616d11932faa3542f704958a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123729"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="50042-102">IMetaDataAssemblyEmit::SetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="50042-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="50042-103">修改指定的 `ExportedType` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="50042-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50042-104">语法</span><span class="sxs-lookup"><span data-stu-id="50042-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50042-105">参数</span><span class="sxs-lookup"><span data-stu-id="50042-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="50042-106">[in]指定的元数据标记`ExportedType`要修改的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="50042-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="50042-107">[in]类型的标记`File`， `AssemblyRef`，或`ExportedType`，指定此类型的实现方式。</span><span class="sxs-lookup"><span data-stu-id="50042-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="50042-108">[in]`TypeDef`代码文件中引用的令牌。</span><span class="sxs-lookup"><span data-stu-id="50042-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="50042-109">[in]指定类型的属性的值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="50042-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50042-110">备注</span><span class="sxs-lookup"><span data-stu-id="50042-110">Remarks</span></span>  
 <span data-ttu-id="50042-111">若要创建`ExportedType`元数据结构，使用[imetadataassemblyemit:: Defineexportedtype](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="50042-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50042-112">要求</span><span class="sxs-lookup"><span data-stu-id="50042-112">Requirements</span></span>  
 <span data-ttu-id="50042-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50042-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50042-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="50042-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50042-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="50042-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50042-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50042-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50042-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="50042-117">See also</span></span>

- [<span data-ttu-id="50042-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="50042-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
