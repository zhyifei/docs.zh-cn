---
title: CorPinvokeMap 枚举
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941092f67f66c5b17c8ae592569c2a8e6a675
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079625"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="f28cb-102">CorPinvokeMap 枚举</span><span class="sxs-lookup"><span data-stu-id="f28cb-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="f28cb-103">指定选项的 PInvoke 调用。</span><span class="sxs-lookup"><span data-stu-id="f28cb-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f28cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="f28cb-104">Syntax</span></span>  
  
```  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,   
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a><span data-ttu-id="f28cb-105">成员</span><span class="sxs-lookup"><span data-stu-id="f28cb-105">Members</span></span>  
  
|<span data-ttu-id="f28cb-106">成员</span><span class="sxs-lookup"><span data-stu-id="f28cb-106">Member</span></span>|<span data-ttu-id="f28cb-107">描述</span><span class="sxs-lookup"><span data-stu-id="f28cb-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="f28cb-108">使用指定的每个成员名称。</span><span class="sxs-lookup"><span data-stu-id="f28cb-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="f28cb-109">保留。</span><span class="sxs-lookup"><span data-stu-id="f28cb-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="f28cb-110">保留。</span><span class="sxs-lookup"><span data-stu-id="f28cb-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="f28cb-111">以多字节字符串的形式封送字符串。</span><span class="sxs-lookup"><span data-stu-id="f28cb-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="f28cb-112">以 Unicode 2 字节字符的形式封送字符串。</span><span class="sxs-lookup"><span data-stu-id="f28cb-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="f28cb-113">针对目标操作系统适当地自动封送字符串。</span><span class="sxs-lookup"><span data-stu-id="f28cb-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="f28cb-114">默认值是 Windows NT、 Windows 2000、 Windows XP 和 Windows Server 2003 系列中; 上的为 Unicode默认值为 ANSI，在 Windows 98 和 Windows me 一起提供。</span><span class="sxs-lookup"><span data-stu-id="f28cb-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="f28cb-115">保留。</span><span class="sxs-lookup"><span data-stu-id="f28cb-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="f28cb-116">执行最佳映射缺乏完全匹配 ANSI 字符集的 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="f28cb-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="f28cb-117">不执行最佳的映射的 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="f28cb-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="f28cb-118">在这种情况下，无法映射的所有字符将都替换为？。</span><span class="sxs-lookup"><span data-stu-id="f28cb-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="f28cb-119">保留。</span><span class="sxs-lookup"><span data-stu-id="f28cb-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="f28cb-120">保留。</span><span class="sxs-lookup"><span data-stu-id="f28cb-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="f28cb-121">互操作封送处理程序遇到的无法映射字符时引发异常。</span><span class="sxs-lookup"><span data-stu-id="f28cb-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="f28cb-122">互操作封送处理程序遇到的无法映射字符时不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="f28cb-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="f28cb-123">保留</span><span class="sxs-lookup"><span data-stu-id="f28cb-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="f28cb-124">允许被调用方能够调用 Win32`SetLastError`从特性化方法返回之前的函数。</span><span class="sxs-lookup"><span data-stu-id="f28cb-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="f28cb-125">保留</span><span class="sxs-lookup"><span data-stu-id="f28cb-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="f28cb-126">使用默认平台调用约定。</span><span class="sxs-lookup"><span data-stu-id="f28cb-126">Use the default platform calling convention.</span></span> <span data-ttu-id="f28cb-127">例如，在 Windows 上默认值是`StdCall`以及它是 Windows CE.NET `Cdecl`。</span><span class="sxs-lookup"><span data-stu-id="f28cb-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="f28cb-128">使用`Cdecl`调用约定。</span><span class="sxs-lookup"><span data-stu-id="f28cb-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="f28cb-129">在这种情况下，调用方清理堆栈。</span><span class="sxs-lookup"><span data-stu-id="f28cb-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="f28cb-130">这样，与调用函数`varargs`（即，接受数目可变的参数的函数）。</span><span class="sxs-lookup"><span data-stu-id="f28cb-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="f28cb-131">使用`StdCall`调用约定。</span><span class="sxs-lookup"><span data-stu-id="f28cb-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="f28cb-132">在这种情况下，被调用方清理堆栈。</span><span class="sxs-lookup"><span data-stu-id="f28cb-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="f28cb-133">这是使用平台 invoke 调用非托管函数的默认约定。</span><span class="sxs-lookup"><span data-stu-id="f28cb-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="f28cb-134">使用`ThisCall`调用约定。</span><span class="sxs-lookup"><span data-stu-id="f28cb-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="f28cb-135">在这种情况下，第一个参数是`this`指针和存储在寄存器 ECX 中。</span><span class="sxs-lookup"><span data-stu-id="f28cb-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="f28cb-136">其他参数被推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="f28cb-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="f28cb-137">`ThisCall`调用约定用于从非托管 DLL 导出的类上调用方法。</span><span class="sxs-lookup"><span data-stu-id="f28cb-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="f28cb-138">保留。</span><span class="sxs-lookup"><span data-stu-id="f28cb-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="f28cb-139">保留。</span><span class="sxs-lookup"><span data-stu-id="f28cb-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f28cb-140">要求</span><span class="sxs-lookup"><span data-stu-id="f28cb-140">Requirements</span></span>  
 <span data-ttu-id="f28cb-141">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f28cb-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f28cb-142">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f28cb-142">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="f28cb-143">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="f28cb-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f28cb-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="f28cb-144">See also</span></span>

- [<span data-ttu-id="f28cb-145">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="f28cb-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
