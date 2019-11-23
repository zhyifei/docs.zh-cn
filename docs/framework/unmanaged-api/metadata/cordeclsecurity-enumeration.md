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
# <a name="cordeclsecurity-enumeration"></a>CorDeclSecurity 枚举
指定可以使用声明性安全执行的安全操作。  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`dclActionMask`|保留。|  
|`dclActionNil`|保留。|  
|`dclRequest`|保留。|  
|`dclDemand`|要求调用堆栈中的所有高级调用方已被授予当前权限对象所指定的权限。|  
|`dclAssert`|The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource|  
|`dclDeny`|The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.|  
|`dclPermitOnly`|仅可以访问此权限对象所指定的资源，即使代码已被授予访问其他资源的权限。|  
|`dclLinktimeCheck`|The immediate caller is required to have been granted the specified permission for a given period of time.|  
|`dclInheritanceCheck`|The derived class inheriting another class or overriding a method is required to have been granted the specified permission.|  
|`dclRequestMinimum`|The caller can request for the minimum permissions required for code to run. 此操作仅可以在程序集的作用域内使用。|  
|`dclRequestOptional`|The caller can request for additional permissions that are optional (not required to run). 此请求隐式拒绝所有未明确请求的其他权限。 此操作仅可以在程序集的作用域内使用。|  
|`dclRequestRefuse`|The caller's request for permissions that might be misused will not be granted. 此操作仅可以在程序集的作用域内使用。|  
|`dclPrejitGrant`|保留。|  
|`dclPrejitDenied`|保留。|  
|`dclNonCasDemand`|保留。|  
|`dclNonCasLinkDemand`|要求直接调用方已被授予指定的权限。|  
|`dclNonCasInheritance`|保留。|  
|`dclLinkDemandChoice`|保留。|  
|`dclInheritanceDemandChoice`|保留。|  
|`dclDemandChoice`|保留。|  
|`dclMaximumValue`|保留。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **Header:** CorHdr.h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
