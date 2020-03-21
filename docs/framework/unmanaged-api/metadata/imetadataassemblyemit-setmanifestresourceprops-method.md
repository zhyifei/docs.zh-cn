---
title: IMetaDataAssemblyEmit::SetManifestResourceProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
ms.openlocfilehash: 9370b27fd385b0223b354365d64aa57048f4ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177845"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="f03d2-102">IMetaDataAssemblyEmit::SetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="f03d2-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="f03d2-103">修改指定的 `ManifestResource` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="f03d2-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="f03d2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f03d2-105">parameters</span><span class="sxs-lookup"><span data-stu-id="f03d2-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="f03d2-106">[在]指定要修改的`ManifestResource`元数据结构的令牌。</span><span class="sxs-lookup"><span data-stu-id="f03d2-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="f03d2-107">[在]映射到资源提供程序的令牌`File`类型`AssemblyRef`或 。</span><span class="sxs-lookup"><span data-stu-id="f03d2-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="f03d2-108">[在]文件中资源开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="f03d2-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="f03d2-109">[在]指定资源属性的标志值的位组合。</span><span class="sxs-lookup"><span data-stu-id="f03d2-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f03d2-110">备注</span><span class="sxs-lookup"><span data-stu-id="f03d2-110">Remarks</span></span>  
 <span data-ttu-id="f03d2-111">要创建`ManifestResource`元数据结构，请使用[IMetaDataAssemblyEmit：:DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f03d2-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f03d2-112">要求</span><span class="sxs-lookup"><span data-stu-id="f03d2-112">Requirements</span></span>  
 <span data-ttu-id="f03d2-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f03d2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f03d2-114">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="f03d2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f03d2-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f03d2-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f03d2-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f03d2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03d2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f03d2-117">See also</span></span>

- [<span data-ttu-id="f03d2-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f03d2-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
