---
title: COR_VERSION 结构
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
ms.openlocfilehash: cc9a67e16635209c3bf303e97dc3e5938943a653
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099090"
---
# <a name="cor_version-structure"></a>COR_VERSION 结构
存储由四个部分组成的公共语言运行时标准版本号。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`dwMajor`|主版本号。|  
|`dwMinor`|次版本号。|  
|`dwBuild`|内部版本号。|  
|`dwSubBuild`|子内部版本号。|  
  
## <a name="remarks"></a>备注  
 如果版本号为1.0.3705.288，1为主要版本号，0为次版本号，3705为内部版本号，288为子内部版本号。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl .idl  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试结构](debugging-structures.md)
- [调试](index.md)
