---
title: "ASSEMBLY_INFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 215d80c3d207c2f50cfbd74386915b0467692b57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="b9c1b-102">ASSEMBLY_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="b9c1b-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="b9c1b-103">包含有关在全局程序集缓存中注册程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9c1b-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9c1b-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b9c1b-105">成员</span><span class="sxs-lookup"><span data-stu-id="b9c1b-105">Members</span></span>  
  
|<span data-ttu-id="b9c1b-106">成员</span><span class="sxs-lookup"><span data-stu-id="b9c1b-106">Member</span></span>|<span data-ttu-id="b9c1b-107">描述</span><span class="sxs-lookup"><span data-stu-id="b9c1b-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="b9c1b-108">以字节为单位，结构的大小。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="b9c1b-109">此字段保留供将来扩展。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="b9c1b-110">指示程序集有关的安装详细信息的标志。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="b9c1b-111">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="b9c1b-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="b9c1b-112">-ASSEMBLYINFO_FLAG_INSTALLED 值，该值指示安装了程序集。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="b9c1b-113">.NET Framework 的当前版本始终设置`dwAssemblyFlags`为此值。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="b9c1b-114">-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 值，该值指示程序集是常驻的负载。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="b9c1b-115">.NET Framework 的当前版本永远不会设置`dwAssemblyFlags`为此值。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="b9c1b-116">总的大小，以千字节为单位，该程序集包含的文件。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="b9c1b-117">指向包含清单的文件的当前路径的字符串缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="b9c1b-118">该路径必须以 null 字符结尾。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="b9c1b-119">宽字符，包括 null 终止符，数，`pszCurrentAssemblyPathBuf`包含。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9c1b-120">惠?</span><span class="sxs-lookup"><span data-stu-id="b9c1b-120">Requirements</span></span>  
 <span data-ttu-id="b9c1b-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b9c1b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9c1b-122">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b9c1b-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b9c1b-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9c1b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9c1b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9c1b-124">See Also</span></span>  
 [<span data-ttu-id="b9c1b-125">合成结构</span><span class="sxs-lookup"><span data-stu-id="b9c1b-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="b9c1b-126">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="b9c1b-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
