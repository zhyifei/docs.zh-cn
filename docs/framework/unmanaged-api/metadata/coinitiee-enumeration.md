---
title: "COINITIEE 枚举"
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
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad117c3efd31cc176281e571b7fde11229c097e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="coinitiee-enumeration"></a>COINITIEE 枚举
指定使用的常量[CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)初始化公共语言运行时。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|默认值初始化模式。 此初始化运行时并创建默认<xref:System.AppDomain>。|  
|`COINITEE_DLL`|初始化运行了托管的 DLL。|  
|`COINITEE_MAIN`|初始化运行托管可执行程序。 此初始化运行时，但不会创建默认值<xref:System.AppDomain>，它在输入该 exe 文件的 main 例程后在创建。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
