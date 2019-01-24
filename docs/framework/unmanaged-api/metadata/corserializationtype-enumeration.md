---
title: CorSerializationType 枚举
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70d2d4ed0d2b923b1095fd0ce898330c319fa5cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637367"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="2d18f-102">CorSerializationType 枚举</span><span class="sxs-lookup"><span data-stu-id="2d18f-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="2d18f-103">指定公共语言运行时如何序列化对象。</span><span class="sxs-lookup"><span data-stu-id="2d18f-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d18f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d18f-104">Syntax</span></span>  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="2d18f-105">成员</span><span class="sxs-lookup"><span data-stu-id="2d18f-105">Members</span></span>  
  
|<span data-ttu-id="2d18f-106">成员</span><span class="sxs-lookup"><span data-stu-id="2d18f-106">Member</span></span>|<span data-ttu-id="2d18f-107">描述</span><span class="sxs-lookup"><span data-stu-id="2d18f-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="2d18f-108">序列化的对象是未定义。</span><span class="sxs-lookup"><span data-stu-id="2d18f-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="2d18f-109">将对象序列化为布尔值类型</span><span class="sxs-lookup"><span data-stu-id="2d18f-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="2d18f-110">将对象序列化为字符类型。</span><span class="sxs-lookup"><span data-stu-id="2d18f-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="2d18f-111">对象序列化为 1 字节有符号整数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="2d18f-112">对象序列化为 1 字节无符号整数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="2d18f-113">对象序列化为 2 字节有符号整数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="2d18f-114">对象序列化为 2 字节无符号整数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="2d18f-115">对象序列化为 4 字节有符号整数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="2d18f-116">对象序列化为 4 字节无符号整数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="2d18f-117">对象序列化为 8 字节有符号整数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="2d18f-118">对象序列化为一个无符号的 8 字节整数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="2d18f-119">将对象序列化为 4 字节浮点数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="2d18f-120">将对象序列化为 8 字节浮点数。</span><span class="sxs-lookup"><span data-stu-id="2d18f-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="2d18f-121">将对象序列化为 System.String 类型。</span><span class="sxs-lookup"><span data-stu-id="2d18f-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="2d18f-122">将对象序列化为一维，零的下限的数组。</span><span class="sxs-lookup"><span data-stu-id="2d18f-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="2d18f-123">将对象序列化为泛型类型。</span><span class="sxs-lookup"><span data-stu-id="2d18f-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="2d18f-124">将对象序列化为一个标记对象。</span><span class="sxs-lookup"><span data-stu-id="2d18f-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="2d18f-125">将对象序列化为一个字段。</span><span class="sxs-lookup"><span data-stu-id="2d18f-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="2d18f-126">将对象序列化为一个属性。</span><span class="sxs-lookup"><span data-stu-id="2d18f-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="2d18f-127">将对象序列化为一个枚举。</span><span class="sxs-lookup"><span data-stu-id="2d18f-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d18f-128">要求</span><span class="sxs-lookup"><span data-stu-id="2d18f-128">Requirements</span></span>  
 <span data-ttu-id="2d18f-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d18f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d18f-130">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2d18f-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2d18f-131">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d18f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d18f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d18f-132">See also</span></span>
- [<span data-ttu-id="2d18f-133">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="2d18f-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
