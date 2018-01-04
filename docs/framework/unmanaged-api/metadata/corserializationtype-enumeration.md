---
title: "CorSerializationType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSerializationType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSerializationType
helpviewer_keywords: CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e43151b1611f5b9b8218d30ba46a9143f463c193
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="bac90-102">CorSerializationType 枚举</span><span class="sxs-lookup"><span data-stu-id="bac90-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="bac90-103">指定如何将对象序列化公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="bac90-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bac90-104">语法</span><span class="sxs-lookup"><span data-stu-id="bac90-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="bac90-105">成员</span><span class="sxs-lookup"><span data-stu-id="bac90-105">Members</span></span>  
  
|<span data-ttu-id="bac90-106">成员</span><span class="sxs-lookup"><span data-stu-id="bac90-106">Member</span></span>|<span data-ttu-id="bac90-107">描述</span><span class="sxs-lookup"><span data-stu-id="bac90-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="bac90-108">序列化的对象是不确定的。</span><span class="sxs-lookup"><span data-stu-id="bac90-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="bac90-109">将对象序列化为布尔值类型</span><span class="sxs-lookup"><span data-stu-id="bac90-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="bac90-110">将对象序列化为字符类型。</span><span class="sxs-lookup"><span data-stu-id="bac90-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="bac90-111">对象序列化为一个带符号的 1 字节整数。</span><span class="sxs-lookup"><span data-stu-id="bac90-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="bac90-112">对象序列化为的无符号的 1 字节整数。</span><span class="sxs-lookup"><span data-stu-id="bac90-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="bac90-113">对象序列化为一个带符号的 2 字节整数。</span><span class="sxs-lookup"><span data-stu-id="bac90-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="bac90-114">对象序列化为的无符号的 2 字节整数。</span><span class="sxs-lookup"><span data-stu-id="bac90-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="bac90-115">对象序列化为一个带符号的 4 字节整数。</span><span class="sxs-lookup"><span data-stu-id="bac90-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="bac90-116">对象序列化为的无符号的 4 字节整数。</span><span class="sxs-lookup"><span data-stu-id="bac90-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="bac90-117">对象序列化为一个带符号的 8 字节整数。</span><span class="sxs-lookup"><span data-stu-id="bac90-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="bac90-118">对象序列化为的无符号的 8 字节整数。</span><span class="sxs-lookup"><span data-stu-id="bac90-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="bac90-119">将对象序列化为 4 字节浮点数。</span><span class="sxs-lookup"><span data-stu-id="bac90-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="bac90-120">将对象序列化为 8 字节浮点数。</span><span class="sxs-lookup"><span data-stu-id="bac90-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="bac90-121">将对象序列化为 System.String 类型。</span><span class="sxs-lookup"><span data-stu-id="bac90-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="bac90-122">将对象序列化为一维，零的下限的数组。</span><span class="sxs-lookup"><span data-stu-id="bac90-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="bac90-123">将对象序列化为泛型类型。</span><span class="sxs-lookup"><span data-stu-id="bac90-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="bac90-124">将对象序列化为标记对象。</span><span class="sxs-lookup"><span data-stu-id="bac90-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="bac90-125">将对象序列化为一个字段。</span><span class="sxs-lookup"><span data-stu-id="bac90-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="bac90-126">将对象序列化为一个属性。</span><span class="sxs-lookup"><span data-stu-id="bac90-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="bac90-127">将对象序列化为一个枚举。</span><span class="sxs-lookup"><span data-stu-id="bac90-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bac90-128">惠?</span><span class="sxs-lookup"><span data-stu-id="bac90-128">Requirements</span></span>  
 <span data-ttu-id="bac90-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bac90-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bac90-130">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="bac90-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bac90-131">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bac90-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bac90-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="bac90-132">See Also</span></span>  
 [<span data-ttu-id="bac90-133">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="bac90-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
