---
title: AssemblyComparisonResult 枚举
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82b81ec29dece182548ead046edc7cb754fbf00e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430656"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult 枚举
根据所指示的两个程序集标识，等同性[CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,   
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,    
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,      
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,    
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion    
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>成员  
  
|成员名称|描述|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|指示所有程序集字段比较匹配中。|  
|`ACR_EquivalentFXUnified`|指示该程序集均被视为等效基于.NET Framework 2.0 版中的程序集版本号的公共语言运行时 (CLR) 版本统一。|  
|`ACR_EquivalentPartialFXUnified`|指示基于.NET Framework 2.0 中的程序集版本号的 CLR 统一的程序集进行部分匹配。|  
|`ACR_EquivalentPartialMatch`|指示程序集进行部分匹配。|  
|`ACR_EquivalentPartialUnified`|指示基于旧统一的版本号的程序集进行部分匹配。|  
|`ACR_EquivalentPartialWeakNamed`|指示只需名称的程序集进行部分匹配。|  
|`ACR_EquivalentUnified`|指示该程序集均被视为等效基于旧版本的.NET Framework 中的版本号的 CLR 统一。|  
|`ACR_EquivalentWeakNamed`|指示两个简单命名的程序集已忽略其版本号之间的匹配项。|  
|`ACR_NonEquivalent`|指示两个程序集之间发生任何匹配项。|  
|`ACR_NonEquivalentPartialVersion`|指示两个程序集匹配除其版本号，这仅部分匹配。|  
|`ACR_NonEquivalentVersion`|指示两个程序集匹配除其版本号，这不会匹配。|  
|`ACR_Unknown`|指示不相等性的原因未知。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [CompareAssemblyIdentity 函数](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)  
 [合成枚举](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
