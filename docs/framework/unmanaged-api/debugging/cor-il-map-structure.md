---
title: COR_IL_MAP 结构
ms.date: 03/30/2017
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
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179296"
---
# <a name="cor_il_map-structure"></a>COR_IL_MAP 结构
指定函数的相对偏移量的更改。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a>成员  
  
|成员|说明|  
|------------|-----------------|  
|`oldOffset`|旧的 Microsoft 中间语言 （MSIL） 相对于函数的开头偏移。|  
|`newOffset`|新的 MSIL 相对于函数的开头偏移。|  
|`fAccurate`|`true`如果已知映射准确;如果映射准确;否则， `false`.|  
  
## <a name="remarks"></a>备注  
 地图的格式如下：调试器将假定引用`oldOffset`原始未修改的 MSIL 代码中的 MSIL 偏移量。 该`newOffset`参数是指新检测代码中的相应 MSIL 偏移量。  
  
 为了正常工作，应满足以下要求：  
  
- 地图应按升序排序。  
  
- 不应重新排序已检测的 MSIL 代码。  
  
- 不应删除原始 MSIL 代码。  
  
- 地图应包括用于映射程序数据库 （PDB） 文件中的所有序列点的条目。  
  
 地图不会插值缺少的条目。 下面的示例显示地图及其结果。  
  
 Map:  
  
- 0 旧偏移，0 新偏移  
  
- 5 个旧偏移，10 个新偏移  
  
- 9 个旧偏移，20 个新偏移  
  
 结果：  
  
- 旧偏移 0、1、2、3 或 4 将映射到新的偏移量 0。  
  
- 旧偏移 5、6、7 或 8 将映射到新的偏移量 10。  
  
- 旧偏移量为 9 或更高，将映射到新的偏移量 20。  
  
- 新的偏移量为 0、1、2、3、4、5、6、7、8 或 9 将映射到旧偏移 0。  
  
- 10、11、12、13、14、15、16、17、18 或 19 的新偏移将映射到旧偏移 5。  
  
- 新的偏移量为 20 或更高，将映射到旧偏移 9。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** 科尔科调试.idl， 科尔普罗芬.伊德尔  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
