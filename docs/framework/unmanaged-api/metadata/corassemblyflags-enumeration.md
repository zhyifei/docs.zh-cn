---
title: CorAssemblyFlags 枚举
ms.date: 03/30/2017
api_name:
- CorAssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAssemblyFlags
helpviewer_keywords:
- CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type:
- apiref
ms.openlocfilehash: fda890cee5f513ea8cf7e82e710f5451a860c49f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443909"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="a5163-102">CorAssemblyFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="a5163-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="a5163-103">包含一些值，用于描述应用于程序集编译的元数据。</span><span class="sxs-lookup"><span data-stu-id="a5163-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5163-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5163-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a5163-105">Members</span><span class="sxs-lookup"><span data-stu-id="a5163-105">Members</span></span>  
  
|<span data-ttu-id="a5163-106">成员</span><span class="sxs-lookup"><span data-stu-id="a5163-106">Member</span></span>|<span data-ttu-id="a5163-107">说明</span><span class="sxs-lookup"><span data-stu-id="a5163-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="a5163-108">指示程序集引用包含经过哈希的完整公钥。</span><span class="sxs-lookup"><span data-stu-id="a5163-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="a5163-109">指示未指定处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="a5163-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="a5163-110">指示处理器体系结构为中性（PE32）。</span><span class="sxs-lookup"><span data-stu-id="a5163-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="a5163-111">指示处理器体系结构为 x86 （PE32）。</span><span class="sxs-lookup"><span data-stu-id="a5163-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="a5163-112">指示处理器体系结构为 Itanium （PE32 +）。</span><span class="sxs-lookup"><span data-stu-id="a5163-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="a5163-113">指示处理器体系结构为 AMD X64 （PE32 +）。</span><span class="sxs-lookup"><span data-stu-id="a5163-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="a5163-114">指示处理器体系结构为 ARM （PE32）。</span><span class="sxs-lookup"><span data-stu-id="a5163-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="a5163-115">指示程序集是引用程序集;也就是说，它适用于任何体系结构，但不能在任何体系结构上运行。</span><span class="sxs-lookup"><span data-stu-id="a5163-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="a5163-116">因此，标志与 `afPA_Mask`相同。</span><span class="sxs-lookup"><span data-stu-id="a5163-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="a5163-117">指示处理器体系结构标志应传播到 `AssemblyRef` 记录。</span><span class="sxs-lookup"><span data-stu-id="a5163-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="a5163-118">描述处理器体系结构的掩码。</span><span class="sxs-lookup"><span data-stu-id="a5163-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="a5163-119">指定包含处理器体系结构说明。</span><span class="sxs-lookup"><span data-stu-id="a5163-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="a5163-120">指示处理器体系结构标志中与索引之间的移位计数。</span><span class="sxs-lookup"><span data-stu-id="a5163-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="a5163-121">指示 <xref:System.Diagnostics.DebuggableAttribute>的 <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> 中的相应值。</span><span class="sxs-lookup"><span data-stu-id="a5163-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="a5163-122">指示 <xref:System.Diagnostics.DebuggableAttribute>的 <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> 中的相应值。</span><span class="sxs-lookup"><span data-stu-id="a5163-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="a5163-123">指示程序集可在运行时从不同的发布服务器重定向到程序集。</span><span class="sxs-lookup"><span data-stu-id="a5163-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="a5163-124">描述内容类型的掩码。</span><span class="sxs-lookup"><span data-stu-id="a5163-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="a5163-125">指示默认内容类型。</span><span class="sxs-lookup"><span data-stu-id="a5163-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="a5163-126">指示 Windows 运行时内容类型。</span><span class="sxs-lookup"><span data-stu-id="a5163-126">Indicates the Windows Runtime content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5163-127">要求</span><span class="sxs-lookup"><span data-stu-id="a5163-127">Requirements</span></span>  
 <span data-ttu-id="a5163-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5163-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5163-129">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="a5163-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a5163-130">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5163-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5163-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5163-131">See also</span></span>

- [<span data-ttu-id="a5163-132">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="a5163-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
