---
title: COUNINITIEE 枚举
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dcd7dc7c51caa94308760c0086384c8eea184ee9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443592"
---
# <a name="couninitiee-enumeration"></a>COUNINITIEE 枚举
指定使用的常量[CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)初始化公共语言运行时。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|指示默认未初始化模式。|  
|`COUNINITEE_DLL`|指示用于卸载程序集的未初始化模式。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
