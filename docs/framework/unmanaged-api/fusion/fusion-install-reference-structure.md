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
ms.openlocfilehash: 611b4a543a1de7c6163ec45ff7f17d07726569ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936482"
---
# <a name="fusioninstallreference-structure"></a><span data-ttu-id="abe97-102">FUSION_INSTALL_REFERENCE 结构</span><span class="sxs-lookup"><span data-stu-id="abe97-102">FUSION_INSTALL_REFERENCE Structure</span></span>
<span data-ttu-id="abe97-103">表示应用程序对应用程序已安装在全局程序集缓存中的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="abe97-103">Represents a reference that an application makes to an assembly that the application has installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abe97-104">语法</span><span class="sxs-lookup"><span data-stu-id="abe97-104">Syntax</span></span>  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="abe97-105">成员</span><span class="sxs-lookup"><span data-stu-id="abe97-105">Members</span></span>  
  
|<span data-ttu-id="abe97-106">成员</span><span class="sxs-lookup"><span data-stu-id="abe97-106">Member</span></span>|<span data-ttu-id="abe97-107">描述</span><span class="sxs-lookup"><span data-stu-id="abe97-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="abe97-108">以字节为单位结构的大小。</span><span class="sxs-lookup"><span data-stu-id="abe97-108">The size of the structure in bytes.</span></span>|  
|`dwFlags`|<span data-ttu-id="abe97-109">保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="abe97-109">Reserved for future extensibility.</span></span> <span data-ttu-id="abe97-110">此值必须为 0 （零）。</span><span class="sxs-lookup"><span data-stu-id="abe97-110">This value must be 0 (zero).</span></span>|  
|`guidScheme`|<span data-ttu-id="abe97-111">会将引用添加的实体。</span><span class="sxs-lookup"><span data-stu-id="abe97-111">The entity that adds the reference.</span></span> <span data-ttu-id="abe97-112">此字段可以具有以下值之一：</span><span class="sxs-lookup"><span data-stu-id="abe97-112">This field can have one of the following values:</span></span><br /><br /> <span data-ttu-id="abe97-113">-FUSION_REFCOUNT_MSI_GUID:使用 Microsoft Windows Installer 安装的应用程序引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="abe97-113">-   FUSION_REFCOUNT_MSI_GUID: The assembly is referenced by an application that was installed using the Microsoft Windows Installer.</span></span> <span data-ttu-id="abe97-114">`szIdentifier`字段设置为`MSI`，并`szNonCanonicalData`字段设置为`Windows Installer`。</span><span class="sxs-lookup"><span data-stu-id="abe97-114">The `szIdentifier` field is set to `MSI`, and the `szNonCanonicalData` field is set to `Windows Installer`.</span></span> <span data-ttu-id="abe97-115">此方案用于 Windows 的并行程序集。</span><span class="sxs-lookup"><span data-stu-id="abe97-115">This scheme is used for Windows side-by-side assemblies.</span></span><br /><span data-ttu-id="abe97-116">-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID:将出现在应用程序引用的程序集**添加/删除程序**接口。</span><span class="sxs-lookup"><span data-stu-id="abe97-116">-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: The assembly is referenced by an application that appears in the **Add/Remove Programs** interface.</span></span> <span data-ttu-id="abe97-117">`szIdentifier`字段提供注册该应用程序使用的标记**添加/删除程序**接口。</span><span class="sxs-lookup"><span data-stu-id="abe97-117">The `szIdentifier` field provides the token that registers the application with the **Add/Remove Programs** interface.</span></span><br /><span data-ttu-id="abe97-118">-FUSION_REFCOUNT_FILEPATH_GUID:应用程序所表示的文件在文件系统中引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="abe97-118">-   FUSION_REFCOUNT_FILEPATH_GUID: The assembly is referenced by an application that is represented by a file in the file system.</span></span> <span data-ttu-id="abe97-119">`szIdentifier`字段提供了此文件的路径。</span><span class="sxs-lookup"><span data-stu-id="abe97-119">The `szIdentifier` field provides the path to this file.</span></span><br /><span data-ttu-id="abe97-120">-FUSION_REFCOUNT_OPAQUE_STRING_GUID:仅由不透明的字符串表示的应用程序引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="abe97-120">-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: The assembly is referenced by an application that is represented only by an opaque string.</span></span> <span data-ttu-id="abe97-121">`szIdentifier`字段提供了此不透明的字符串。</span><span class="sxs-lookup"><span data-stu-id="abe97-121">The `szIdentifier` field provides this opaque string.</span></span> <span data-ttu-id="abe97-122">删除此值时在全局程序集缓存不会检查存在的不透明引用。</span><span class="sxs-lookup"><span data-stu-id="abe97-122">The global assembly cache does not check for the existence of opaque references when you remove this value.</span></span><br /><span data-ttu-id="abe97-123">-FUSION_REFCOUNT_OSINSTALL_GUID:保留此值。</span><span class="sxs-lookup"><span data-stu-id="abe97-123">-   FUSION_REFCOUNT_OSINSTALL_GUID: This value is reserved.</span></span>|  
|`szIdentifier`|<span data-ttu-id="abe97-124">标识在全局程序集缓存中安装了程序集的应用程序的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="abe97-124">A unique string that identifies the application that installed the assembly in the global assembly cache.</span></span> <span data-ttu-id="abe97-125">其值的值取决于`guidScheme`字段。</span><span class="sxs-lookup"><span data-stu-id="abe97-125">Its value depends upon the value of the `guidScheme` field.</span></span>|  
|`szNonCanonicalData`|<span data-ttu-id="abe97-126">一个字符串，仅会将引用添加的实体可以理解。</span><span class="sxs-lookup"><span data-stu-id="abe97-126">A string that is understood only by the entity that adds the reference.</span></span> <span data-ttu-id="abe97-127">在全局程序集缓存将此字符串存储，但不使用它。</span><span class="sxs-lookup"><span data-stu-id="abe97-127">The global assembly cache stores this string, but does not use it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="abe97-128">要求</span><span class="sxs-lookup"><span data-stu-id="abe97-128">Requirements</span></span>  
 <span data-ttu-id="abe97-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abe97-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abe97-130">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="abe97-130">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="abe97-131">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abe97-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe97-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="abe97-132">See also</span></span>

- [<span data-ttu-id="abe97-133">合成结构</span><span class="sxs-lookup"><span data-stu-id="abe97-133">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [<span data-ttu-id="abe97-134">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="abe97-134">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
