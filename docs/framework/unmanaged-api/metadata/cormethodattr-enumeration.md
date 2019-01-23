---
title: CorMethodAttr 枚举
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a69ca889e226168adb1b84ab64dc0f882c27606
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520524"
---
# <a name="cormethodattr-enumeration"></a><span data-ttu-id="20512-102">CorMethodAttr 枚举</span><span class="sxs-lookup"><span data-stu-id="20512-102">CorMethodAttr Enumeration</span></span>
<span data-ttu-id="20512-103">包含描述一种方法的功能的值。</span><span class="sxs-lookup"><span data-stu-id="20512-103">Contains values that describe the features of a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20512-104">语法</span><span class="sxs-lookup"><span data-stu-id="20512-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="20512-105">成员</span><span class="sxs-lookup"><span data-stu-id="20512-105">Members</span></span>  
  
|<span data-ttu-id="20512-106">成员</span><span class="sxs-lookup"><span data-stu-id="20512-106">Member</span></span>|<span data-ttu-id="20512-107">描述</span><span class="sxs-lookup"><span data-stu-id="20512-107">Description</span></span>|  
|------------|-----------------|  
|`mdMemberAccessMask`|<span data-ttu-id="20512-108">指定成员访问权限。</span><span class="sxs-lookup"><span data-stu-id="20512-108">Specifies member access.</span></span>|  
|`mdPrivateScope`|<span data-ttu-id="20512-109">指定该成员不能被引用。</span><span class="sxs-lookup"><span data-stu-id="20512-109">Specifies that the member cannot be referenced.</span></span>|  
|`mdPrivate`|<span data-ttu-id="20512-110">指定该成员是只能由父类型访问。</span><span class="sxs-lookup"><span data-stu-id="20512-110">Specifies that the member is accessible only by the parent type.</span></span>|  
|`mdFamANDAssem`|<span data-ttu-id="20512-111">指定该成员是仅在此程序集中的子类型访问。</span><span class="sxs-lookup"><span data-stu-id="20512-111">Specifies that the member is accessible by subtypes only in this assembly.</span></span>|  
|`mdAssem`|<span data-ttu-id="20512-112">指定该成员是可访问的程序集中的任何人。</span><span class="sxs-lookup"><span data-stu-id="20512-112">Specifies that the member is accessibly by anyone in the assembly.</span></span>|  
|`mdFamily`|<span data-ttu-id="20512-113">指定该成员是只能由类型和子类型访问。</span><span class="sxs-lookup"><span data-stu-id="20512-113">Specifies that the member is accessible only by type and subtypes.</span></span>|  
|`mdFamORAssem`|<span data-ttu-id="20512-114">指定该成员是可由派生类中它的程序集的其他类型访问。</span><span class="sxs-lookup"><span data-stu-id="20512-114">Specifies that the member is accessible by derived classes and by other types in its assembly.</span></span>|  
|`mdPublic`|<span data-ttu-id="20512-115">指定该成员是由下列所有类型与访问作用域可访问。</span><span class="sxs-lookup"><span data-stu-id="20512-115">Specifies that the member is accessible by all types with access to the scope.</span></span>|  
|`mdStatic`|<span data-ttu-id="20512-116">指定为该类型的一部分而不是实例成员定义成员。</span><span class="sxs-lookup"><span data-stu-id="20512-116">Specifies that the member is defined as part of the type rather than as a member of an instance.</span></span>|  
|`mdFinal`|<span data-ttu-id="20512-117">指定不能重写该方法。</span><span class="sxs-lookup"><span data-stu-id="20512-117">Specifies that the method cannot be overridden.</span></span>|  
|`mdVirtual`|<span data-ttu-id="20512-118">指定可以重写该方法。</span><span class="sxs-lookup"><span data-stu-id="20512-118">Specifies that the method can be overridden.</span></span>|  
|`mdHideBySig`|<span data-ttu-id="20512-119">指定的方法按名称和签名，而不是只按名称隐藏。</span><span class="sxs-lookup"><span data-stu-id="20512-119">Specifies that the method hides by name and signature, rather than just by name.</span></span>|  
|`mdVtableLayoutMask`|<span data-ttu-id="20512-120">指定虚拟表布局。</span><span class="sxs-lookup"><span data-stu-id="20512-120">Specifies virtual table layout.</span></span>|  
|`mdReuseSlot`|<span data-ttu-id="20512-121">指定用于此方法在虚拟表中的槽在重用。</span><span class="sxs-lookup"><span data-stu-id="20512-121">Specifies that the slot used for this method in the virtual table be reused.</span></span> <span data-ttu-id="20512-122">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="20512-122">This is the default.</span></span>|  
|`mdNewSlot`|<span data-ttu-id="20512-123">指定此方法总是获取虚拟表中的新槽。</span><span class="sxs-lookup"><span data-stu-id="20512-123">Specifies that the method always gets a new slot in the virtual table.</span></span>|  
|`mdCheckAccessOnOverride`|<span data-ttu-id="20512-124">指定可以通过向其是可见的相同类型中重写该方法。</span><span class="sxs-lookup"><span data-stu-id="20512-124">Specifies that the method can be overridden by the same types to which it is visible.</span></span>|  
|`mdAbstract`|<span data-ttu-id="20512-125">指定未实现方法。</span><span class="sxs-lookup"><span data-stu-id="20512-125">Specifies that the method is not implemented.</span></span>|  
|`mdSpecialName`|<span data-ttu-id="20512-126">指定的方法是特殊字符，其名称描述如何。</span><span class="sxs-lookup"><span data-stu-id="20512-126">Specifies that the method is special, and that its name describes how.</span></span>|  
|`mdPinvokeImpl`|<span data-ttu-id="20512-127">指定使用 PInvoke 转发该方法的实现。</span><span class="sxs-lookup"><span data-stu-id="20512-127">Specifies that the method implementation is forwarded using PInvoke.</span></span>|  
|`mdUnmanagedExport`|<span data-ttu-id="20512-128">指定的方法是导出到非托管代码的托管的方法。</span><span class="sxs-lookup"><span data-stu-id="20512-128">Specifies that the method is a managed method exported to unmanaged code.</span></span>|  
|`mdReservedMask`|<span data-ttu-id="20512-129">公共语言运行时，保留供内部使用。</span><span class="sxs-lookup"><span data-stu-id="20512-129">Reserved for internal use by the common language runtime.</span></span>|  
|`mdRTSpecialName`|<span data-ttu-id="20512-130">指定公共语言运行时应检查的方法名称的编码。</span><span class="sxs-lookup"><span data-stu-id="20512-130">Specifies that the common language runtime should check the encoding of the method name.</span></span>|  
|`mdHasSecurity`|<span data-ttu-id="20512-131">指定该方法具有与之关联的安全。</span><span class="sxs-lookup"><span data-stu-id="20512-131">Specifies that the method has security associated with it.</span></span>|  
|`mdRequireSecObject`|<span data-ttu-id="20512-132">指定该方法调用包含安全代码的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="20512-132">Specifies that the method calls another method containing security code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20512-133">要求</span><span class="sxs-lookup"><span data-stu-id="20512-133">Requirements</span></span>  
 <span data-ttu-id="20512-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20512-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20512-135">**标头：** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="20512-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="20512-136">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20512-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20512-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="20512-137">See also</span></span>
- [<span data-ttu-id="20512-138">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="20512-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
