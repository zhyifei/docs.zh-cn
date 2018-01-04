---
title: "CorAttributeTargets 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAttributeTargets
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAttributeTargets
helpviewer_keywords: CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ce701c026b4e977c376b6e6f0f342b031634e38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="e060f-102">CorAttributeTargets 枚举</span><span class="sxs-lookup"><span data-stu-id="e060f-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="e060f-103">指定可应用属性的应用程序元素。</span><span class="sxs-lookup"><span data-stu-id="e060f-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e060f-104">语法</span><span class="sxs-lookup"><span data-stu-id="e060f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e060f-105">成员</span><span class="sxs-lookup"><span data-stu-id="e060f-105">Members</span></span>  
  
|<span data-ttu-id="e060f-106">成员</span><span class="sxs-lookup"><span data-stu-id="e060f-106">Member</span></span>|<span data-ttu-id="e060f-107">描述</span><span class="sxs-lookup"><span data-stu-id="e060f-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="e060f-108">特性可以应用于程序集。</span><span class="sxs-lookup"><span data-stu-id="e060f-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="e060f-109">特性可以应用于可移植可执行文件 （.dll 或.exe） 模块。</span><span class="sxs-lookup"><span data-stu-id="e060f-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="e060f-110">特性可以应用于类。</span><span class="sxs-lookup"><span data-stu-id="e060f-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="e060f-111">特性可以应用于结构;即，类型值。</span><span class="sxs-lookup"><span data-stu-id="e060f-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="e060f-112">特性可以应用于枚举。</span><span class="sxs-lookup"><span data-stu-id="e060f-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="e060f-113">特性可以应用于构造函数。</span><span class="sxs-lookup"><span data-stu-id="e060f-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="e060f-114">特性可以应用于方法。</span><span class="sxs-lookup"><span data-stu-id="e060f-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="e060f-115">特性可以应用于属性。</span><span class="sxs-lookup"><span data-stu-id="e060f-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="e060f-116">特性可以应用于字段。</span><span class="sxs-lookup"><span data-stu-id="e060f-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="e060f-117">特性可以应用于事件。</span><span class="sxs-lookup"><span data-stu-id="e060f-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="e060f-118">特性可以应用于接口。</span><span class="sxs-lookup"><span data-stu-id="e060f-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="e060f-119">特性可以应用于参数。</span><span class="sxs-lookup"><span data-stu-id="e060f-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="e060f-120">特性可以应用于委托。</span><span class="sxs-lookup"><span data-stu-id="e060f-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="e060f-121">特性可以应用于泛型参数。</span><span class="sxs-lookup"><span data-stu-id="e060f-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="e060f-122">特性可以应用于任何应用程序元素。</span><span class="sxs-lookup"><span data-stu-id="e060f-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="e060f-123">特性可以应用于类的成员。</span><span class="sxs-lookup"><span data-stu-id="e060f-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e060f-124">备注</span><span class="sxs-lookup"><span data-stu-id="e060f-124">Remarks</span></span>  
 <span data-ttu-id="e060f-125">`CorAttributeTargets`枚举值可以组合与按位 OR 操作来获得首选的组合。</span><span class="sxs-lookup"><span data-stu-id="e060f-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="e060f-126">`CorAttributeTargets`便可与托管<xref:System.AttributeTargets?displayProperty=nameWithType>枚举。</span><span class="sxs-lookup"><span data-stu-id="e060f-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e060f-127">惠?</span><span class="sxs-lookup"><span data-stu-id="e060f-127">Requirements</span></span>  
 <span data-ttu-id="e060f-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e060f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e060f-129">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e060f-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e060f-130">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e060f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e060f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="e060f-131">See Also</span></span>  
 [<span data-ttu-id="e060f-132">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="e060f-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
