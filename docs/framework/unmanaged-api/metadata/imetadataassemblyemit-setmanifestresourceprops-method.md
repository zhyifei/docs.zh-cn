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
ms.openlocfilehash: f6b5e12df60663b75e10b04eaa008a75d720d753
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434441"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="c3c9e-102">IMetaDataAssemblyEmit::SetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="c3c9e-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="c3c9e-103">修改指定的 `ManifestResource` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="c3c9e-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c9e-104">语法</span><span class="sxs-lookup"><span data-stu-id="c3c9e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3c9e-105">参数</span><span class="sxs-lookup"><span data-stu-id="c3c9e-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="c3c9e-106">中用于指定要修改的 `ManifestResource` 元数据结构的标记。</span><span class="sxs-lookup"><span data-stu-id="c3c9e-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="c3c9e-107">中映射到资源提供程序的 `File` 或 `AssemblyRef`类型的标记。</span><span class="sxs-lookup"><span data-stu-id="c3c9e-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="c3c9e-108">中文件中资源的起始位置的偏移量。</span><span class="sxs-lookup"><span data-stu-id="c3c9e-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="c3c9e-109">中指定资源特性的标志值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="c3c9e-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3c9e-110">备注</span><span class="sxs-lookup"><span data-stu-id="c3c9e-110">Remarks</span></span>  
 <span data-ttu-id="c3c9e-111">若要创建 `ManifestResource` 元数据结构，请使用[IMetaDataAssemblyEmit：:D efinemanifestresource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c3c9e-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3c9e-112">要求</span><span class="sxs-lookup"><span data-stu-id="c3c9e-112">Requirements</span></span>  
 <span data-ttu-id="c3c9e-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c9e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3c9e-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="c3c9e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3c9e-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c3c9e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3c9e-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3c9e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c9e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3c9e-117">See also</span></span>

- [<span data-ttu-id="c3c9e-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="c3c9e-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
