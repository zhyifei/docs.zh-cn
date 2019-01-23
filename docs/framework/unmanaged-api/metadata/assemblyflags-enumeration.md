---
title: AssemblyFlags 枚举
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9796dd234611fd6bbdf2b949b8a0ed66527aaba9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521252"
---
# <a name="assemblyflags-enumeration"></a><span data-ttu-id="8eea2-102">AssemblyFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="8eea2-102">AssemblyFlags Enumeration</span></span>
<span data-ttu-id="8eea2-103">包含描述运行时功能的程序集的值。</span><span class="sxs-lookup"><span data-stu-id="8eea2-103">Contains values that describe run-time features of an assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eea2-104">语法</span><span class="sxs-lookup"><span data-stu-id="8eea2-104">Syntax</span></span>  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8eea2-105">成员</span><span class="sxs-lookup"><span data-stu-id="8eea2-105">Members</span></span>  
  
|<span data-ttu-id="8eea2-106">成员</span><span class="sxs-lookup"><span data-stu-id="8eea2-106">Member</span></span>|<span data-ttu-id="8eea2-107">描述</span><span class="sxs-lookup"><span data-stu-id="8eea2-107">Description</span></span>|  
|------------|-----------------|  
|`afImplicitExportedTypes`|<span data-ttu-id="8eea2-108">指定导出的类型定义是隐式包含程序集的文件中。</span><span class="sxs-lookup"><span data-stu-id="8eea2-108">Specifies that exported type definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="8eea2-109">在.NET framework 1.0 和 1.1 版中，此值始终假定要设置。</span><span class="sxs-lookup"><span data-stu-id="8eea2-109">In the .NET Framework versions 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afImplicitResources`|<span data-ttu-id="8eea2-110">指定的资源定义中是隐式包含程序集的文件。</span><span class="sxs-lookup"><span data-stu-id="8eea2-110">Specifies that resource definitions are implicit within the files that comprise the assembly.</span></span> <span data-ttu-id="8eea2-111">在.NET Framework 1.0 和 1.1 中，此值始终假定要设置。</span><span class="sxs-lookup"><span data-stu-id="8eea2-111">In the .NET Framework 1.0 and 1.1, this value is always assumed to be set.</span></span>|  
|`afNonSideBySideAppDomain`|<span data-ttu-id="8eea2-112">指定是否在同一应用程序域中运行该程序集不能执行与其他版本。</span><span class="sxs-lookup"><span data-stu-id="8eea2-112">Specifies that the assembly cannot execute with other versions if they are running in the same application domain.</span></span>|  
|`afNonSideBySideProcess`|<span data-ttu-id="8eea2-113">指定是否在同一进程中运行该程序集不能执行与其他版本。</span><span class="sxs-lookup"><span data-stu-id="8eea2-113">Specifies that the assembly cannot execute with other versions if they are running in the same process.</span></span>|  
|`afNonSideBySideMachine`|<span data-ttu-id="8eea2-114">指定是否在同一台计算机上运行该程序集不能执行与其他版本。</span><span class="sxs-lookup"><span data-stu-id="8eea2-114">Specifies that the assembly cannot execute with other versions if they are running on the same computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8eea2-115">备注</span><span class="sxs-lookup"><span data-stu-id="8eea2-115">Remarks</span></span>  
 <span data-ttu-id="8eea2-116">0x0010 和 0x0070 非独占，之间的值用于描述通过并行兼容性功能的引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="8eea2-116">The values between 0x0010 and 0x0070, inclusive, are used to describe side-by-side compatibility features of the referenced assembly.</span></span> <span data-ttu-id="8eea2-117">如果没有这些值设置，该程序集被假定为通过并行兼容。</span><span class="sxs-lookup"><span data-stu-id="8eea2-117">If none of these values are set, the assembly is assumed to be side-by-side compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eea2-118">要求</span><span class="sxs-lookup"><span data-stu-id="8eea2-118">Requirements</span></span>  
 <span data-ttu-id="8eea2-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8eea2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eea2-120">**标头：** MsCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8eea2-120">**Header:** MsCorEE.h</span></span>  
  
 <span data-ttu-id="8eea2-121">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8eea2-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8eea2-122">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eea2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eea2-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8eea2-123">See also</span></span>
- [<span data-ttu-id="8eea2-124">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="8eea2-124">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="8eea2-125">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="8eea2-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
