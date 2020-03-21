---
title: CorSymSearchPolicyAttributes 枚举
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 786e53d43ecde0bc3a97fadb77184d25d41430bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178351"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>CorSymSearchPolicyAttributes 枚举
指定在搜索符号读取器时要使用的策略。 这些常量由[ISymUn 托管 Binder2：：getReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)和[ISymUn托管 Binder3：：getReader 来自回调](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)方法使用。  
  
> [!IMPORTANT]
> 从不受信任的源打开程序数据库 （PDB） 文件存在安全风险。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`AllowRegistryAccess`|查询符号搜索路径的注册表。|  
|`AllowSymbolServerAccess`|访问符号服务器。|  
|`AllowOriginalPathAccess`|搜索调试目录中指定的路径。|  
|`AllowReferencePathAccess`|在 .exe 文件所在的位置搜索 PDB。|  
  
## <a name="requirements"></a>要求  
 **标题：** 科西姆.伊德尔，科西姆.h  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区枚举](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
