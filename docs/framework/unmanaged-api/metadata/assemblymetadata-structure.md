---
title: ASSEMBLYMETADATA 结构
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 24ec1f7d553a59425f7eb02af8e91010d940eb07
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444269"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA 结构
包含有关被引用程序集的信息，包括其版本及其对区域设置、处理器和操作系统的支持级别。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`usMajorVersion`|引用的程序集的主版本号。 此值不能为零。 如果设置了 `usMajorVersion` 的所有位，则不指定主版本。|  
|`usMinorVersion`|所引用程序集的次版本号。 此值不能为零。 如果设置了 `usMinorVersion` 的所有位，则不指定次版本。|  
|`usBuildNumber`|引用的程序集的生成号。 此值不能为零。 如果设置了 `usBuildNumber` 的所有位，则不指定内部版本号。|  
|`usRevisionNumber`|引用的程序集的修订号。 此值不能为零。 如果设置了 `usRevisionNumber` 的所有位，则不指定修订号。|  
|`szLocale`|符合 RFC1766 规范（由分号分隔）的区域设置名称的列表，指定被引用程序集支持的区域设置。 空值表示区域设置独立性。 **注意：** 在 .NET Framework 版本1.0 中，不能指定多个区域设置。|  
|`cbLocale`|`szLocale`的大小（以宽字符为大小）。|  
|`rdwProcessor`|Winnt 中定义的标识符的数组，适用于所引用的程序集所支持的处理器类型。 空值表示处理器独立性。|  
|`ulProcessor`|`rdwProcessor` 数组的长度。|  
|`rOS`|指定被引用的程序集支持的操作系统的[OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)实例的数组。 NULL 值指示与操作系统无关。|  
|`ulOS`|`rOS` 数组的长度。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据结构](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [OSINFO 结构](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
