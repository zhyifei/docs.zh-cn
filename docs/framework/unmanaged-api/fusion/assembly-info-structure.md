---
title: ASSEMBLY_INFO 结构
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
ms.openlocfilehash: a43d5e15c02a97ff10a6a5afd439cadebb6b33d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109217"
---
# <a name="assembly_info-structure"></a><span data-ttu-id="f3f24-102">ASSEMBLY_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="f3f24-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="f3f24-103">包含有关在全局程序集缓存中注册的程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="f3f24-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3f24-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3f24-104">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="f3f24-105">Members</span><span class="sxs-lookup"><span data-stu-id="f3f24-105">Members</span></span>  
  
|<span data-ttu-id="f3f24-106">成员</span><span class="sxs-lookup"><span data-stu-id="f3f24-106">Member</span></span>|<span data-ttu-id="f3f24-107">描述</span><span class="sxs-lookup"><span data-stu-id="f3f24-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="f3f24-108">结构的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f3f24-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="f3f24-109">此字段保留供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="f3f24-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="f3f24-110">指示程序集的安装详细信息的标志。</span><span class="sxs-lookup"><span data-stu-id="f3f24-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="f3f24-111">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="f3f24-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="f3f24-112">-ASSEMBLYINFO_FLAG_INSTALLED 值，该值指示已安装程序集。</span><span class="sxs-lookup"><span data-stu-id="f3f24-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="f3f24-113">当前版本的 .NET Framework 始终将 `dwAssemblyFlags` 设置为此值。</span><span class="sxs-lookup"><span data-stu-id="f3f24-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="f3f24-114">-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 值，指示程序集是一个有效负载。</span><span class="sxs-lookup"><span data-stu-id="f3f24-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="f3f24-115">.NET Framework 的当前版本从不将 `dwAssemblyFlags` 设置为此值。</span><span class="sxs-lookup"><span data-stu-id="f3f24-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="f3f24-116">程序集包含的文件的总大小（kb）。</span><span class="sxs-lookup"><span data-stu-id="f3f24-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="f3f24-117">指向包含清单文件的当前路径的字符串缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="f3f24-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="f3f24-118">路径必须以 null 字符结尾。</span><span class="sxs-lookup"><span data-stu-id="f3f24-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="f3f24-119">`pszCurrentAssemblyPathBuf` 包含的宽字符数，包括 null 结束符。</span><span class="sxs-lookup"><span data-stu-id="f3f24-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3f24-120">要求</span><span class="sxs-lookup"><span data-stu-id="f3f24-120">Requirements</span></span>  
 <span data-ttu-id="f3f24-121">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3f24-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3f24-122">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="f3f24-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f3f24-123">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3f24-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3f24-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3f24-124">See also</span></span>

- [<span data-ttu-id="f3f24-125">合成结构</span><span class="sxs-lookup"><span data-stu-id="f3f24-125">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="f3f24-126">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="f3f24-126">Global Assembly Cache</span></span>](../../app-domains/gac.md)
