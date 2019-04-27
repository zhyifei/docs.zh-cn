---
title: CorAttributeTargets 枚举
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49784a0eba0458a7b9ddbcd58cbe1a187c3c779a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905822"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="f4fe4-102">CorAttributeTargets 枚举</span><span class="sxs-lookup"><span data-stu-id="f4fe4-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="f4fe4-103">指定可应用属性的应用程序元素。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4fe4-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4fe4-104">Syntax</span></span>  
  
```  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="f4fe4-105">成员</span><span class="sxs-lookup"><span data-stu-id="f4fe4-105">Members</span></span>  
  
|<span data-ttu-id="f4fe4-106">成员</span><span class="sxs-lookup"><span data-stu-id="f4fe4-106">Member</span></span>|<span data-ttu-id="f4fe4-107">描述</span><span class="sxs-lookup"><span data-stu-id="f4fe4-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="f4fe4-108">特性可以应用于程序集。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="f4fe4-109">特性可以应用于可移植可执行文件 （.dll 或.exe） 模块。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="f4fe4-110">特性可以应用于类。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="f4fe4-111">特性可以应用于结构;也就是说，类型的值。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="f4fe4-112">特性可以应用于枚举。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="f4fe4-113">特性可以应用于构造函数。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="f4fe4-114">特性可以应用于方法。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="f4fe4-115">特性可以应用于属性。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="f4fe4-116">特性可以应用于字段。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="f4fe4-117">特性可以应用于事件。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="f4fe4-118">特性可以应用于接口。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="f4fe4-119">属性可以应用于参数。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="f4fe4-120">可以对委托应用属性。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="f4fe4-121">特性可以应用于泛型参数。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="f4fe4-122">特性可以应用于任何应用程序元素。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="f4fe4-123">特性可以应用于类的成员。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4fe4-124">备注</span><span class="sxs-lookup"><span data-stu-id="f4fe4-124">Remarks</span></span>  
 <span data-ttu-id="f4fe4-125">`CorAttributeTargets`枚举值可以组合使用位或运算来获得首选的组合。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="f4fe4-126">`CorAttributeTargets`与托管<xref:System.AttributeTargets?displayProperty=nameWithType>枚举。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4fe4-127">要求</span><span class="sxs-lookup"><span data-stu-id="f4fe4-127">Requirements</span></span>  
 <span data-ttu-id="f4fe4-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4fe4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4fe4-129">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f4fe4-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f4fe4-130">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4fe4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4fe4-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4fe4-131">See also</span></span>

- [<span data-ttu-id="f4fe4-132">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="f4fe4-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
