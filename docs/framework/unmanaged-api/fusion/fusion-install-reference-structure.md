---
title: "FUSION_INSTALL_REFERENCE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36321606fe208233fb6114fe9568b655f0e1b400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="7bd05-102">FUSION_INSTALL_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="7bd05-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="7bd05-103">表示应用程序对应用程序已安装在全局程序集缓存中程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="7bd05-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd05-104">语法</span><span class="sxs-lookup"><span data-stu-id="7bd05-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="7bd05-105">成员</span><span class="sxs-lookup"><span data-stu-id="7bd05-105">Members</span></span>  
  
|<span data-ttu-id="7bd05-106">成员</span><span class="sxs-lookup"><span data-stu-id="7bd05-106">Member</span></span>|<span data-ttu-id="7bd05-107">描述</span><span class="sxs-lookup"><span data-stu-id="7bd05-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="7bd05-108">以字节为单位结构的大小。</span><span class="sxs-lookup"><span data-stu-id="7bd05-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="7bd05-109">留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="7bd05-109">Reserved for future extensibility.</span></span> <span data-ttu-id="7bd05-110">此值必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="7bd05-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="7bd05-111">将引用添加的实体。</span><span class="sxs-lookup"><span data-stu-id="7bd05-111">The entity that adds the reference.</span></span> <span data-ttu-id="7bd05-112">此字段可以具有以下值之一：</span><span class="sxs-lookup"><span data-stu-id="7bd05-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="7bd05-113">-FUSION_REFCOUNT_MSI_GUID： 使用 Microsoft Windows Installer 安装的应用程序引用了程序集。</span><span class="sxs-lookup"><span data-stu-id="7bd05-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="7bd05-114">`szIdentifier`字段设置为`MSI`，和`szNonCanonicalData`字段设置为`Windows Installer`。</span><span class="sxs-lookup"><span data-stu-id="7bd05-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="7bd05-115">此方案适用于 Windows 的并行程序集。</span><span class="sxs-lookup"><span data-stu-id="7bd05-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="7bd05-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID： 出现在应用程序引用的程序集**添加/删除程序**接口。</span><span class="sxs-lookup"><span data-stu-id="7bd05-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="7bd05-117">`szIdentifier`字段提供注册与该应用程序的令牌**添加/删除程序**接口。</span><span class="sxs-lookup"><span data-stu-id="7bd05-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="7bd05-118">-FUSION_REFCOUNT_FILEPATH_GUID： 程序集被引用的应用程序在文件系统中表示的文件。</span><span class="sxs-lookup"><span data-stu-id="7bd05-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="7bd05-119">`szIdentifier`字段提供此文件的路径。</span><span class="sxs-lookup"><span data-stu-id="7bd05-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="7bd05-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID： 程序集被引用的应用程序仅由一个不透明的字符串。</span><span class="sxs-lookup"><span data-stu-id="7bd05-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="7bd05-121">`szIdentifier`字段提供此不透明的字符串。</span><span class="sxs-lookup"><span data-stu-id="7bd05-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="7bd05-122">全局程序集缓存不会检查存在不透明引用时删除此值。</span><span class="sxs-lookup"><span data-stu-id="7bd05-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="7bd05-123">-FUSION_REFCOUNT_OSINSTALL_GUID： 保留此值。</span><span class="sxs-lookup"><span data-stu-id="7bd05-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="7bd05-124">一个标识的应用程序在全局程序集缓存中安装了程序集的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="7bd05-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="7bd05-125">其值取决于值`guidScheme`字段。</span><span class="sxs-lookup"><span data-stu-id="7bd05-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="7bd05-126">一个字符串，理解只能通过将引用添加的实体。</span><span class="sxs-lookup"><span data-stu-id="7bd05-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="7bd05-127">全局程序集缓存存储此字符串中，但不使用它。</span><span class="sxs-lookup"><span data-stu-id="7bd05-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7bd05-128">惠?</span><span class="sxs-lookup"><span data-stu-id="7bd05-128">Requirements</span></span>  
 <span data-ttu-id="7bd05-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7bd05-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bd05-130">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7bd05-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7bd05-131">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bd05-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd05-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="7bd05-132">See Also</span></span>  
 [<span data-ttu-id="7bd05-133">合成结构</span><span class="sxs-lookup"><span data-stu-id="7bd05-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="7bd05-134">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="7bd05-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
