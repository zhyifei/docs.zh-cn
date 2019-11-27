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
ms.openlocfilehash: 4fd31e6b752e13a5c43198760e9a4d62a8f77d10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448562"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a>CorSymSearchPolicyAttributes 枚举
指定在搜索符号读取器时要使用的策略。 [ISymUnmanagedBinder2：： GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)和[ISymUnmanagedBinder3：： GetReaderFromCallback](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)方法使用这些常量。  
  
> [!IMPORTANT]
> 打开不受信任的源中的程序数据库（PDB）文件会带来安全风险。  
  
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
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`AllowRegistryAccess`|在注册表中查询符号搜索路径。|  
|`AllowSymbolServerAccess`|访问符号服务器。|  
|`AllowOriginalPathAccess`|搜索在调试目录中指定的路径。|  
|`AllowReferencePathAccess`|搜索 .exe 文件所在位置的 PDB。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区枚举](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
