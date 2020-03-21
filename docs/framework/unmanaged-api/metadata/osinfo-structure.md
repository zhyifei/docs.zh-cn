---
title: OSINFO 结构
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175221"
---
# <a name="osinfo-structure"></a><span data-ttu-id="b17a8-102">OSINFO 结构</span><span class="sxs-lookup"><span data-stu-id="b17a8-102">OSINFO Structure</span></span>
<span data-ttu-id="b17a8-103">包含有关程序集或模块的操作系统的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b17a8-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b17a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="b17a8-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b17a8-105">成员</span><span class="sxs-lookup"><span data-stu-id="b17a8-105">Members</span></span>  
  
|<span data-ttu-id="b17a8-106">成员</span><span class="sxs-lookup"><span data-stu-id="b17a8-106">Member</span></span>|<span data-ttu-id="b17a8-107">说明</span><span class="sxs-lookup"><span data-stu-id="b17a8-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="b17a8-108">由微软 Windows 平台函数`GetVersionEx`定义的标识符值之一。</span><span class="sxs-lookup"><span data-stu-id="b17a8-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="b17a8-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="b17a8-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="b17a8-110">- VER_PLATFORM_WIN32s，或 0x0000，以指定微软 Windows 3.1。</span><span class="sxs-lookup"><span data-stu-id="b17a8-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="b17a8-111">- VER_PLATFORM_WIN32_WINDOWS，或 0x0001，以指定 Windows 95、Windows 98 或它们产生的操作系统。</span><span class="sxs-lookup"><span data-stu-id="b17a8-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="b17a8-112">- VER_PLATFORM_WIN32_NT，或 0x0002，以指定 Windows NT 或操作系统从它下降。</span><span class="sxs-lookup"><span data-stu-id="b17a8-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="b17a8-113">操作系统主版本，或用于指示任何版本的 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="b17a8-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="b17a8-114">操作系统次要版本，或用于指示任何版本的 NULL 值。</span><span class="sxs-lookup"><span data-stu-id="b17a8-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b17a8-115">备注</span><span class="sxs-lookup"><span data-stu-id="b17a8-115">Remarks</span></span>  
 <span data-ttu-id="b17a8-116">`OSINFO`基于调用微软`OSVERSIONINFOEX`Windows 平台功能`GetVersionEx`时使用的结构。</span><span class="sxs-lookup"><span data-stu-id="b17a8-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="b17a8-117">此结构由 ASSEMBLYMETADATA 结构用于指示其操作系统支持。</span><span class="sxs-lookup"><span data-stu-id="b17a8-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b17a8-118">要求</span><span class="sxs-lookup"><span data-stu-id="b17a8-118">Requirements</span></span>  
 <span data-ttu-id="b17a8-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b17a8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b17a8-120">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="b17a8-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b17a8-121">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b17a8-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b17a8-122">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b17a8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17a8-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b17a8-123">See also</span></span>

- [<span data-ttu-id="b17a8-124">元数据结构</span><span class="sxs-lookup"><span data-stu-id="b17a8-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="b17a8-125">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="b17a8-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
