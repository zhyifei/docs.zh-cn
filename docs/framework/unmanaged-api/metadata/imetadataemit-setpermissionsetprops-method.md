---
title: IMetaDataEmit::SetPermissionSetProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8a4d3b7014d0da88e83b507c39c039d39ba93d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542673"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="e26a2-102">IMetaDataEmit::SetPermissionSetProps 方法</span><span class="sxs-lookup"><span data-stu-id="e26a2-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="e26a2-103">设置或更新功能的调用之前定义的权限集的元数据签名[imetadataemit:: Definepermissionset](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)。</span><span class="sxs-lookup"><span data-stu-id="e26a2-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e26a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="e26a2-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e26a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="e26a2-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e26a2-106">[in]表示要进行修饰的对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="e26a2-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="e26a2-107">[in]一个[CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)值，该值指定要使用的声明性安全的类型。</span><span class="sxs-lookup"><span data-stu-id="e26a2-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="e26a2-108">[in]BLOB 的权限。</span><span class="sxs-lookup"><span data-stu-id="e26a2-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="e26a2-109">[in]大小，以字节为单位的`pvPermission`。</span><span class="sxs-lookup"><span data-stu-id="e26a2-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="e26a2-110">[out]`mdPermission`元数据标记所表示的已更新的权限。</span><span class="sxs-lookup"><span data-stu-id="e26a2-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e26a2-111">要求</span><span class="sxs-lookup"><span data-stu-id="e26a2-111">Requirements</span></span>  
 <span data-ttu-id="e26a2-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e26a2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e26a2-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e26a2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e26a2-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e26a2-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e26a2-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e26a2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26a2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e26a2-116">See also</span></span>
- [<span data-ttu-id="e26a2-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="e26a2-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e26a2-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="e26a2-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
