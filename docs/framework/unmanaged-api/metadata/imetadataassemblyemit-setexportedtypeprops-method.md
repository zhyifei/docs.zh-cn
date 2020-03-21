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
ms.openlocfilehash: dd1d6f1da6e49837eebd9356500f403c199b011b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177856"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="67178-102">IMetaDataAssemblyEmit::SetExportedTypeProps 方法</span><span class="sxs-lookup"><span data-stu-id="67178-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="67178-103">修改指定的 `ExportedType` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="67178-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67178-104">语法</span><span class="sxs-lookup"><span data-stu-id="67178-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67178-105">parameters</span><span class="sxs-lookup"><span data-stu-id="67178-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="67178-106">[在]指定要修改的`ExportedType`元数据结构的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="67178-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="67178-107">[在]指定如何实现此类型的`File`令牌`AssemblyRef`的类型`ExportedType`。</span><span class="sxs-lookup"><span data-stu-id="67178-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="67178-108">[在]代码`TypeDef`文件中引用的令牌。</span><span class="sxs-lookup"><span data-stu-id="67178-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="67178-109">[在]指定类型属性的值的位组合。</span><span class="sxs-lookup"><span data-stu-id="67178-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67178-110">备注</span><span class="sxs-lookup"><span data-stu-id="67178-110">Remarks</span></span>  
 <span data-ttu-id="67178-111">要创建`ExportedType`元数据结构，请使用[IMetaDataAssemblyEmit：:Defineexportetype 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="67178-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67178-112">要求</span><span class="sxs-lookup"><span data-stu-id="67178-112">Requirements</span></span>  
 <span data-ttu-id="67178-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67178-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67178-114">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="67178-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67178-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="67178-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67178-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67178-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67178-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67178-117">See also</span></span>

- [<span data-ttu-id="67178-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="67178-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
