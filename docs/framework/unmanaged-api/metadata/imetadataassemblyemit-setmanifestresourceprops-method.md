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
ms.openlocfilehash: 74111a175b0decbc1beef7c8df5ade59d31d845b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009140"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="ad6d9-102">IMetaDataAssemblyEmit::SetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="ad6d9-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="ad6d9-103">修改指定的 `ManifestResource` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="ad6d9-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad6d9-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad6d9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad6d9-105">参数</span><span class="sxs-lookup"><span data-stu-id="ad6d9-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="ad6d9-106">中`ManifestResource`用于指定要修改的元数据结构的标记。</span><span class="sxs-lookup"><span data-stu-id="ad6d9-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="ad6d9-107">中`File` `AssemblyRef` 映射到资源提供程序的标记，类型为或。</span><span class="sxs-lookup"><span data-stu-id="ad6d9-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="ad6d9-108">中文件中资源的起始位置的偏移量。</span><span class="sxs-lookup"><span data-stu-id="ad6d9-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="ad6d9-109">中指定资源特性的标志值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="ad6d9-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad6d9-110">备注</span><span class="sxs-lookup"><span data-stu-id="ad6d9-110">Remarks</span></span>  
 <span data-ttu-id="ad6d9-111">若要创建 `ManifestResource` 元数据结构，请使用[IMetaDataAssemblyEmit：:D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ad6d9-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad6d9-112">要求</span><span class="sxs-lookup"><span data-stu-id="ad6d9-112">Requirements</span></span>  
 <span data-ttu-id="ad6d9-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad6d9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad6d9-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="ad6d9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad6d9-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ad6d9-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad6d9-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad6d9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad6d9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad6d9-117">See also</span></span>

- [<span data-ttu-id="ad6d9-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="ad6d9-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
