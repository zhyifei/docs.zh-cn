---
title: "AssemblyFlags 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyFlags
helpviewer_keywords: AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91760b6d16b663257bf3d89915da3bd88b3411bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="b46c3-102">AssemblyFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="b46c3-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="b46c3-103">包含值，用于描述程序集的运行时功能。</span><span class="sxs-lookup"><span data-stu-id="b46c3-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b46c3-104">语法</span><span class="sxs-lookup"><span data-stu-id="b46c3-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b46c3-105">成员</span><span class="sxs-lookup"><span data-stu-id="b46c3-105">Members</span></span>  
  
|<span data-ttu-id="b46c3-106">成员</span><span class="sxs-lookup"><span data-stu-id="b46c3-106">Member</span></span>|<span data-ttu-id="b46c3-107">描述</span><span class="sxs-lookup"><span data-stu-id="b46c3-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="b46c3-108">指定导出的类型定义是隐式包含该程序集的文件内。</span><span class="sxs-lookup"><span data-stu-id="b46c3-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="b46c3-109">在.NET framework 1.0 和 1.1 版中，此值始终假定要设置。</span><span class="sxs-lookup"><span data-stu-id="b46c3-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="b46c3-110">指定资源定义是隐式包含该程序集的文件内。</span><span class="sxs-lookup"><span data-stu-id="b46c3-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="b46c3-111">在.NET Framework 1.0 和 1.1 中，此值始终假定要设置。</span><span class="sxs-lookup"><span data-stu-id="b46c3-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="b46c3-112">指定程序集无法与其他版本执行，是否它们在同一应用程序域中运行。</span><span class="sxs-lookup"><span data-stu-id="b46c3-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="b46c3-113">指定程序集无法与其他版本执行，是否它们相同的进程中运行。</span><span class="sxs-lookup"><span data-stu-id="b46c3-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="b46c3-114">指定程序集无法与其他版本执行，是否同一台计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="b46c3-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b46c3-115">备注</span><span class="sxs-lookup"><span data-stu-id="b46c3-115">Remarks</span></span>  
 <span data-ttu-id="b46c3-116">0x0010 和 0x0070 （含)，之间的值用于描述的引用的程序集的并排显示兼容性功能。</span><span class="sxs-lookup"><span data-stu-id="b46c3-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="b46c3-117">如果这些值均未设置，则假定程序集是通过并行兼容。</span><span class="sxs-lookup"><span data-stu-id="b46c3-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b46c3-118">要求</span><span class="sxs-lookup"><span data-stu-id="b46c3-118">Requirements</span></span>  
 <span data-ttu-id="b46c3-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b46c3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b46c3-120">**标头：** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b46c3-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="b46c3-121">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b46c3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b46c3-122">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b46c3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b46c3-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b46c3-123">See Also</span></span>  
 [<span data-ttu-id="b46c3-124">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="b46c3-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="b46c3-125">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="b46c3-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
