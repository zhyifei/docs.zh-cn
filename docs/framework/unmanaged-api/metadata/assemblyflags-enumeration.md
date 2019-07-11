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
ms.openlocfilehash: 502e7841f8c413aa48732bcea0b6c2178d70c061
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776442"
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags 枚举
包含描述运行时功能的程序集的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
|`afImplicitExportedTypes`|指定导出的类型定义是隐式包含程序集的文件中。 在.NET framework 1.0 和 1.1 版中，此值始终假定要设置。|  
|`afImplicitResources`|指定的资源定义中是隐式包含程序集的文件。 在.NET Framework 1.0 和 1.1 中，此值始终假定要设置。|  
|`afNonSideBySideAppDomain`|指定是否在同一应用程序域中运行该程序集不能执行与其他版本。|  
|`afNonSideBySideProcess`|指定是否在同一进程中运行该程序集不能执行与其他版本。|  
|`afNonSideBySideMachine`|指定是否在同一台计算机上运行该程序集不能执行与其他版本。|  
  
## <a name="remarks"></a>备注  
 0x0010 和 0x0070 非独占，之间的值用于描述通过并行兼容性功能的引用的程序集。 如果没有这些值设置，该程序集被假定为通过并行兼容。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MsCorEE.h  
  
 **库：** 包含为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
