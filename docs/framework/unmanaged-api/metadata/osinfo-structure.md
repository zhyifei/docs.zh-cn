---
title: "OSINFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: OSINFO
api_location: mscoree.dll
api_type: COM
f1_keywords: OSINFO
helpviewer_keywords: OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 700e9bcfe33e5be3725bd24b212b3a77ad139b2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="osinfo-structure"></a><span data-ttu-id="e635d-102">OSINFO 结构</span><span class="sxs-lookup"><span data-stu-id="e635d-102">OSINFO Structure</span></span>
<span data-ttu-id="e635d-103">包含有关操作系统的程序集或模块的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e635d-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e635d-104">语法</span><span class="sxs-lookup"><span data-stu-id="e635d-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e635d-105">成员</span><span class="sxs-lookup"><span data-stu-id="e635d-105">Members</span></span>  
  
|<span data-ttu-id="e635d-106">成员</span><span class="sxs-lookup"><span data-stu-id="e635d-106">Member</span></span>|<span data-ttu-id="e635d-107">描述</span><span class="sxs-lookup"><span data-stu-id="e635d-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="e635d-108">一个由 Microsoft Windows 平台函数定义的标识符值`GetVersionEx`。</span><span class="sxs-lookup"><span data-stu-id="e635d-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="e635d-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e635d-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="e635d-110">-VER_PLATFORM_WIN32s 或 0x0000，要指定 Microsoft Windows 3.1。</span><span class="sxs-lookup"><span data-stu-id="e635d-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="e635d-111">-VER_PLATFORM_WIN32_WINDOWS 或从 0x0001，指定 Windows 95、 Windows 98 或继承自此它们的操作系统。</span><span class="sxs-lookup"><span data-stu-id="e635d-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="e635d-112">-VER_PLATFORM_WIN32_NT 或 0x0010，指定 Windows NT 或继承自此它的操作系统。</span><span class="sxs-lookup"><span data-stu-id="e635d-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="e635d-113">操作系统主要版本或 NULL 值以指示任何版本。</span><span class="sxs-lookup"><span data-stu-id="e635d-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="e635d-114">操作系统次要版本或 NULL 值以指示任何版本。</span><span class="sxs-lookup"><span data-stu-id="e635d-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e635d-115">备注</span><span class="sxs-lookup"><span data-stu-id="e635d-115">Remarks</span></span>  
 <span data-ttu-id="e635d-116">`OSINFO`基于`OSVERSIONINFOEX`结构，它是 Microsoft Windows 平台函数调用中使用的`GetVersionEx`。</span><span class="sxs-lookup"><span data-stu-id="e635d-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="e635d-117">此结构是 ASSEMBLYMETADATA 结构用于指示其操作系统的支持。</span><span class="sxs-lookup"><span data-stu-id="e635d-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e635d-118">要求</span><span class="sxs-lookup"><span data-stu-id="e635d-118">Requirements</span></span>  
 <span data-ttu-id="e635d-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e635d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e635d-120">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e635d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e635d-121">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e635d-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e635d-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e635d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e635d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e635d-123">See Also</span></span>  
 [<span data-ttu-id="e635d-124">元数据结构</span><span class="sxs-lookup"><span data-stu-id="e635d-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="e635d-125">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="e635d-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
