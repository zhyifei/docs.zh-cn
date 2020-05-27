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
ms.openlocfilehash: 199a649b0481c2a740926636345eefbda6831ef2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007541"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="880eb-102">CorPinvokeMap 枚举</span><span class="sxs-lookup"><span data-stu-id="880eb-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="880eb-103">指定 PInvoke 调用的选项。</span><span class="sxs-lookup"><span data-stu-id="880eb-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="880eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="880eb-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="880eb-105">成员</span><span class="sxs-lookup"><span data-stu-id="880eb-105">Members</span></span>  
  
|<span data-ttu-id="880eb-106">成员</span><span class="sxs-lookup"><span data-stu-id="880eb-106">Member</span></span>|<span data-ttu-id="880eb-107">描述</span><span class="sxs-lookup"><span data-stu-id="880eb-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="880eb-108">按指定使用每个成员名称。</span><span class="sxs-lookup"><span data-stu-id="880eb-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="880eb-109">保留。</span><span class="sxs-lookup"><span data-stu-id="880eb-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="880eb-110">保留。</span><span class="sxs-lookup"><span data-stu-id="880eb-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="880eb-111">以多字节字符串的形式封送字符串。</span><span class="sxs-lookup"><span data-stu-id="880eb-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="880eb-112">以 Unicode 2 字节字符的形式封送字符串。</span><span class="sxs-lookup"><span data-stu-id="880eb-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="880eb-113">针对目标操作系统适当地自动封送字符串。</span><span class="sxs-lookup"><span data-stu-id="880eb-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="880eb-114">在 Windows NT、Windows 2000、Windows XP 和 Windows Server 2003 系列上，默认值为 Unicode;在 Windows 98 和 Windows Me 上，默认值为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="880eb-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="880eb-115">保留。</span><span class="sxs-lookup"><span data-stu-id="880eb-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="880eb-116">在 ANSI 字符集中执行与缺少完全匹配的 Unicode 字符的最佳映射。</span><span class="sxs-lookup"><span data-stu-id="880eb-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="880eb-117">不要执行 Unicode 字符的最佳映射。</span><span class="sxs-lookup"><span data-stu-id="880eb-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="880eb-118">在这种情况下，所有无法映射的字符都将替换为 "？"。</span><span class="sxs-lookup"><span data-stu-id="880eb-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="880eb-119">保留。</span><span class="sxs-lookup"><span data-stu-id="880eb-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="880eb-120">保留。</span><span class="sxs-lookup"><span data-stu-id="880eb-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="880eb-121">当互操作封送拆收器遇到无法映射的字符时引发异常。</span><span class="sxs-lookup"><span data-stu-id="880eb-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="880eb-122">在互操作封送拆收器遇到无法映射的字符时不引发异常。</span><span class="sxs-lookup"><span data-stu-id="880eb-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="880eb-123">保留</span><span class="sxs-lookup"><span data-stu-id="880eb-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="880eb-124">允许被调用方在 `SetLastError` 从属性化方法返回之前调用 Win32 函数。</span><span class="sxs-lookup"><span data-stu-id="880eb-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="880eb-125">保留</span><span class="sxs-lookup"><span data-stu-id="880eb-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="880eb-126">使用默认平台调用约定。</span><span class="sxs-lookup"><span data-stu-id="880eb-126">Use the default platform calling convention.</span></span> <span data-ttu-id="880eb-127">例如，在 Windows 上，默认值为 `StdCall` ，在 Windows CE .net 上是 `Cdecl` 。</span><span class="sxs-lookup"><span data-stu-id="880eb-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="880eb-128">使用 `Cdecl` 调用约定。</span><span class="sxs-lookup"><span data-stu-id="880eb-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="880eb-129">在这种情况下，调用方会清理堆栈。</span><span class="sxs-lookup"><span data-stu-id="880eb-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="880eb-130">这样就可以使用调用函数 `varargs` （即，接受可变数量的参数的函数）。</span><span class="sxs-lookup"><span data-stu-id="880eb-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="880eb-131">使用 `StdCall` 调用约定。</span><span class="sxs-lookup"><span data-stu-id="880eb-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="880eb-132">在这种情况下，被调用方清理堆栈。</span><span class="sxs-lookup"><span data-stu-id="880eb-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="880eb-133">这是使用平台 invoke 调用非托管函数的默认约定。</span><span class="sxs-lookup"><span data-stu-id="880eb-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="880eb-134">使用 `ThisCall` 调用约定。</span><span class="sxs-lookup"><span data-stu-id="880eb-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="880eb-135">在这种情况下，第一个参数是 `this` 指针，它存储在寄存器 ECX 中。</span><span class="sxs-lookup"><span data-stu-id="880eb-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="880eb-136">其他参数被推送到堆栈上。</span><span class="sxs-lookup"><span data-stu-id="880eb-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="880eb-137">`ThisCall`调用约定用于对从非托管 DLL 导出的类调用方法。</span><span class="sxs-lookup"><span data-stu-id="880eb-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="880eb-138">保留。</span><span class="sxs-lookup"><span data-stu-id="880eb-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="880eb-139">保留。</span><span class="sxs-lookup"><span data-stu-id="880eb-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="880eb-140">要求</span><span class="sxs-lookup"><span data-stu-id="880eb-140">Requirements</span></span>  
 <span data-ttu-id="880eb-141">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="880eb-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="880eb-142">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="880eb-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="880eb-143">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="880eb-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="880eb-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="880eb-144">See also</span></span>

- [<span data-ttu-id="880eb-145">元数据枚举</span><span class="sxs-lookup"><span data-stu-id="880eb-145">Metadata Enumerations</span></span>](metadata-enumerations.md)
