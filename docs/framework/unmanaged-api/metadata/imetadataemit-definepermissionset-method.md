---
title: IMetaDataEmit::DefinePermissionSet 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: a0fd3fdb6dde9fd6b88ea6c64ed907c8a3e9e46d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175793"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="6761c-102">IMetaDataEmit::DefinePermissionSet 方法</span><span class="sxs-lookup"><span data-stu-id="6761c-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="6761c-103">为具有指定元数据签名的权限集创建定义，并获取该权限集定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="6761c-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6761c-104">语法</span><span class="sxs-lookup"><span data-stu-id="6761c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6761c-105">parameters</span><span class="sxs-lookup"><span data-stu-id="6761c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6761c-106">[在]要修饰的对象。</span><span class="sxs-lookup"><span data-stu-id="6761c-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="6761c-107">[在]指定要使用的声明性安全性类型的[CorDecl 安全](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)值。</span><span class="sxs-lookup"><span data-stu-id="6761c-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="6761c-108">[在]权限 BLOB。</span><span class="sxs-lookup"><span data-stu-id="6761c-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="6761c-109">[在]的大小（以字节为单位）的大小`pvPermission`。</span><span class="sxs-lookup"><span data-stu-id="6761c-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="6761c-110">[出]返回的权限令牌。</span><span class="sxs-lookup"><span data-stu-id="6761c-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6761c-111">要求</span><span class="sxs-lookup"><span data-stu-id="6761c-111">Requirements</span></span>  
 <span data-ttu-id="6761c-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6761c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6761c-113">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="6761c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6761c-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6761c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6761c-115">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6761c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6761c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6761c-116">See also</span></span>

- [<span data-ttu-id="6761c-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="6761c-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6761c-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="6761c-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
