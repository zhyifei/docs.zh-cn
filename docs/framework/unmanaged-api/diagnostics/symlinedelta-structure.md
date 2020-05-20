---
title: SYMLINEDELTA 结构
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609295"
---
# <a name="symlinedelta-structure"></a>SYMLINEDELTA 结构
向符号处理程序提供有关因编辑而移动的方法的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`mdMethod`|方法的元数据标记。|  
|`delta`|此方法已移动的行数。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym .idl  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区结构](diagnostics-symbol-store-structures.md)
