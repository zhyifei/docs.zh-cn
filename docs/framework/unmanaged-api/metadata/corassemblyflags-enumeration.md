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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d6ec37bbd8750c27a41b5f18180c7726cdcd483
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442823"
---
# <a name="corassemblyflags-enumeration"></a><span data-ttu-id="28ec7-102">CorAssemblyFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="28ec7-102">CorAssemblyFlags Enumeration</span></span>
<span data-ttu-id="28ec7-103">包含一些值，用于描述应用于程序集编译的元数据。</span><span class="sxs-lookup"><span data-stu-id="28ec7-103">Contains values that describe the metadata applied to an assembly compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ec7-104">语法</span><span class="sxs-lookup"><span data-stu-id="28ec7-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="28ec7-105">成员</span><span class="sxs-lookup"><span data-stu-id="28ec7-105">Members</span></span>  
  
|<span data-ttu-id="28ec7-106">成员</span><span class="sxs-lookup"><span data-stu-id="28ec7-106">Member</span></span>|<span data-ttu-id="28ec7-107">描述</span><span class="sxs-lookup"><span data-stu-id="28ec7-107">Description</span></span>|  
|------------|-----------------|  
|`afPublicKey`|<span data-ttu-id="28ec7-108">指示程序集引用包含完整的未经哈希的公钥。</span><span class="sxs-lookup"><span data-stu-id="28ec7-108">Indicates that the assembly reference holds the full, unhashed public key.</span></span>|  
|`afPA_None`|<span data-ttu-id="28ec7-109">指示未指定的处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="28ec7-109">Indicates that the processor architecture is unspecified.</span></span>|  
|`afPA_MSIL`|<span data-ttu-id="28ec7-110">指示处理器体系结构是非特定 （pe32 +）。</span><span class="sxs-lookup"><span data-stu-id="28ec7-110">Indicates that the processor architecture is neutral (PE32).</span></span>|  
|`afPA_x86`|<span data-ttu-id="28ec7-111">指示处理器体系结构是 x86 （pe32 +）。</span><span class="sxs-lookup"><span data-stu-id="28ec7-111">Indicates that the processor architecture is x86 (PE32).</span></span>|  
|`afPA_IA64`|<span data-ttu-id="28ec7-112">指示处理器体系结构为 Itanium （PE32 +）。</span><span class="sxs-lookup"><span data-stu-id="28ec7-112">Indicates that the processor architecture is Itanium (PE32+).</span></span>|  
|`afPA_AMD64`|<span data-ttu-id="28ec7-113">指示处理器体系结构是 AMD X64 （PE32 +）。</span><span class="sxs-lookup"><span data-stu-id="28ec7-113">Indicates that the processor architecture is AMD X64 (PE32+).</span></span>|  
|`afPA_ARM`|<span data-ttu-id="28ec7-114">指示处理器体系结构是 ARM （pe32 +）。</span><span class="sxs-lookup"><span data-stu-id="28ec7-114">Indicates that the processor architecture is ARM (PE32).</span></span>|  
|`afPA_NoPlatform`|<span data-ttu-id="28ec7-115">指示程序集是引用程序集;也就是说，它将应用于任何体系结构，但无法在任何体系结构上运行。</span><span class="sxs-lookup"><span data-stu-id="28ec7-115">Indicates that the assembly is a reference assembly; that is, it applies to any architecture but cannot run on any architecture.</span></span> <span data-ttu-id="28ec7-116">因此，该标志等同于`afPA_Mask`。</span><span class="sxs-lookup"><span data-stu-id="28ec7-116">Thus, the flag is the same as `afPA_Mask`.</span></span>|  
|`afPA_Specified`|<span data-ttu-id="28ec7-117">指示应将处理器体系结构标志传播到`AssemblyRef`记录。</span><span class="sxs-lookup"><span data-stu-id="28ec7-117">Indicates that the processor architecture flags should be propagated to the `AssemblyRef` record.</span></span>|  
|`afPA_Mask`|<span data-ttu-id="28ec7-118">描述的处理器体系结构的掩码。</span><span class="sxs-lookup"><span data-stu-id="28ec7-118">A mask that describes the processor architecture.</span></span>|  
|`afPA_FullMask`|<span data-ttu-id="28ec7-119">指定包含处理器体系结构说明。</span><span class="sxs-lookup"><span data-stu-id="28ec7-119">Specifies that the processor architecture description is included.</span></span>|  
|`afPA_Shift`|<span data-ttu-id="28ec7-120">指示在处理器体系结构标志到和从索引中的 shift 计数。</span><span class="sxs-lookup"><span data-stu-id="28ec7-120">Indicates a shift count in the processor architecture flags to and from the index.</span></span>|  
|`afEnableJITcompileTracking`|<span data-ttu-id="28ec7-121">指示从相应的值<xref:System.Diagnostics.DebuggableAttribute.DebuggingModes>的<xref:System.Diagnostics.DebuggableAttribute>。</span><span class="sxs-lookup"><span data-stu-id="28ec7-121">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afDisableJITcompileOptimizer`|<span data-ttu-id="28ec7-122">指示从相应的值<xref:System.Diagnostics.DebuggableAttribute.DebuggingModes>的<xref:System.Diagnostics.DebuggableAttribute>。</span><span class="sxs-lookup"><span data-stu-id="28ec7-122">Indicates the corresponding value from the <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> of the <xref:System.Diagnostics.DebuggableAttribute>.</span></span>|  
|`afRetargetable`|<span data-ttu-id="28ec7-123">指示程序集可以重定向在运行时的程序集从不同的发布者。</span><span class="sxs-lookup"><span data-stu-id="28ec7-123">Indicates that the assembly can be retargeted at run time to an assembly from a different publisher.</span></span>|  
|`afContentType_Mask`|<span data-ttu-id="28ec7-124">描述内容的类型掩码。</span><span class="sxs-lookup"><span data-stu-id="28ec7-124">A mask that describes the content type.</span></span>|  
|`afContentType_Default`|<span data-ttu-id="28ec7-125">指示默认内容类型。</span><span class="sxs-lookup"><span data-stu-id="28ec7-125">Indicates the default content type.</span></span>|  
|`afContentType_WindowsRuntime`|<span data-ttu-id="28ec7-126">指示[!INCLUDE[wrt](../../../../includes/wrt-md.md)]内容类型。</span><span class="sxs-lookup"><span data-stu-id="28ec7-126">Indicates the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] content type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28ec7-127">要求</span><span class="sxs-lookup"><span data-stu-id="28ec7-127">Requirements</span></span>  
 <span data-ttu-id="28ec7-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28ec7-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28ec7-129">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="28ec7-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="28ec7-130">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28ec7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ec7-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="28ec7-131">See Also</span></span>  
 [<span data-ttu-id="28ec7-132">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="28ec7-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
