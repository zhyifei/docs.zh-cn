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
ms.openlocfilehash: de4cfdf2a9353eebdebaf4df9e481d06d776ff04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177492"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="edfac-102">IMetaDataEmit::SetPermissionSetProps 方法</span><span class="sxs-lookup"><span data-stu-id="edfac-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="edfac-103">设置或更新由之前调用[IMetaDataEmit：:Define许可集](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)定义的权限集的元数据签名的功能。</span><span class="sxs-lookup"><span data-stu-id="edfac-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edfac-104">语法</span><span class="sxs-lookup"><span data-stu-id="edfac-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edfac-105">parameters</span><span class="sxs-lookup"><span data-stu-id="edfac-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="edfac-106">[在]表示要修饰的对象的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="edfac-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="edfac-107">[在]指定要使用的声明性安全性类型的[CorDecl 安全](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="edfac-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="edfac-108">[在]权限 BLOB。</span><span class="sxs-lookup"><span data-stu-id="edfac-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="edfac-109">[在]的大小（以字节为单位）的大小`pvPermission`。</span><span class="sxs-lookup"><span data-stu-id="edfac-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="edfac-110">[出]表示`mdPermission`更新权限的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="edfac-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edfac-111">要求</span><span class="sxs-lookup"><span data-stu-id="edfac-111">Requirements</span></span>  
 <span data-ttu-id="edfac-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="edfac-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edfac-113">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="edfac-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edfac-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="edfac-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edfac-115">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edfac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edfac-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edfac-116">See also</span></span>

- [<span data-ttu-id="edfac-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="edfac-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="edfac-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="edfac-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
