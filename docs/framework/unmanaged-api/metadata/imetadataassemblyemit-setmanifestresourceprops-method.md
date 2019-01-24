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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d92129bd7c51ba2fa574f8337ba2b3727ab7b172
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599044"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="c2fb7-102">IMetaDataAssemblyEmit::SetManifestResourceProps 方法</span><span class="sxs-lookup"><span data-stu-id="c2fb7-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="c2fb7-103">修改指定的 `ManifestResource` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="c2fb7-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2fb7-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2fb7-104">Syntax</span></span>  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2fb7-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2fb7-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="c2fb7-106">[in]指定的令牌`ManifestResource`要修改的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="c2fb7-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="c2fb7-107">[in]类型的标记`File`或`AssemblyRef`，映射到资源提供程序。</span><span class="sxs-lookup"><span data-stu-id="c2fb7-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="c2fb7-108">[in]到文件中资源的开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="c2fb7-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="c2fb7-109">[in]指定资源的属性的标志值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="c2fb7-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2fb7-110">备注</span><span class="sxs-lookup"><span data-stu-id="c2fb7-110">Remarks</span></span>  
 <span data-ttu-id="c2fb7-111">若要创建`ManifestResource`元数据结构，使用[imetadataassemblyemit:: Definemanifestresource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c2fb7-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2fb7-112">要求</span><span class="sxs-lookup"><span data-stu-id="c2fb7-112">Requirements</span></span>  
 <span data-ttu-id="c2fb7-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2fb7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2fb7-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2fb7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2fb7-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c2fb7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2fb7-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2fb7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fb7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2fb7-117">See also</span></span>
- [<span data-ttu-id="c2fb7-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="c2fb7-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
