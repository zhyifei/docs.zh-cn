---
title: "CorMethodAttr 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorMethodAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodAttr
helpviewer_keywords:
- CorMethodAttr enumeration [.NET Framework metadata]
ms.assetid: 4e0c3521-e54d-43c1-9857-cc76b49b8ffc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4e144b64664a149115f3047b98267c2f218a76e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="98982-102">CorMethodAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="98982-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="98982-103">包含值，用于描述方法的功能。</span><span class="sxs-lookup"><span data-stu-id="98982-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98982-104">语法</span><span class="sxs-lookup"><span data-stu-id="98982-104">Syntax</span></span>  
  
```  
typedef enum CorMethodAttr {  
  
    mdMemberAccessMask          =   0x0007,  
    mdPrivateScope              =   0x0000,  
    mdPrivate                   =   0x0001,  
    mdFamANDAssem               =   0x0002,  
    mdAssem                     =   0x0003,  
    mdFamily                    =   0x0004,  
    mdFamORAssem                =   0x0005,  
    mdPublic                    =   0x0006,  
  
    mdStatic                    =   0x0010,  
    mdFinal                     =   0x0020,  
    mdVirtual                   =   0x0040,  
    mdHideBySig                 =   0x0080,  
  
    mdVtableLayoutMask          =   0x0100,  
    mdReuseSlot                 =   0x0000,  
    mdNewSlot                   =   0x0100,  
  
    mdCheckAccessOnOverride     =   0x0200,  
    mdAbstract                  =   0x0400,  
    mdSpecialName               =   0x0800,  
  
    mdPinvokeImpl               =   0x2000,  
    mdUnmanagedExport           =   0x0008,  
  
    mdReservedMask              =   0xd000,  
    mdRTSpecialName             =   0x1000,  
    mdHasSecurity               =   0x4000,  
    mdRequireSecObject          =   0x8000,  
  
} CorMethodAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="98982-105">成员</span><span class="sxs-lookup"><span data-stu-id="98982-105">Members</span></span>  
  
|<span data-ttu-id="98982-106">成员</span><span class="sxs-lookup"><span data-stu-id="98982-106">Member</span></span>|<span data-ttu-id="98982-107">描述</span><span class="sxs-lookup"><span data-stu-id="98982-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="98982-108">指定成员访问。</span><span class="sxs-lookup"><span data-stu-id="98982-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="98982-109">指定该成员不能被引用。</span><span class="sxs-lookup"><span data-stu-id="98982-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="98982-110">指定的成员是只能由父类型访问。</span><span class="sxs-lookup"><span data-stu-id="98982-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="98982-111">指定的成员是可访问的子类型仅在此程序集。</span><span class="sxs-lookup"><span data-stu-id="98982-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="98982-112">指定的成员是可在程序集中的任何人。</span><span class="sxs-lookup"><span data-stu-id="98982-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="98982-113">指定的成员是只能由类型和子类型访问。</span><span class="sxs-lookup"><span data-stu-id="98982-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="98982-114">指定的成员是可由派生类和在其程序集的其他类型访问。</span><span class="sxs-lookup"><span data-stu-id="98982-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="98982-115">指定成员可由具有访问权限的所有类型到的作用域访问。</span><span class="sxs-lookup"><span data-stu-id="98982-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="98982-116">指定该成员已定义类型的一部分，而不是实例的成员。</span><span class="sxs-lookup"><span data-stu-id="98982-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="98982-117">指定不重写方法。</span><span class="sxs-lookup"><span data-stu-id="98982-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="98982-118">指定该方法可以重写。</span><span class="sxs-lookup"><span data-stu-id="98982-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="98982-119">指定的方法隐藏按名称和签名，而不是只按名称。</span><span class="sxs-lookup"><span data-stu-id="98982-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="98982-120">指定虚拟表布局。</span><span class="sxs-lookup"><span data-stu-id="98982-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="98982-121">指定用于虚拟表中的此方法的槽可重复使用。</span><span class="sxs-lookup"><span data-stu-id="98982-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="98982-122">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="98982-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="98982-123">指定该方法总是获取虚拟表中的新槽。</span><span class="sxs-lookup"><span data-stu-id="98982-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="98982-124">指定可以对其是可见的相同类型中重写该方法。</span><span class="sxs-lookup"><span data-stu-id="98982-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="98982-125">指定未实现方法。</span><span class="sxs-lookup"><span data-stu-id="98982-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="98982-126">指定该方法是特殊的并且其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="98982-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="98982-127">指定使用 PInvoke 转发方法的实现。</span><span class="sxs-lookup"><span data-stu-id="98982-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="98982-128">指定的方法是导出到非托管代码的托管的方法。</span><span class="sxs-lookup"><span data-stu-id="98982-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="98982-129">保留供内部使用公共语言运行时。</span><span class="sxs-lookup"><span data-stu-id="98982-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="98982-130">指定公共语言运行时，应检查的方法名称的编码。</span><span class="sxs-lookup"><span data-stu-id="98982-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="98982-131">指定该方法有与之关联的安全。</span><span class="sxs-lookup"><span data-stu-id="98982-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="98982-132">指定该方法调用包含安全代码的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="98982-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98982-133">惠?</span><span class="sxs-lookup"><span data-stu-id="98982-133">Requirements</span></span>  
 <span data-ttu-id="98982-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98982-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98982-135">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="98982-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="98982-136">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98982-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98982-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="98982-137">See Also</span></span>  
 [<span data-ttu-id="98982-138">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="98982-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
