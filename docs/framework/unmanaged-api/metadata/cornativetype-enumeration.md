---
title: CorNativeType 枚举
ms.date: 03/30/2017
api_name:
- CorNativeType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeType
helpviewer_keywords:
- CorNativeType enumeration [.NET Framework metadata]
ms.assetid: e47a72f1-9609-48ed-bb34-97170d7f6890
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b28fe8e8fd8b602a01b6358f46f60cdf792ced0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448620"
---
# <a name="cornativetype-enumeration"></a><span data-ttu-id="2a67d-102">CorNativeType 枚举</span><span class="sxs-lookup"><span data-stu-id="2a67d-102">CorNativeType Enumeration</span></span>
<span data-ttu-id="2a67d-103">包含一些值，用于描述本机非托管类型。</span><span class="sxs-lookup"><span data-stu-id="2a67d-103">Contains values that describe native unmanaged types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a67d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a67d-104">Syntax</span></span>  
  
```  
typedef enum CorNativeType {  
  
    NATIVE_TYPE_END                  = 0x0,  
    NATIVE_TYPE_VOID                 = 0x1,  
    NATIVE_TYPE_BOOLEAN              = 0x2,  
    NATIVE_TYPE_I1                   = 0x3,  
    NATIVE_TYPE_U1                   = 0x4,  
    NATIVE_TYPE_I2                   = 0x5,  
    NATIVE_TYPE_U2                   = 0x6,  
    NATIVE_TYPE_I4                   = 0x7,  
    NATIVE_TYPE_U4                   = 0x8,  
    NATIVE_TYPE_I8                   = 0x9,  
    NATIVE_TYPE_U8                   = 0xa,  
    NATIVE_TYPE_R4                   = 0xb,  
    NATIVE_TYPE_R8                   = 0xc,  
    NATIVE_TYPE_SYSCHAR              = 0xd,  
    NATIVE_TYPE_VARIANT              = 0xe,  
    NATIVE_TYPE_CURRENCY             = 0xf,  
    NATIVE_TYPE_PTR                  = 0x10,  
  
    NATIVE_TYPE_DECIMAL              = 0x11,  
    NATIVE_TYPE_DATE                 = 0x12,  
    NATIVE_TYPE_BSTR                 = 0x13,  
    NATIVE_TYPE_LPSTR                = 0x14,  
    NATIVE_TYPE_LPWSTR               = 0x15,  
    NATIVE_TYPE_LPTSTR               = 0x16,  
    NATIVE_TYPE_FIXEDSYSSTRING       = 0x17,  
    NATIVE_TYPE_OBJECTREF            = 0x18,  
    NATIVE_TYPE_IUNKNOWN             = 0x19,  
    NATIVE_TYPE_IDISPATCH            = 0x1a,  
    NATIVE_TYPE_STRUCT               = 0x1b,  
    NATIVE_TYPE_INTF                 = 0x1c,  
    NATIVE_TYPE_SAFEARRAY            = 0x1d,  
    NATIVE_TYPE_FIXEDARRAY           = 0x1e,  
    NATIVE_TYPE_INT                  = 0x1f,  
    NATIVE_TYPE_UINT                 = 0x20,  
  
    NATIVE_TYPE_NESTEDSTRUCT         = 0x21,  
    NATIVE_TYPE_BYVALSTR             = 0x22,  
    NATIVE_TYPE_ANSIBSTR             = 0x23,  
    NATIVE_TYPE_TBSTR                = 0x24,  
    NATIVE_TYPE_VARIANTBOOL          = 0x25,  
    NATIVE_TYPE_FUNC                 = 0x26,  
  
    NATIVE_TYPE_ASANY                = 0x28,  
    NATIVE_TYPE_ARRAY                = 0x2a,  
    NATIVE_TYPE_LPSTRUCT             = 0x2b,  
    NATIVE_TYPE_CUSTOMMARSHALER      = 0x2c,  
    NATIVE_TYPE_IINSPECTABLE         = 0x2e,  
    NATIVE_TYPE_HSTRING              = 0x2f,  
  
    NATIVE_TYPE_ERROR                = 0x2d,   
  
    NATIVE_TYPE_MAX                  = 0x50  
  
} CorNativeType;  
```  
  
## <a name="members"></a><span data-ttu-id="2a67d-105">成员</span><span class="sxs-lookup"><span data-stu-id="2a67d-105">Members</span></span>  
  
