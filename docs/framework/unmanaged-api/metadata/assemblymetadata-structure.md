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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83f6190872ecf4435688f3b7c82a61f5f15d9f62
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443321"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA 结构
包含有关所引用的程序集，包括其版本和其级别的支持的区域设置、 处理器和操作系统信息。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`usMajorVersion`|主版本号，引用程序集。 此值不能为零。 如果所有的位`usMajorVersion`的设置，未指定的主版本。|  
|`usMinorVersion`|引用的程序集的次版本号。 此值不能为零。 如果所有的位`usMinorVersion`的设置，未指定的次版本。|  
|`usBuildNumber`|引用的程序集的生成号。 此值不能为零。 如果所有的位`usBuildNumber`的设置，未指定的生成号。|  
|`usRevisionNumber`|引用的程序集修订号。 此值不能为零。 如果所有的位`usRevisionNumber`的设置，未指定修订号。|  
|`szLocale`|符合 RFC1766 规范中，由分号分隔，指定所引用的程序集支持的区域设置的区域设置名称的列表。 Null 值表示区域设置独立性。 **注意：** .NET Framework 版本 1.0 不能指定多个区域设置中。|  
|`cbLocale`|在宽字符为单位的大小`szLocale`。|  
|`rdwProcessor`|标识符，如 Winnt.h 中的定义被引用程序集支持的处理器类型的数组。 一个 NULL 值指示处理器独立性。|  
|`ulProcessor`|长度`rdwProcessor`数组。|  
|`rOS`|数组[OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)指定引用的程序集支持的操作系统的实例。 一个 NULL 值指示操作系统独立性。|  
|`ulOS`|长度`rOS`数组。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据结构](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [OSINFO 结构](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
