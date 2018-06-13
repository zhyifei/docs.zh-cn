---
title: CorElementType Enumeration1
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ebe2cf95f5637e6924b85c2389f1c59679580298
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449165"
---
# <a name="corelementtype-enumeration1"></a><span data-ttu-id="ad6fa-102">CorElementType Enumeration1</span><span class="sxs-lookup"><span data-stu-id="ad6fa-102">CorElementType Enumeration1</span></span>
<span data-ttu-id="ad6fa-103">指定公共语言运行时<xref:System.Type>、 类型修饰符，或者有关元数据类型签名中类型的信息。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad6fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad6fa-104">Syntax</span></span>  
  
```  
typedef enum CorElementType {  
    ELEMENT_TYPE_END            = 0x0,  
    ELEMENT_TYPE_VOID           = 0x1,  
    ELEMENT_TYPE_BOOLEAN        = 0x2,  
    ELEMENT_TYPE_CHAR           = 0x3,  
    ELEMENT_TYPE_I1             = 0x4,  
    ELEMENT_TYPE_U1             = 0x5,  
    ELEMENT_TYPE_I2             = 0x6,  
    ELEMENT_TYPE_U2             = 0x7,  
    ELEMENT_TYPE_I4             = 0x8,  
    ELEMENT_TYPE_U4             = 0x9,  
    ELEMENT_TYPE_I8             = 0xa,  
    ELEMENT_TYPE_U8             = 0xb,  
    ELEMENT_TYPE_R4             = 0xc,  
    ELEMENT_TYPE_R8             = 0xd,  
    ELEMENT_TYPE_STRING         = 0xe,  
  
    ELEMENT_TYPE_PTR            = 0xf,  
    ELEMENT_TYPE_BYREF          = 0x10,  
  
    ELEMENT_TYPE_VALUETYPE      = 0x11,  
    ELEMENT_TYPE_CLASS          = 0x12,  
    ELEMENT_TYPE_VAR            = 0x13,  
    ELEMENT_TYPE_ARRAY          = 0x14,  
    ELEMENT_TYPE_GENERICINST    = 0x15,  
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,  
  
    ELEMENT_TYPE_I              = 0x18,  
    ELEMENT_TYPE_U              = 0x19,  
    ELEMENT_TYPE_FNPTR          = 0x1B,  
    ELEMENT_TYPE_OBJECT         = 0x1C,  
    ELEMENT_TYPE_SZARRAY        = 0x1D,  
    ELEMENT_TYPE_MVAR           = 0x1e,  
  
    ELEMENT_TYPE_CMOD_REQD      = 0x1F,  
    ELEMENT_TYPE_CMOD_OPT       = 0x20,  
  
    ELEMENT_TYPE_INTERNAL       = 0x21,  
    ELEMENT_TYPE_MAX            = 0x22,  
  
    ELEMENT_TYPE_MODIFIER       = 0x40,  
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,  
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER  
  
} CorElementType;  
```  
  
## <a name="members"></a><span data-ttu-id="ad6fa-105">成员</span><span class="sxs-lookup"><span data-stu-id="ad6fa-105">Members</span></span>  
  