|<span data-ttu-id="2a67d-106">成员</span><span class="sxs-lookup"><span data-stu-id="2a67d-106">Member</span></span>|<span data-ttu-id="2a67d-107">描述</span><span class="sxs-lookup"><span data-stu-id="2a67d-107">Description</span></span>|  
|------------|-----------------|  
|`NATIVE_TYPE_END`|<span data-ttu-id="2a67d-108">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-108">Obsolete.</span></span>|  
|`NATIVE_TYPE_VOID`|<span data-ttu-id="2a67d-109">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-109">Obsolete.</span></span>|  
|`NATIVE_TYPE_BOOLEAN`|<span data-ttu-id="2a67d-110">非零和 FALSE，则为 TRUE 的 4 字节布尔值为零。</span><span class="sxs-lookup"><span data-stu-id="2a67d-110">A 4-byte Boolean value, where TRUE is non-zero and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_I1`|<span data-ttu-id="2a67d-111">一个 8 位有符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-111">A signed 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_U1`|<span data-ttu-id="2a67d-112">一个 8 位无符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-112">An unsigned 8-bit integer value.</span></span>|  
|`NATIVE_TYPE_I2`|<span data-ttu-id="2a67d-113">一个 16 位有符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-113">A signed 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_U2`|<span data-ttu-id="2a67d-114">一个 16 位无符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-114">An unsigned 16-bit integer value.</span></span>|  
|`NATIVE_TYPE_I4`|<span data-ttu-id="2a67d-115">带符号的 32 位整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-115">A signed 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_U4`|<span data-ttu-id="2a67d-116">32 位无符号整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-116">An unsigned 32-bit integer value.</span></span>|  
|`NATIVE_TYPE_I8`|<span data-ttu-id="2a67d-117">一个 64 位有符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-117">A signed 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_U8`|<span data-ttu-id="2a67d-118">一个 64 位无符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-118">An unsigned 64-bit integer value.</span></span>|  
|`NATIVE_TYPE_R4`|<span data-ttu-id="2a67d-119">4 字节浮点数字值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-119">A 4-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_R8`|<span data-ttu-id="2a67d-120">8 字节浮点数字值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-120">An 8-byte floating-point numeric value.</span></span>|  
|`NATIVE_TYPE_SYSCHAR`|<span data-ttu-id="2a67d-121">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-121">Obsolete.</span></span>|  
|`NATIVE_TYPE_VARIANT`|<span data-ttu-id="2a67d-122">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-122">Obsolete.</span></span>|  
|`NATIVE_TYPE_CURRENCY`|<span data-ttu-id="2a67d-123">数值的 COM 类型对应于托管<xref:System.Decimal>类型。</span><span class="sxs-lookup"><span data-stu-id="2a67d-123">A numeric COM type that corresponds to the managed <xref:System.Decimal> type.</span></span>|  
|`NATIVE_TYPE_PTR`|<span data-ttu-id="2a67d-124">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-124">Obsolete.</span></span>|  
|`NATIVE_TYPE_DECIMAL`|<span data-ttu-id="2a67d-125">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-125">Obsolete.</span></span>|  
|`NATIVE_TYPE_DATE`|<span data-ttu-id="2a67d-126">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-126">Obsolete.</span></span>|  
|`NATIVE_TYPE_BSTR`|<span data-ttu-id="2a67d-127">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-127">COM Interop.</span></span>|  
|`NATIVE_TYPE_LPSTR`|<span data-ttu-id="2a67d-128">为 LPSTR 字符串值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-128">An LPSTR string value.</span></span>|  
|`NATIVE_TYPE_LPWSTR`|<span data-ttu-id="2a67d-129">为 LPWSTR 字符串值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-129">An LPWSTR string value.</span></span>|  
|`NATIVE_TYPE_LPTSTR`|<span data-ttu-id="2a67d-130">LPTSTR 字符串值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-130">An LPTSTR string value.</span></span>|  
|`NATIVE_TYPE_FIXEDSYSSTRING`|<span data-ttu-id="2a67d-131">一个固定的、 系统定义的字符串值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-131">A fixed, system-defined string value.</span></span>|  
|`NATIVE_TYPE_OBJECTREF`|<span data-ttu-id="2a67d-132">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-132">Obsolete.</span></span>|  
|`NATIVE_TYPE_IUNKNOWN`|<span data-ttu-id="2a67d-133">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-133">COM Interop.</span></span>|  
|`NATIVE_TYPE_IDISPATCH`|<span data-ttu-id="2a67d-134">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-134">COM Interop.</span></span>|  
|`NATIVE_TYPE_STRUCT`|<span data-ttu-id="2a67d-135">一个本机结构的值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-135">A native structure value.</span></span>|  
|`NATIVE_TYPE_INTF`|<span data-ttu-id="2a67d-136">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-136">COM Interop.</span></span>|  
|`NATIVE_TYPE_SAFEARRAY`|<span data-ttu-id="2a67d-137">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-137">COM Interop.</span></span>|  
|`NATIVE_TYPE_FIXEDARRAY`|<span data-ttu-id="2a67d-138">一个固定长度的数组的值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-138">A fixed-length array value.</span></span>|  
|`NATIVE_TYPE_INT`|<span data-ttu-id="2a67d-139">一个本机的 16 位有符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-139">A native 16-bit signed integer value.</span></span>|  
|`NATIVE_TYPE_UINT`|<span data-ttu-id="2a67d-140">一个本机的 16 位无符号的整数值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-140">A native 16-bit unsigned integer value.</span></span>|  
|`NATIVE_TYPE_NESTEDSTRUCT`|<span data-ttu-id="2a67d-141">已过时。</span><span class="sxs-lookup"><span data-stu-id="2a67d-141">Obsolete.</span></span><br /><br /> <span data-ttu-id="2a67d-142">使用 NATIVE_TYPE_STRUCT。</span><span class="sxs-lookup"><span data-stu-id="2a67d-142">Use NATIVE_TYPE_STRUCT.</span></span>|  
|`NATIVE_TYPE_BYVALSTR`|<span data-ttu-id="2a67d-143">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-143">COM Interop.</span></span>|  
|`NATIVE_TYPE_ANSIBSTR`|<span data-ttu-id="2a67d-144">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-144">COM Interop.</span></span>|  
|`NATIVE_TYPE_TBSTR`|<span data-ttu-id="2a67d-145">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-145">COM Interop.</span></span><br /><br /> <span data-ttu-id="2a67d-146">选择 BSTR 或 ANSIBSTR 因平台而异。</span><span class="sxs-lookup"><span data-stu-id="2a67d-146">Select BSTR or ANSIBSTR depending on the platform.</span></span>|  
|`NATIVE_TYPE_VARIANTBOOL`|<span data-ttu-id="2a67d-147">一个 2 字节布尔值，其中 TRUE 为-1，则返回 FALSE 是零。</span><span class="sxs-lookup"><span data-stu-id="2a67d-147">A 2-byte Boolean value, where TRUE is -1 and FALSE is zero.</span></span>|  
|`NATIVE_TYPE_FUNC`|<span data-ttu-id="2a67d-148">函数指针。</span><span class="sxs-lookup"><span data-stu-id="2a67d-148">A function pointer.</span></span>|  
|`NATIVE_TYPE_ASANY`|<span data-ttu-id="2a67d-149">对任何本机类型的引用。</span><span class="sxs-lookup"><span data-stu-id="2a67d-149">A reference to any native type.</span></span>|  
|`NATIVE_TYPE_ARRAY`|<span data-ttu-id="2a67d-150">对包含未指定类型的成员的数组的引用。</span><span class="sxs-lookup"><span data-stu-id="2a67d-150">A reference to an array with members of an unspecified type.</span></span>|  
|`NATIVE_TYPE_LPSTRUCT`|<span data-ttu-id="2a67d-151">指向一个结构的 32 位整数指针。</span><span class="sxs-lookup"><span data-stu-id="2a67d-151">A 32-bit integer pointer to a structure.</span></span>|  
|`NATIVE_TYPE_CUSTOMMARSHALER`|<span data-ttu-id="2a67d-152">自定义封送处理程序的本机类型。</span><span class="sxs-lookup"><span data-stu-id="2a67d-152">A custom marshaler native type.</span></span><br /><br /> <span data-ttu-id="2a67d-153">这必须跟以下格式的字符串:"本机类型名称/0 自定义封送处理程序类型名称/0 可选 cookie/0"或"{本机类型 GUID} / 0 自定义封送处理程序类型名称/0 可选 cookie/0"</span><span class="sxs-lookup"><span data-stu-id="2a67d-153">This must be followed by a string of the following format: "Native type name/0Custom marshaler type name/0Optional cookie/0" or "{Native type GUID}/0Custom marshaler type name/0Optional cookie/0"</span></span>|  
|`NATIVE_TYPE_ERROR`|<span data-ttu-id="2a67d-154">COM 互操作。</span><span class="sxs-lookup"><span data-stu-id="2a67d-154">COM Interop.</span></span><br /><br /> <span data-ttu-id="2a67d-155">与 ELEMENT_TYPE_I4 此类型将映射到 VT_HRESULT。</span><span class="sxs-lookup"><span data-stu-id="2a67d-155">With ELEMENT_TYPE_I4 this type maps to VT_HRESULT.</span></span>|  
|`NATIVE_TYPE_IINSPECTABLE`|<span data-ttu-id="2a67d-156">一个本机`IInspectable`类型。</span><span class="sxs-lookup"><span data-stu-id="2a67d-156">A native `IInspectable` type.</span></span>|  
|`NATIVE_TYPE_HSTRING`|<span data-ttu-id="2a67d-157">一个本机`HString`。</span><span class="sxs-lookup"><span data-stu-id="2a67d-157">A native `HString`.</span></span>|  
|`NATIVE_TYPE_MAX`|<span data-ttu-id="2a67d-158">无效值。</span><span class="sxs-lookup"><span data-stu-id="2a67d-158">An invalid value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a67d-159">要求</span><span class="sxs-lookup"><span data-stu-id="2a67d-159">Requirements</span></span>  
 <span data-ttu-id="2a67d-160">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a67d-160">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a67d-161">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2a67d-161">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2a67d-162">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a67d-162">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a67d-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a67d-163">See Also</span></span>  
 <xref:System.Runtime.InteropServices.UnmanagedType>  
 [<span data-ttu-id="2a67d-164">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="2a67d-164">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
