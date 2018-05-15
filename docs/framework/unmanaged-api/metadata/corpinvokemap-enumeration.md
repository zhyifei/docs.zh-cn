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
ms.openlocfilehash: edb45c9ceefb242e5a72e8602dc93ecd39b2df09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="091f5-102">CorPinvokeMap 枚举</span><span class="sxs-lookup"><span data-stu-id="091f5-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="091f5-103">指定为 PInvoke 调用的选项。</span><span class="sxs-lookup"><span data-stu-id="091f5-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="091f5-104">语法</span><span class="sxs-lookup"><span data-stu-id="091f5-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="091f5-105">成员</span><span class="sxs-lookup"><span data-stu-id="091f5-105">Members</span></span>  
  
|<span data-ttu-id="091f5-106">成员</span><span class="sxs-lookup"><span data-stu-id="091f5-106">Member</span></span>|<span data-ttu-id="091f5-107">描述</span><span class="sxs-lookup"><span data-stu-id="091f5-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="091f5-108">使用指定的每个成员名称。</span><span class="sxs-lookup"><span data-stu-id="091f5-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="091f5-109">保留。</span><span class="sxs-lookup"><span data-stu-id="091f5-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="091f5-110">保留。</span><span class="sxs-lookup"><span data-stu-id="091f5-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="091f5-111">以多字节字符串的形式封送字符串。</span><span class="sxs-lookup"><span data-stu-id="091f5-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="091f5-112">以 Unicode 2 字节字符的形式封送字符串。</span><span class="sxs-lookup"><span data-stu-id="091f5-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="091f5-113">针对目标操作系统适当地自动封送字符串。</span><span class="sxs-lookup"><span data-stu-id="091f5-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="091f5-114">默认值是 Windows NT、 Windows 2000、 Windows XP 和 Windows Server 2003 系列中; 上的为 Unicode默认值是 Windows 98 和 Windows me 上的为 ANSI</span><span class="sxs-lookup"><span data-stu-id="091f5-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="091f5-115">保留。</span><span class="sxs-lookup"><span data-stu-id="091f5-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="091f5-116">执行最佳的映射缺少完全匹配 ANSI 字符集中的 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="091f5-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="091f5-117">不执行 Unicode 字符的最佳的的映射。</span><span class="sxs-lookup"><span data-stu-id="091f5-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="091f5-118">在这种情况下，所有无法映射的字符将替换为？。</span><span class="sxs-lookup"><span data-stu-id="091f5-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="091f5-119">保留。</span><span class="sxs-lookup"><span data-stu-id="091f5-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="091f5-120">保留。</span><span class="sxs-lookup"><span data-stu-id="091f5-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="091f5-121">当互操作封送处理程序遇到无法映射的字符，则引发异常。</span><span class="sxs-lookup"><span data-stu-id="091f5-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="091f5-122">当互操作封送处理程序遇到无法映射的字符，则不引发异常。</span><span class="sxs-lookup"><span data-stu-id="091f5-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="091f5-123">保留</span><span class="sxs-lookup"><span data-stu-id="091f5-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="091f5-124">允许被调用方调用 Win32`SetLastError`从特性化方法返回之前的函数。</span><span class="sxs-lookup"><span data-stu-id="091f5-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="091f5-125">保留</span><span class="sxs-lookup"><span data-stu-id="091f5-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="091f5-126">使用默认平台调用约定。</span><span class="sxs-lookup"><span data-stu-id="091f5-126">Use the default platform calling convention.</span></span> <span data-ttu-id="091f5-127">例如，在 Windows 上默认值是`StdCall`和 Windows CE.NET 很`Cdecl`。</span><span class="sxs-lookup"><span data-stu-id="091f5-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="091f5-128">使用`Cdecl`调用约定。</span><span class="sxs-lookup"><span data-stu-id="091f5-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="091f5-129">在这种情况下，调用方将清理堆栈。</span><span class="sxs-lookup"><span data-stu-id="091f5-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="091f5-130">这使调用函数使用`varargs`（即，接受可变数目的参数的函数）。</span><span class="sxs-lookup"><span data-stu-id="091f5-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="091f5-131">使用`StdCall`调用约定。</span><span class="sxs-lookup"><span data-stu-id="091f5-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="091f5-132">在这种情况下，被调用方将清理堆栈。</span><span class="sxs-lookup"><span data-stu-id="091f5-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="091f5-133">这是使用平台 invoke 调用非托管函数的默认约定。</span><span class="sxs-lookup"><span data-stu-id="091f5-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="091f5-134">使用`ThisCall`调用约定。</span><span class="sxs-lookup"><span data-stu-id="091f5-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="091f5-135">在这种情况下，第一个参数是`this`指针和存储在 ECX 寄存器。</span><span class="sxs-lookup"><span data-stu-id="091f5-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="091f5-136">其他参数被推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="091f5-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="091f5-137">`ThisCall`调用约定用于调用从非托管 DLL 中导出的类上的方法。</span><span class="sxs-lookup"><span data-stu-id="091f5-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="091f5-138">保留。</span><span class="sxs-lookup"><span data-stu-id="091f5-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="091f5-139">保留。</span><span class="sxs-lookup"><span data-stu-id="091f5-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="091f5-140">要求</span><span class="sxs-lookup"><span data-stu-id="091f5-140">Requirements</span></span>  
 <span data-ttu-id="091f5-141">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="091f5-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="091f5-142">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="091f5-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="091f5-143">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="091f5-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091f5-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="091f5-144">See Also</span></span>  
 [<span data-ttu-id="091f5-145">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="091f5-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
