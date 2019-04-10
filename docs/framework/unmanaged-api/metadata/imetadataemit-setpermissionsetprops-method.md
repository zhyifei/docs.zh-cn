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
ms.openlocfilehash: 510c33b8e0e26bead00dcb85a6ceba102a5f267d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163769"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="40643-102">IMetaDataEmit::SetPermissionSetProps 方法</span><span class="sxs-lookup"><span data-stu-id="40643-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="40643-103">设置或更新功能的调用之前定义的权限集的元数据签名[imetadataemit:: Definepermissionset](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)。</span><span class="sxs-lookup"><span data-stu-id="40643-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40643-104">语法</span><span class="sxs-lookup"><span data-stu-id="40643-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40643-105">参数</span><span class="sxs-lookup"><span data-stu-id="40643-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="40643-106">[in]表示要进行修饰的对象的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="40643-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="40643-107">[in]一个[CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)值，该值指定要使用的声明性安全的类型。</span><span class="sxs-lookup"><span data-stu-id="40643-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="40643-108">[in]BLOB 的权限。</span><span class="sxs-lookup"><span data-stu-id="40643-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="40643-109">[in]大小，以字节为单位的`pvPermission`。</span><span class="sxs-lookup"><span data-stu-id="40643-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="40643-110">[out]`mdPermission`元数据标记所表示的已更新的权限。</span><span class="sxs-lookup"><span data-stu-id="40643-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40643-111">要求</span><span class="sxs-lookup"><span data-stu-id="40643-111">Requirements</span></span>  
 <span data-ttu-id="40643-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40643-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40643-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="40643-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40643-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="40643-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="40643-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="40643-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="40643-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="40643-116">See also</span></span>

- [<span data-ttu-id="40643-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="40643-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="40643-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="40643-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
