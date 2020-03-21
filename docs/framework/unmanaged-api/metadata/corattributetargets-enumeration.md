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
ms.openlocfilehash: 51741aa3a6d965c1e9743081628d8ad62e8fb04e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176196"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="1ed5b-102">CorAttributeTargets 枚举</span><span class="sxs-lookup"><span data-stu-id="1ed5b-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="1ed5b-103">指定可应用属性的应用程序元素。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ed5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ed5b-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="1ed5b-105">成员</span><span class="sxs-lookup"><span data-stu-id="1ed5b-105">Members</span></span>  
  
|<span data-ttu-id="1ed5b-106">成员</span><span class="sxs-lookup"><span data-stu-id="1ed5b-106">Member</span></span>|<span data-ttu-id="1ed5b-107">说明</span><span class="sxs-lookup"><span data-stu-id="1ed5b-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="1ed5b-108">可以对程序集应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="1ed5b-109">属性可以应用于可移植可执行 （.dll 或 .exe） 模块。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="1ed5b-110">可以对类应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="1ed5b-111">可以对结构应用属性，即值类型。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="1ed5b-112">可以对枚举应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="1ed5b-113">可以对构造函数应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="1ed5b-114">可以对方法应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="1ed5b-115">可以对属性 (Property) 应用属性 (Attribute)。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="1ed5b-116">可以对字段应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="1ed5b-117">可以对事件应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="1ed5b-118">可以对接口应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="1ed5b-119">可以对参数应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="1ed5b-120">可以对委托应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="1ed5b-121">可以对泛型参数应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="1ed5b-122">可以对任何应用程序元素应用属性。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="1ed5b-123">属性可以应用于类的成员。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ed5b-124">备注</span><span class="sxs-lookup"><span data-stu-id="1ed5b-124">Remarks</span></span>  
 <span data-ttu-id="1ed5b-125">枚`CorAttributeTargets`举值可以与位或操作组合，以获得首选组合。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="1ed5b-126">并行`CorAttributeTargets`化托管<xref:System.AttributeTargets?displayProperty=nameWithType>枚举。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ed5b-127">要求</span><span class="sxs-lookup"><span data-stu-id="1ed5b-127">Requirements</span></span>  
 <span data-ttu-id="1ed5b-128">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ed5b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ed5b-129">**标题：** 科尔赫德</span><span class="sxs-lookup"><span data-stu-id="1ed5b-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1ed5b-130">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ed5b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed5b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ed5b-131">See also</span></span>

- [<span data-ttu-id="1ed5b-132">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="1ed5b-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
