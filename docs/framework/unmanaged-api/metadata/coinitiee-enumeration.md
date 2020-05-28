---
title: COINITIEE 枚举
ms.date: 03/30/2017
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
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005903"
---
# <a name="coinitiee-enumeration"></a>COINITIEE 枚举
指定初始化公共语言运行时[CoInitializeEE](../hosting/coinitializeee-function.md)使用的常量。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|默认初始化模式。 这将初始化运行时并创建默认值 <xref:System.AppDomain> 。|  
|`COINITEE_DLL`|初始化以运行托管 DLL。|  
|`COINITEE_MAIN`|初始化以运行托管 EXE。 这将初始化运行时，但不会创建默认值 <xref:System.AppDomain> ，该默认值是在输入 EXE 的主例程之后创建的。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据枚举](metadata-enumerations.md)
