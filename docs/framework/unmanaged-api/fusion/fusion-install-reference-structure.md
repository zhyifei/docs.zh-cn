---
title: FUSION_INSTALL_REFERENCE 结构
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e81fb7c99b9fd03a69456a84f2191770f40121d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795343"
---
# <a name="fusion_install_reference-structure"></a><span data-ttu-id="48668-102">FUSION_INSTALL_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="48668-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="48668-103">表示应用程序对应用程序已安装在全局程序集缓存中的程序集进行的引用。</span><span class="sxs-lookup"><span data-stu-id="48668-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48668-104">语法</span><span class="sxs-lookup"><span data-stu-id="48668-104">Syntax</span></span>  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="48668-105">成员</span><span class="sxs-lookup"><span data-stu-id="48668-105">Members</span></span>  
  
|<span data-ttu-id="48668-106">成员</span><span class="sxs-lookup"><span data-stu-id="48668-106">Member</span></span>|<span data-ttu-id="48668-107">描述</span><span class="sxs-lookup"><span data-stu-id="48668-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="48668-108">结构的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="48668-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="48668-109">保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="48668-109">Reserved for future extensibility.</span></span> <span data-ttu-id="48668-110">此值必须为0（零）。</span><span class="sxs-lookup"><span data-stu-id="48668-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="48668-111">添加引用的实体。</span><span class="sxs-lookup"><span data-stu-id="48668-111">The entity that adds the reference.</span></span> <span data-ttu-id="48668-112">此字段可以具有以下值之一：</span><span class="sxs-lookup"><span data-stu-id="48668-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="48668-113">- FUSION_REFCOUNT_MSI_GUID:此程序集由使用 Microsoft Windows Installer 安装的应用程序引用。</span><span class="sxs-lookup"><span data-stu-id="48668-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="48668-114">该`szIdentifier`字段设置为`MSI`，并且该`szNonCanonicalData`字段设置为`Windows Installer`。</span><span class="sxs-lookup"><span data-stu-id="48668-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="48668-115">此方案用于 Windows 并行程序集。</span><span class="sxs-lookup"><span data-stu-id="48668-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="48668-116">- FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID:程序集由出现在 "**添加/删除程序**" 界面中的应用程序引用。</span><span class="sxs-lookup"><span data-stu-id="48668-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="48668-117">字段提供了用于将应用程序注册到 "**添加/删除程序**" 界面的令牌。 `szIdentifier`</span><span class="sxs-lookup"><span data-stu-id="48668-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="48668-118">- FUSION_REFCOUNT_FILEPATH_GUID:程序集由文件系统中的文件所表示的应用程序引用。</span><span class="sxs-lookup"><span data-stu-id="48668-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="48668-119">`szIdentifier`字段提供此文件的路径。</span><span class="sxs-lookup"><span data-stu-id="48668-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="48668-120">- FUSION_REFCOUNT_OPAQUE_STRING_GUID:此程序集由仅由不透明字符串表示的应用程序引用。</span><span class="sxs-lookup"><span data-stu-id="48668-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="48668-121">`szIdentifier`字段提供了此不透明字符串。</span><span class="sxs-lookup"><span data-stu-id="48668-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="48668-122">删除此值时，全局程序集缓存不会检查不透明引用是否存在。</span><span class="sxs-lookup"><span data-stu-id="48668-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="48668-123">- FUSION_REFCOUNT_OSINSTALL_GUID:此值为保留值。</span><span class="sxs-lookup"><span data-stu-id="48668-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="48668-124">标识在全局程序集缓存中安装程序集的应用程序的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="48668-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="48668-125">其值取决于`guidScheme`字段的值。</span><span class="sxs-lookup"><span data-stu-id="48668-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="48668-126">仅由添加了引用的实体识别的字符串。</span><span class="sxs-lookup"><span data-stu-id="48668-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="48668-127">全局程序集缓存存储此字符串，但不使用它。</span><span class="sxs-lookup"><span data-stu-id="48668-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48668-128">要求</span><span class="sxs-lookup"><span data-stu-id="48668-128">Requirements</span></span>  
 <span data-ttu-id="48668-129">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48668-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48668-130">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="48668-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="48668-131">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48668-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48668-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="48668-132">See also</span></span>

- [<span data-ttu-id="48668-133">合成结构</span><span class="sxs-lookup"><span data-stu-id="48668-133">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="48668-134">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="48668-134">Global Assembly Cache</span></span>](../../app-domains/gac.md)
