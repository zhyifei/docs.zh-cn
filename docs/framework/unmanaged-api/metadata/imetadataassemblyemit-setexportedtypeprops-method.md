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
ms.openlocfilehash: ae682c354a7a5188611b103008a3e18f8d821260
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431940"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="30966-102">IMetaDataAssemblyEmit::SetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="30966-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="30966-103">修改指定的 `ExportedType` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="30966-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30966-104">语法</span><span class="sxs-lookup"><span data-stu-id="30966-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30966-105">参数</span><span class="sxs-lookup"><span data-stu-id="30966-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="30966-106">中用于指定要修改的 `ExportedType` 元数据结构的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="30966-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="30966-107">中标记类型 `File`、`AssemblyRef`或 `ExportedType`指定如何实现此类型。</span><span class="sxs-lookup"><span data-stu-id="30966-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="30966-108">中在代码文件中引用 `TypeDef` 标记。</span><span class="sxs-lookup"><span data-stu-id="30966-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="30966-109">中值的按位组合，用于指定类型的特性。</span><span class="sxs-lookup"><span data-stu-id="30966-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30966-110">备注</span><span class="sxs-lookup"><span data-stu-id="30966-110">Remarks</span></span>  
 <span data-ttu-id="30966-111">若要创建 `ExportedType` 元数据结构，请使用[IMetaDataAssemblyEmit：:D efineexportedtype](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="30966-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30966-112">要求</span><span class="sxs-lookup"><span data-stu-id="30966-112">Requirements</span></span>  
 <span data-ttu-id="30966-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="30966-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30966-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="30966-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30966-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="30966-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30966-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30966-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30966-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30966-117">See also</span></span>

- [<span data-ttu-id="30966-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="30966-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
