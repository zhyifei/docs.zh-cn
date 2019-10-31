---
title: ASSEMBLY_INFO 结构
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
ms.openlocfilehash: a43d5e15c02a97ff10a6a5afd439cadebb6b33d2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109217"
---
# <a name="assembly_info-structure"></a>ASSEMBLY_INFO 结构
包含有关在全局程序集缓存中注册的程序集的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`cbAssemblyInfo`|结构的大小（以字节为单位）。 此字段保留供将来进行扩展。|  
|`dwAssemblyFlags`|指示程序集的安装详细信息的标志。 支持以下值：<br /><br /> -ASSEMBLYINFO_FLAG_INSTALLED 值，该值指示已安装程序集。 当前版本的 .NET Framework 始终将 `dwAssemblyFlags` 设置为此值。<br />-ASSEMBLYINFO_FLAG_PAYLOADRESIDENT 值，指示程序集是一个有效负载。 .NET Framework 的当前版本从不将 `dwAssemblyFlags` 设置为此值。|  
|`uliAssemblySizeInKB`|程序集包含的文件的总大小（kb）。|  
|`pszCurrentAssemblyPathBuf`|指向包含清单文件的当前路径的字符串缓冲区的指针。 路径必须以 null 字符结尾。|  
|`cchBuf`|`pszCurrentAssemblyPathBuf` 包含的宽字符数，包括 null 结束符。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成结构](fusion-structures.md)
- [全局程序集缓存](../../app-domains/gac.md)
