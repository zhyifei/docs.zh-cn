---
title: CorElementType 枚举
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
ms.openlocfilehash: a4e9268d292004f447b30c82f1db4d0fe58404fe
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937952"
---
# <a name="corelementtype-enumeration"></a><span data-ttu-id="2e745-102">CorElementType 枚举</span><span class="sxs-lookup"><span data-stu-id="2e745-102">CorElementType Enumeration</span></span>

<span data-ttu-id="2e745-103">指定公共语言运行时 <xref:System.Type>、类型修饰符或元数据类型签名中的类型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="2e745-103">Specifies a common language runtime <xref:System.Type>, a type modifier, or information about a type in a metadata type signature.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e745-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e745-104">Syntax</span></span>

```cpp
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

## <a name="members"></a><span data-ttu-id="2e745-105">Members</span><span class="sxs-lookup"><span data-stu-id="2e745-105">Members</span></span>

|<span data-ttu-id="2e745-106">成员</span><span class="sxs-lookup"><span data-stu-id="2e745-106">Member</span></span>|<span data-ttu-id="2e745-107">描述</span><span class="sxs-lookup"><span data-stu-id="2e745-107">Description</span></span>|
|------------|-----------------|
|`ELEMENT_TYPE_END`|<span data-ttu-id="2e745-108">内部使用。</span><span class="sxs-lookup"><span data-stu-id="2e745-108">Used internally.</span></span>|
|`ELEMENT_TYPE_VOID`|<span data-ttu-id="2e745-109">Void 类型。</span><span class="sxs-lookup"><span data-stu-id="2e745-109">A void type.</span></span>|
|`ELEMENT_TYPE_BOOLEAN`|<span data-ttu-id="2e745-110">布尔类型</span><span class="sxs-lookup"><span data-stu-id="2e745-110">A Boolean type</span></span>|
|`ELEMENT_TYPE_CHAR`|<span data-ttu-id="2e745-111">一个字符类型。</span><span class="sxs-lookup"><span data-stu-id="2e745-111">A character type.</span></span>|
|`ELEMENT_TYPE_I1`|<span data-ttu-id="2e745-112">有符号1字节整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-112">A signed 1-byte integer.</span></span>|
|`ELEMENT_TYPE_U1`|<span data-ttu-id="2e745-113">1 字节无符号整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-113">An unsigned 1-byte integer.</span></span>|
|`ELEMENT_TYPE_I2`|<span data-ttu-id="2e745-114">有符号的2字节整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-114">A signed 2-byte integer.</span></span>|
|`ELEMENT_TYPE_U2`|<span data-ttu-id="2e745-115">无符号2字节整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-115">An unsigned 2-byte integer.</span></span>|
|`ELEMENT_TYPE_I4`|<span data-ttu-id="2e745-116">有符号4字节整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-116">A signed 4-byte integer.</span></span>|
|`ELEMENT_TYPE_U4`|<span data-ttu-id="2e745-117">4字节无符号整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-117">An unsigned 4-byte integer.</span></span>|
|`ELEMENT_TYPE_I8`|<span data-ttu-id="2e745-118">8字节有符号整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-118">A signed 8-byte integer.</span></span>|
|`ELEMENT_TYPE_U8`|<span data-ttu-id="2e745-119">8字节无符号整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-119">An unsigned 8-byte integer.</span></span>|
|`ELEMENT_TYPE_R4`|<span data-ttu-id="2e745-120">4字节浮点数。</span><span class="sxs-lookup"><span data-stu-id="2e745-120">A 4-byte floating point.</span></span>|
|`ELEMENT_TYPE_R8`|<span data-ttu-id="2e745-121">8字节浮点数。</span><span class="sxs-lookup"><span data-stu-id="2e745-121">An 8-byte floating point.</span></span>|
|`ELEMENT_TYPE_STRING`|<span data-ttu-id="2e745-122">System.string 类型。</span><span class="sxs-lookup"><span data-stu-id="2e745-122">A System.String type.</span></span>|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="2e745-123">指针类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-123">A pointer type modifier.</span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="2e745-124">引用类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-124">A reference type modifier.</span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="2e745-125">值类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-125">A value type modifier.</span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="2e745-126">类类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-126">A class type modifier.</span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="2e745-127">类变量类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-127">A class variable type modifier.</span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="2e745-128">多维数组类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-128">A multi-dimensional array type modifier.</span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="2e745-129">泛型类型的类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-129">A type modifier for generic types.</span></span>|
|`ELEMENT_TYPE_TYPEDBYREF`|<span data-ttu-id="2e745-130">类型化的引用。</span><span class="sxs-lookup"><span data-stu-id="2e745-130">A typed reference.</span></span>|
|`ELEMENT_TYPE_I`|<span data-ttu-id="2e745-131">本机整数的大小。</span><span class="sxs-lookup"><span data-stu-id="2e745-131">Size of a native integer.</span></span>|
|`ELEMENT_TYPE_U`|<span data-ttu-id="2e745-132">无符号本机整数的大小。</span><span class="sxs-lookup"><span data-stu-id="2e745-132">Size of an unsigned native integer.</span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="2e745-133">指向函数的指针。</span><span class="sxs-lookup"><span data-stu-id="2e745-133">A pointer to a function.</span></span>|
|`ELEMENT_TYPE_OBJECT`|<span data-ttu-id="2e745-134">System.object 类型。</span><span class="sxs-lookup"><span data-stu-id="2e745-134">A System.Object type.</span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="2e745-135">一维的、从零开始的下限数组类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-135">A single-dimensional, zero lower-bound array type modifier.</span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="2e745-136">方法变量类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-136">A method variable type modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="2e745-137">C 语言必需的修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-137">A C language required modifier.</span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="2e745-138">C 语言可选修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-138">A C language optional modifier.</span></span>|
|`ELEMENT_TYPE_INTERNAL`|<span data-ttu-id="2e745-139">内部使用。</span><span class="sxs-lookup"><span data-stu-id="2e745-139">Used internally.</span></span>|
|`ELEMENT_TYPE_MAX`|<span data-ttu-id="2e745-140">无效类型。</span><span class="sxs-lookup"><span data-stu-id="2e745-140">An invalid type.</span></span>|
|`ELEMENT_TYPE_MODIFIER`|<span data-ttu-id="2e745-141">内部使用。</span><span class="sxs-lookup"><span data-stu-id="2e745-141">Used internally.</span></span>|
|`ELEMENT_TYPE_SENTINEL`|<span data-ttu-id="2e745-142">作为参数数目可变的列表的 sentinel 的类型修饰符。</span><span class="sxs-lookup"><span data-stu-id="2e745-142">A type modifier that is a sentinel for a list of a variable number of parameters.</span></span>|
|`ELEMENT_TYPE_PINNED`|<span data-ttu-id="2e745-143">内部使用。</span><span class="sxs-lookup"><span data-stu-id="2e745-143">Used internally.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2e745-144">备注</span><span class="sxs-lookup"><span data-stu-id="2e745-144">Remarks</span></span>

<span data-ttu-id="2e745-145">类型修饰符构成了用于表示更复杂类型的基础。</span><span class="sxs-lookup"><span data-stu-id="2e745-145">The type modifiers form the basis for representing more complex types.</span></span> <span data-ttu-id="2e745-146">`CorElementType` 类型修饰符值应用于在类型签名中紧跟在其后面的值。</span><span class="sxs-lookup"><span data-stu-id="2e745-146">A `CorElementType` type modifier value is applied to the value that immediately follows it in the type signature.</span></span> <span data-ttu-id="2e745-147">按照下表中的说明，`CorElementType` 类型修饰符值之后的值可以是一个 `CorElementType` 简单类型值、一个元数据标记或其他值。</span><span class="sxs-lookup"><span data-stu-id="2e745-147">The value that follows the `CorElementType` type modifier value can be a `CorElementType` simple type value, a metadata token, or other value, as specified in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="2e745-148">所有数字（*数字*、*参数计数*、*元数据标记*、*排名*、*计数*和*界限*）都存储为压缩整数。</span><span class="sxs-lookup"><span data-stu-id="2e745-148">All numbers (*number*, *argument Count*, *metadata token*, *rank*, *count*, and *bound*) are stored as compressed integers.</span></span> <span data-ttu-id="2e745-149">有关详细信息，请参阅 ECMA 网站上的[标准 ECMA-335-公共语言基础结构（CLI）](http://www.ecma-international.org/publications/standards/Ecma-335.htm) 。</span><span class="sxs-lookup"><span data-stu-id="2e745-149">See [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) on the ECMA Web site for details.</span></span>

|<span data-ttu-id="2e745-150">类型修饰符</span><span class="sxs-lookup"><span data-stu-id="2e745-150">Type modifier</span></span>|<span data-ttu-id="2e745-151">格式</span><span class="sxs-lookup"><span data-stu-id="2e745-151">Format</span></span>|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|<span data-ttu-id="2e745-152">ELEMENT_TYPE_PTR \<`CorElementType` 值 ></span><span class="sxs-lookup"><span data-stu-id="2e745-152">ELEMENT_TYPE_PTR \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_BYREF`|<span data-ttu-id="2e745-153">ELEMENT_TYPE_BYREF \<`CorElementType` 值 ></span><span class="sxs-lookup"><span data-stu-id="2e745-153">ELEMENT_TYPE_BYREF \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_VALUETYPE`|<span data-ttu-id="2e745-154">`mdTypeDef` 元数据标记 \<ELEMENT_TYPE_VALUETYPE ></span><span class="sxs-lookup"><span data-stu-id="2e745-154">ELEMENT_TYPE_VALUETYPE \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CLASS`|<span data-ttu-id="2e745-155">`mdTypeDef` 元数据标记 \<ELEMENT_TYPE_CLASS ></span><span class="sxs-lookup"><span data-stu-id="2e745-155">ELEMENT_TYPE_CLASS \<an `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_VAR`|<span data-ttu-id="2e745-156">\<号码 ELEMENT_TYPE_VAR ></span><span class="sxs-lookup"><span data-stu-id="2e745-156">ELEMENT_TYPE_VAR \<number></span></span>|
|`ELEMENT_TYPE_ARRAY`|<span data-ttu-id="2e745-157">ELEMENT_TYPE_ARRAY \<`CorElementType` 值 > \<> \<> \<> \<> \<</span><span class="sxs-lookup"><span data-stu-id="2e745-157">ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN> \<boundN></span></span>|
|`ELEMENT_TYPE_GENERICINST`|<span data-ttu-id="2e745-158">ELEMENT_TYPE_GENERICINST \<`mdTypeDef` 元数据令牌 > \<参数计数 > \<arg1 > ... \<argN ></span><span class="sxs-lookup"><span data-stu-id="2e745-158">ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ... \<argN></span></span>|
|`ELEMENT_TYPE_FNPTR`|<span data-ttu-id="2e745-159">ELEMENT_TYPE_FNPTR \<函数的完整签名，包括调用约定 ></span><span class="sxs-lookup"><span data-stu-id="2e745-159">ELEMENT_TYPE_FNPTR \<complete signature for the function, including calling convention></span></span>|
|`ELEMENT_TYPE_SZARRAY`|<span data-ttu-id="2e745-160">ELEMENT_TYPE_SZARRAY \<`CorElementType` 值 ></span><span class="sxs-lookup"><span data-stu-id="2e745-160">ELEMENT_TYPE_SZARRAY \<a `CorElementType` value></span></span>|
|`ELEMENT_TYPE_MVAR`|<span data-ttu-id="2e745-161">\<号码 ELEMENT_TYPE_MVAR ></span><span class="sxs-lookup"><span data-stu-id="2e745-161">ELEMENT_TYPE_MVAR \<number></span></span>|
|`ELEMENT_TYPE_CMOD_REQD`|<span data-ttu-id="2e745-162">ELEMENT_TYPE_\<`mdTypeRef` 或 `mdTypeDef` 的元数据标记 ></span><span class="sxs-lookup"><span data-stu-id="2e745-162">ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|
|`ELEMENT_TYPE_CMOD_OPT`|<span data-ttu-id="2e745-163">E_T_CMOD_OPT \<`mdTypeRef` 或 `mdTypeDef` 的元数据标记 ></span><span class="sxs-lookup"><span data-stu-id="2e745-163">E_T_CMOD_OPT \<a `mdTypeRef` or `mdTypeDef` metadata token></span></span>|

## <a name="requirements"></a><span data-ttu-id="2e745-164">需求</span><span class="sxs-lookup"><span data-stu-id="2e745-164">Requirements</span></span>

<span data-ttu-id="2e745-165">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e745-165">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="2e745-166">**标头：** Corhdr。h</span><span class="sxs-lookup"><span data-stu-id="2e745-166">**Header:** CorHdr.h</span></span>

<span data-ttu-id="2e745-167">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e745-167">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2e745-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e745-168">See also</span></span>

- [<span data-ttu-id="2e745-169">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="2e745-169">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
