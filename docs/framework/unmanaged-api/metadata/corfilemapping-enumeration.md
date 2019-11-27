---
title: CorFileMapping 枚举
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
ms.openlocfilehash: f85a36c810df52f871ecc75b92a3b4440455c66b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450293"
---
# <a name="corfilemapping-enumeration"></a>CorFileMapping 枚举
包含一些值，这些值描述从对[IMetaDataInfo：： GetFileMapping](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)方法的调用返回的文件映射的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`fmFlat`|文件映射为数据文件。 也就是说，不会将 `SEC_IMAGE` 标志传递到 Microsoft Win32 `CreateFileMapping` 函数。|  
|`fmExecutableImage`|使用 `LoadLibrary` 函数或带有 `SEC_IMAGE` 标志的 `CreateFileMapping` 函数为执行映射文件。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Corhdr。h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [GetFileMapping 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-getfilemapping-method.md)
