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
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178293"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult 枚举
指示由[比较装配标识](compareassemblyidentity-function.md)函数确定的两个程序集标识的等效性。  
  
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
  
## <a name="members"></a>成员  
  
|成员名称|说明|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|指示比较中的所有程序集字段匹配。|  
|`ACR_EquivalentFXUnified`|指示基于 .NET Framework 版本 2.0 中程序集版本 2.0 中程序集版本编号的通用语言运行时版本 （CLR） 统一，将程序集视为等效。|  
|`ACR_EquivalentPartialFXUnified`|指示基于 .NET 框架 2.0 中程序集版本号的 CLR 统一的程序集的部分匹配。|  
|`ACR_EquivalentPartialMatch`|指示程序集的部分匹配。|  
|`ACR_EquivalentPartialUnified`|指示基于版本号的旧统一的程序集的部分匹配。|  
|`ACR_EquivalentPartialWeakNamed`|指示简单命名程序集的部分匹配。|  
|`ACR_EquivalentUnified`|指示基于 .NET Framework 旧版本中版本号的 CLR 统一，将程序集视为等效。|  
|`ACR_EquivalentWeakNamed`|指示两个简单命名的程序集之间的匹配，其版本号被忽略。|  
|`ACR_NonEquivalent`|指示两个程序集之间没有匹配。|  
|`ACR_NonEquivalentPartialVersion`|指示两个程序集匹配，但版本号除外，只有部分匹配。|  
|`ACR_NonEquivalentVersion`|指示两个程序集匹配，但版本号不匹配。|  
|`ACR_Unknown`|指示非等价的原因尚不清楚。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** 融合.h  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [CompareAssemblyIdentity 函数](compareassemblyidentity-function.md)
- [合成枚举](fusion-enumerations.md)
