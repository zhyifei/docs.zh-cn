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
ms.openlocfilehash: e5fff28e1c2c0d31285c9621c184a44355813a03
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479683"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="fd998-102">IMetaDataAssemblyEmit::SetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="fd998-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="fd998-103">修改指定的 `ExportedType` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="fd998-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd998-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd998-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd998-105">参数</span><span class="sxs-lookup"><span data-stu-id="fd998-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="fd998-106">[in]指定的元数据标记`ExportedType`要修改的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="fd998-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="fd998-107">[in]类型的标记`File`， `AssemblyRef`，或`ExportedType`，指定此类型的实现方式。</span><span class="sxs-lookup"><span data-stu-id="fd998-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="fd998-108">[in]`TypeDef`代码文件中引用的令牌。</span><span class="sxs-lookup"><span data-stu-id="fd998-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="fd998-109">[in]指定类型的属性的值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="fd998-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd998-110">备注</span><span class="sxs-lookup"><span data-stu-id="fd998-110">Remarks</span></span>  
 <span data-ttu-id="fd998-111">若要创建`ExportedType`元数据结构，使用[imetadataassemblyemit:: Defineexportedtype](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fd998-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd998-112">要求</span><span class="sxs-lookup"><span data-stu-id="fd998-112">Requirements</span></span>  
 <span data-ttu-id="fd998-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd998-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd998-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fd998-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd998-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fd998-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd998-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd998-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd998-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd998-117">See also</span></span>
- [<span data-ttu-id="fd998-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="fd998-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
