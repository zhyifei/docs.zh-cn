---
title: "CorMethodImpl 枚举"
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
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e82eb50e4850ffbb4d5fc67d9603a3128cf8bcf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodimpl-enumeration"></a>CorMethodImpl 枚举
包含一些值，用于描述方法实现功能。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`miCodeTypeMask`|描述代码类型的标志。|  
|`miIL`|指定方法的实现是 Microsoft 中间语言 (MSIL)。|  
|`miNative`|指定方法实现为本机。|  
|`miOPTIL`|指定方法的实现是 OPTIL。|  
|`miRuntime`|指定方法的实现由公共语言运行时。|  
|`miManagedMask`|指示是否是托管或非托管代码的标志。|  
|`miUnmanaged`|指定方法的实现不受管理。|  
|`miManaged`|指定管理方法的实现。|  
|`miForwardRef`|指定定义方法。 此标志是主要用于合并方案。|  
|`miPreserveSig`|指定方法签名，不能改变为使 HRESULT 转换。|  
|`miInternalCall`|保留供内部使用公共语言运行时。|  
|`miSynchronized`|指定的方法是单线程方式通过其正文。|  
|`miNoInlining`|指定方法不能内联。|  
|`miAggressiveInlining`|指定该方法应内联如有可能。|  
|`miNoOptimization`|指定该方法不应优化。|  
|`miMaxMethodImplVal`|最大有效值`CorMethodImpl`。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
