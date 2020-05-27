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
ms.openlocfilehash: a069e2f4ec5d4114e9504fa5a58c5066fdfd7249
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008035"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="e992b-102">IMetaDataEmit::DefinePermissionSet 方法</span><span class="sxs-lookup"><span data-stu-id="e992b-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="e992b-103">使用指定的元数据签名创建权限集的定义，并获取该权限集定义的标记。</span><span class="sxs-lookup"><span data-stu-id="e992b-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e992b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e992b-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e992b-105">参数</span><span class="sxs-lookup"><span data-stu-id="e992b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e992b-106">中要修饰的对象。</span><span class="sxs-lookup"><span data-stu-id="e992b-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="e992b-107">中一个[CorDeclSecurity](cordeclsecurity-enumeration.md)值，指定要使用的声明性安全类型。</span><span class="sxs-lookup"><span data-stu-id="e992b-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="e992b-108">中权限 BLOB。</span><span class="sxs-lookup"><span data-stu-id="e992b-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="e992b-109">中的大小（以字节为单位） `pvPermission` 。</span><span class="sxs-lookup"><span data-stu-id="e992b-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="e992b-110">弄返回的权限标记。</span><span class="sxs-lookup"><span data-stu-id="e992b-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e992b-111">要求</span><span class="sxs-lookup"><span data-stu-id="e992b-111">Requirements</span></span>  
 <span data-ttu-id="e992b-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e992b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e992b-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="e992b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e992b-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e992b-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e992b-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e992b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e992b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e992b-116">See also</span></span>

- [<span data-ttu-id="e992b-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="e992b-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e992b-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="e992b-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
