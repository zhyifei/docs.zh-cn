---
title: "COR_IL_MAP 结构"
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
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e2772833d75ced2209896ca37cf6cf37fb965f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corilmap-structure"></a>COR_IL_MAP 结构
指定函数的相对偏移量的更改。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`oldOffset`|旧 Microsoft 中间语言 (MSIL) 偏移量相对于函数的开头。|  
|`newOffset`|相对于函数的开头新 MSIL 偏移量。|  
|`fAccurate`|`true`如果映射已知不准确的。否则为`false`。|  
  
## <a name="remarks"></a>备注  
 映射的格式如下： 调试器将假定`oldOffset`指内原始、 未修改 MSIL 代码的 MSIL 偏移量。 `newOffset`参数是指已插入检测点的最新的代码中的相应 MSIL 偏移量。  
  
 单步执行正常工作，应满足以下要求：  
  
-   应以升序排序映射。  
  
-   已检测的 MSIL 代码不应重新排序。  
  
-   不应删除原始的 MSIL 代码。  
  
-   映射应包括要映射的程序数据库 (PDB) 文件中的所有序列点的条目。  
  
 映射不插入缺失的条目。 下面的示例显示地图和其结果。  
  
 映射：  
  
-   旧偏移量为 0，0 新的偏移量  
  
-   旧偏移量为 5，10 个新的偏移量  
  
-   9 旧的偏移量，新偏移量为 20  
  
 结果：  
  
-   旧偏移量为 0、 1、 2、 3 或 4 将映射到新的偏移量为 0。  
  
-   旧偏移量为 5、 6、 7 或 8 将映射到新偏移量为 10。  
  
-   旧偏移量 9 或更高版本将映射到新偏移量为 20。  
  
-   新偏移量 0、 1、 2、 3、 4、 5、 6、 7、 8 或 9 将映射到旧偏移量为 0。  
  
-   10、 11、 12、 13、 14、 15、 16、 17、 18 或 19 的新的偏移量将映射到旧偏移量为 5。  
  
-   20 或更高版本的新的偏移量将映射到旧偏移量为 9。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorProf.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试结构](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
