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
ms.openlocfilehash: 3d3fd88a2c1ac90f823b23d8d2bcb5b177a625c3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109014"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult 枚举
指示由[CompareAssemblyIdentity](compareassemblyidentity-function.md)函数确定的两个程序集标识的等效性。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|成员名称|描述|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|指示比较匹配项中的所有程序集字段。|  
|`ACR_EquivalentFXUnified`|指示根据 .NET Framework 版本2.0 中的公共语言运行时版本（CLR）统一的程序集版本号，将程序集视为等效。|  
|`ACR_EquivalentPartialFXUnified`|指示程序集的部分匹配，这些程序集基于 .NET Framework 2.0 中的程序集版本号的 CLR 统一。|  
|`ACR_EquivalentPartialMatch`|指示程序集的部分匹配项。|  
|`ACR_EquivalentPartialUnified`|指示程序集的部分匹配，这些程序集基于旧的版本号。|  
|`ACR_EquivalentPartialWeakNamed`|指示只与命名的程序集进行部分匹配。|  
|`ACR_EquivalentUnified`|指示程序集根据 .NET Framework 旧版本中的 CLR 统一版本号被视为等效的。|  
|`ACR_EquivalentWeakNamed`|指示两个只命名的程序集的匹配项，这些程序集的版本号被忽略。|  
|`ACR_NonEquivalent`|指示两个程序集之间未发生匹配。|  
|`ACR_NonEquivalentPartialVersion`|指示除了仅部分匹配的版本号外，这两个程序集匹配。|  
|`ACR_NonEquivalentVersion`|指示两个程序集匹配，但其版本号不匹配。|  
|`ACR_Unknown`|指示非等效的原因未知。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [CompareAssemblyIdentity 函数](compareassemblyidentity-function.md)
- [合成枚举](fusion-enumerations.md)
