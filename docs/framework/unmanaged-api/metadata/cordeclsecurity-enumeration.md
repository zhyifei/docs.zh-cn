---
title: CorDeclSecurity 枚举
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
ms.openlocfilehash: 98183ed02f8821b7c40852de2d040775d30f2518
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443745"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="a4874-102">CorDeclSecurity 枚举</span><span class="sxs-lookup"><span data-stu-id="a4874-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="a4874-103">指定可以使用声明性安全执行的安全操作。</span><span class="sxs-lookup"><span data-stu-id="a4874-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4874-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4874-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="a4874-105">Members</span><span class="sxs-lookup"><span data-stu-id="a4874-105">Members</span></span>  
  
|<span data-ttu-id="a4874-106">成员</span><span class="sxs-lookup"><span data-stu-id="a4874-106">Member</span></span>|<span data-ttu-id="a4874-107">描述</span><span class="sxs-lookup"><span data-stu-id="a4874-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="a4874-108">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="a4874-109">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="a4874-110">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="a4874-111">要求调用堆栈中的所有高级调用方已被授予当前权限对象所指定的权限。</span><span class="sxs-lookup"><span data-stu-id="a4874-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="a4874-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span><span class="sxs-lookup"><span data-stu-id="a4874-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="a4874-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span><span class="sxs-lookup"><span data-stu-id="a4874-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="a4874-114">仅可以访问此权限对象所指定的资源，即使代码已被授予访问其他资源的权限。</span><span class="sxs-lookup"><span data-stu-id="a4874-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="a4874-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span><span class="sxs-lookup"><span data-stu-id="a4874-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="a4874-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span><span class="sxs-lookup"><span data-stu-id="a4874-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="a4874-117">The caller can request for the minimum permissions required for code to run.</span><span class="sxs-lookup"><span data-stu-id="a4874-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="a4874-118">此操作仅可以在程序集的作用域内使用。</span><span class="sxs-lookup"><span data-stu-id="a4874-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="a4874-119">The caller can request for additional permissions that are optional (not required to run).</span><span class="sxs-lookup"><span data-stu-id="a4874-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="a4874-120">此请求隐式拒绝所有未明确请求的其他权限。</span><span class="sxs-lookup"><span data-stu-id="a4874-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="a4874-121">此操作仅可以在程序集的作用域内使用。</span><span class="sxs-lookup"><span data-stu-id="a4874-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="a4874-122">The caller's request for permissions that might be misused will not be granted.</span><span class="sxs-lookup"><span data-stu-id="a4874-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="a4874-123">此操作仅可以在程序集的作用域内使用。</span><span class="sxs-lookup"><span data-stu-id="a4874-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="a4874-124">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="a4874-125">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="a4874-126">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="a4874-127">要求直接调用方已被授予指定的权限。</span><span class="sxs-lookup"><span data-stu-id="a4874-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="a4874-128">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="a4874-129">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="a4874-130">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="a4874-131">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="a4874-132">保留。</span><span class="sxs-lookup"><span data-stu-id="a4874-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4874-133">要求</span><span class="sxs-lookup"><span data-stu-id="a4874-133">Requirements</span></span>  
 <span data-ttu-id="a4874-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4874-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4874-135">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="a4874-135">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="a4874-136">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4874-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4874-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4874-137">See also</span></span>

- [<span data-ttu-id="a4874-138">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="a4874-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
