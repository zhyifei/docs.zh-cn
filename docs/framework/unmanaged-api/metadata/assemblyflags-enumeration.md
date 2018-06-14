---
title: AssemblyFlags 枚举
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fc6d08e960b0ba82c76945a318ec723546f71b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444901"
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags 枚举
包含值，用于描述程序集的运行时功能。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`afImplicitExportedTypes`|指定导出的类型定义是隐式包含该程序集的文件内。 在.NET framework 1.0 和 1.1 版中，此值始终假定要设置。|  
|`afImplicitResources`|指定资源定义是隐式包含该程序集的文件内。 在.NET Framework 1.0 和 1.1 中，此值始终假定要设置。|  
|`afNonSideBySideAppDomain`|指定程序集无法与其他版本执行，是否它们在同一应用程序域中运行。|  
|`afNonSideBySideProcess`|指定程序集无法与其他版本执行，是否它们相同的进程中运行。|  
|`afNonSideBySideMachine`|指定程序集无法与其他版本执行，是否同一台计算机上运行。|  
  
## <a name="remarks"></a>备注  
 0x0010 和 0x0070 （含)，之间的值用于描述的引用的程序集的并排显示兼容性功能。 如果这些值均未设置，则假定程序集是通过并行兼容。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MsCorEE.h  
  
 **库：** 作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