|<span data-ttu-id="ad6fa-106">成员</span><span class="sxs-lookup"><span data-stu-id="ad6fa-106">Member</span></span>|<span data-ttu-id="ad6fa-107">描述</span><span class="sxs-lookup"><span data-stu-id="ad6fa-107">Description</span></span>|  
|------------|-----------------|  
|`ELEMENT_TYPE_END`|<span data-ttu-id="ad6fa-108">内部使用。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-108">Used internally.</span></span>|  
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="ad6fa-109">Void 类型。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-109">A void type.</span></span>|  
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="ad6fa-110">布尔值类型</span><span class="sxs-lookup"><span data-stu-id="ad6fa-110">A Boolean type</span></span>|  
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="ad6fa-111">一个字符类型。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-111">A character type.</span></span>|  
|`ELEMENT_TYPE_I1`|<span data-ttu-id="ad6fa-112">一个带符号的 1 字节整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-112">A signed 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_U1`|<span data-ttu-id="ad6fa-113">1 字节无符号整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-113">An unsigned 1-byte integer.</span></span>|  
|`ELEMENT_TYPE_I2`|<span data-ttu-id="ad6fa-114">一个带符号的 2 字节整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-114">A signed 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_U2`|<span data-ttu-id="ad6fa-115">无符号的 2 字节整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-115">An unsigned 2-byte integer.</span></span>|  
|`ELEMENT_TYPE_I4`|<span data-ttu-id="ad6fa-116">一个带符号的 4 字节整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-116">A signed 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_U4`|<span data-ttu-id="ad6fa-117">无符号的 4 字节整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-117">An unsigned 4-byte integer.</span></span>|  
|`ELEMENT_TYPE_I8`|<span data-ttu-id="ad6fa-118">一个带符号的 8 字节整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-118">A signed 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_U8`|<span data-ttu-id="ad6fa-119">无符号的 8 字节整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-119">An unsigned 8-byte integer.</span></span>|  
|`ELEMENT_TYPE_R4`|<span data-ttu-id="ad6fa-120">4 字节的浮点数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-120">A 4-byte floating point.</span></span>|  
|`ELEMENT_TYPE_R8`|<span data-ttu-id="ad6fa-121">8 字节浮点。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-121">An 8-byte floating point.</span></span>|  
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="ad6fa-122">System.String 类型。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-122">A System.String type.</span></span>|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="ad6fa-123">指针类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-123">A pointer type modifier.</span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="ad6fa-124">引用类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-124">A reference type modifier.</span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="ad6fa-125">值类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-125">A value type modifier.</span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="ad6fa-126">类类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-126">A class type modifier.</span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="ad6fa-127">类变量的类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-127">A class variable type modifier.</span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="ad6fa-128">多维数组类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-128">A multi-dimensional array type modifier.</span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="ad6fa-129">泛型类型的类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-129">A type modifier for generic types.</span></span>|  
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="ad6fa-130">类型化的引用。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-130">A typed reference.</span></span>|  
|`ELEMENT_TYPE_I`|<span data-ttu-id="ad6fa-131">本机整数的大小。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-131">Size of a native integer.</span></span>|  
|`ELEMENT_TYPE_U`|<span data-ttu-id="ad6fa-132">本机的无符号整数的大小。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-132">Size of an unsigned native integer.</span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="ad6fa-133">指向函数的指针。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-133">A pointer to a function.</span></span>|  
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="ad6fa-134">一种 System.Object 类型。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-134">A System.Object type.</span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="ad6fa-135">一维、 零的下限数组的类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="ad6fa-136">方法变量的类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-136">A method variable type modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="ad6fa-137">C 语言必需的修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-137">A C language required modifier.</span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="ad6fa-138">C 语言可选修饰符。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-138">A C language optional modifier.</span></span>|  
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="ad6fa-139">内部使用。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-139">Used internally.</span></span>|  
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="ad6fa-140">无效类型。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-140">An invalid type.</span></span>|  
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="ad6fa-141">内部使用。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-141">Used internally.</span></span>|  
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="ad6fa-142">类型修饰符，有关的可变数目的参数列表 sentinel。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|  
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="ad6fa-143">内部使用。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-143">Used internally.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad6fa-144">备注</span><span class="sxs-lookup"><span data-stu-id="ad6fa-144">Remarks</span></span>  
 <span data-ttu-id="ad6fa-145">类型修饰符构成表示更复杂的类型的基础。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="ad6fa-146">A`CorElementType`类型修饰符值应用于类型签名中紧随该项的值。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="ad6fa-147">之后的值`CorElementType`类型修饰符值可以是`CorElementType`简单类型值、 元数据标记或其他值，指定下表中。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad6fa-148">所有数字 (*数*，*自变量计数*，*元数据标记*，*级别*，*计数*，和*绑定*) 都存储为压缩的整数。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="ad6fa-149">请参阅[标准 ecma-335-公共语言基础结构 (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) ECMA 网站有关的详细信息上。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=116487) on the ECMA Web site for details.</span></span>  
  
|<span data-ttu-id="ad6fa-150">类型修饰符</span><span class="sxs-lookup"><span data-stu-id="ad6fa-150">Type modifier</span></span>|<span data-ttu-id="ad6fa-151">格式</span><span class="sxs-lookup"><span data-stu-id="ad6fa-151">Format</span></span>|  
|-------------------|------------|  
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="ad6fa-152">ELEMENT_TYPE_PTR <`CorElementType`值 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-152">ELEMENT_TYPE_PTR <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="ad6fa-153">ELEMENT_TYPE_BYREF <`CorElementType`值 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-153">ELEMENT_TYPE_BYREF <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="ad6fa-154">ELEMENT_TYPE_VALUETYPE <`mdTypeDef`元数据令牌 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-154">ELEMENT_TYPE_VALUETYPE <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="ad6fa-155">ELEMENT_TYPE_CLASS <`mdTypeDef`元数据令牌 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-155">ELEMENT_TYPE_CLASS <an `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="ad6fa-156">ELEMENT_TYPE_VAR\<数量 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-156">ELEMENT_TYPE_VAR \<number></span></span>|  
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="ad6fa-157">ELEMENT_TYPE_ARRAY <`CorElementType`值 >\<级别 > \<count1 > \<bound1 >...\<countN > \<boundN ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-157">ELEMENT_TYPE_ARRAY <a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|  
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="ad6fa-158">ELEMENT_TYPE_GENERICINST <`mdTypeDef`元数据标记 >\<自变量计数 > \<arg1 >...\<argN ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-158">ELEMENT_TYPE_GENERICINST <an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|  
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="ad6fa-159">ELEMENT_TYPE_FNPTR\<对于函数，包括调用约定的完整签名 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|  
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="ad6fa-160">ELEMENT_TYPE_SZARRAY <`CorElementType`值 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-160">ELEMENT_TYPE_SZARRAY <a `CorElementType` value></span></span>|  
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="ad6fa-161">ELEMENT_TYPE_MVAR\<数量 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-161">ELEMENT_TYPE_MVAR \<number></span></span>|  
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="ad6fa-162">ELEMENT_TYPE_ <`mdTypeRef`或`mdTypeDef`元数据令牌 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-162">ELEMENT_TYPE_<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="ad6fa-163">E_T_CMOD_OPT <`mdTypeRef`或`mdTypeDef`元数据令牌 ></span><span class="sxs-lookup"><span data-stu-id="ad6fa-163">E_T_CMOD_OPT <a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad6fa-164">要求</span><span class="sxs-lookup"><span data-stu-id="ad6fa-164">Requirements</span></span>  
 <span data-ttu-id="ad6fa-165">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad6fa-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad6fa-166">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ad6fa-166">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ad6fa-167">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad6fa-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad6fa-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad6fa-168">See Also</span></span>  
 [<span data-ttu-id="ad6fa-169">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="ad6fa-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
