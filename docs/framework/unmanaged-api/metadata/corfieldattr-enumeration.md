---
title: CorFieldAttr 枚举
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b07388b7f7385e93a6ca891e8ea98a2ce69763c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576010"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="e4106-102">CorFieldAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="e4106-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="e4106-103">包含一些值，用于描述字段的相应元数据。</span><span class="sxs-lookup"><span data-stu-id="e4106-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4106-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4106-104">Syntax</span></span>  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="e4106-105">成员</span><span class="sxs-lookup"><span data-stu-id="e4106-105">Members</span></span>  
  
|<span data-ttu-id="e4106-106">成员</span><span class="sxs-lookup"><span data-stu-id="e4106-106">Member</span></span>|<span data-ttu-id="e4106-107">描述</span><span class="sxs-lookup"><span data-stu-id="e4106-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="e4106-108">指定可访问性信息。</span><span class="sxs-lookup"><span data-stu-id="e4106-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="e4106-109">指定不能引用的字段。</span><span class="sxs-lookup"><span data-stu-id="e4106-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="e4106-110">指定字段只能由其父类型访问。</span><span class="sxs-lookup"><span data-stu-id="e4106-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="e4106-111">指定字段是由其程序集中的派生类可访问。</span><span class="sxs-lookup"><span data-stu-id="e4106-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="e4106-112">指定该字段是可由其程序集中的所有类型访问。</span><span class="sxs-lookup"><span data-stu-id="e4106-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="e4106-113">指定该字段只能由其类型访问和派生类。</span><span class="sxs-lookup"><span data-stu-id="e4106-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="e4106-114">指定该字段可由派生类中它的程序集的所有类型访问。</span><span class="sxs-lookup"><span data-stu-id="e4106-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="e4106-115">指定字段具有可见性的所有类型，此作用域的访问。</span><span class="sxs-lookup"><span data-stu-id="e4106-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="e4106-116">指定字段及其类型的成员，而不是实例成员。</span><span class="sxs-lookup"><span data-stu-id="e4106-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="e4106-117">指定在初始化后，无法更改该字段。</span><span class="sxs-lookup"><span data-stu-id="e4106-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="e4106-118">指定字段值是一个编译时常量。</span><span class="sxs-lookup"><span data-stu-id="e4106-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="e4106-119">指定项目扩展其类型时，该字段不会序列化。</span><span class="sxs-lookup"><span data-stu-id="e4106-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="e4106-120">指定该字段是特殊的并且其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="e4106-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="e4106-121">指定字段实现通过 PInvoke 转发。</span><span class="sxs-lookup"><span data-stu-id="e4106-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="e4106-122">公共语言运行时，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="e4106-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="e4106-123">指定公共语言运行时元数据内部 Api 应检查该名称的编码。</span><span class="sxs-lookup"><span data-stu-id="e4106-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="e4106-124">指定该字段包含封送处理信息。</span><span class="sxs-lookup"><span data-stu-id="e4106-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="e4106-125">指定该字段具有默认值。</span><span class="sxs-lookup"><span data-stu-id="e4106-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="e4106-126">指定该字段具有相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="e4106-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e4106-127">要求</span><span class="sxs-lookup"><span data-stu-id="e4106-127">Requirements</span></span>  
 <span data-ttu-id="e4106-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4106-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4106-129">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e4106-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e4106-130">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4106-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4106-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4106-131">See also</span></span>
- [<span data-ttu-id="e4106-132">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="e4106-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
