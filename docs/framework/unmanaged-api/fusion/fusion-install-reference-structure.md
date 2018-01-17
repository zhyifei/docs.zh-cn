---
title: "FUSION_INSTALL_REFERENCE 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36321606fe208233fb6114fe9568b655f0e1b400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="fusioninstallreference-structure"></a>FUSION_INSTALL_REFERENCE 结构
表示应用程序对应用程序已安装在全局程序集缓存中程序集的引用。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`cbSize`|以字节为单位结构的大小。|  
|`dwFlags`|留待将来扩展。 此值必须为 0 （零）。|  
|`guidScheme`|将引用添加的实体。 此字段可以具有以下值之一：<br /><br /> -FUSION_REFCOUNT_MSI_GUID： 使用 Microsoft Windows Installer 安装的应用程序引用了程序集。 `szIdentifier`字段设置为`MSI`，和`szNonCanonicalData`字段设置为`Windows Installer`。 此方案适用于 Windows 的并行程序集。<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID： 出现在应用程序引用的程序集**添加/删除程序**接口。 `szIdentifier`字段提供注册与该应用程序的令牌**添加/删除程序**接口。<br />-FUSION_REFCOUNT_FILEPATH_GUID： 程序集被引用的应用程序在文件系统中表示的文件。 `szIdentifier`字段提供此文件的路径。<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID： 程序集被引用的应用程序仅由一个不透明的字符串。 `szIdentifier`字段提供此不透明的字符串。 全局程序集缓存不会检查存在不透明引用时删除此值。<br />-FUSION_REFCOUNT_OSINSTALL_GUID： 保留此值。|  
|`szIdentifier`|一个标识的应用程序在全局程序集缓存中安装了程序集的唯一字符串。 其值取决于值`guidScheme`字段。|  
|`szNonCanonicalData`|一个字符串，理解只能通过将引用添加的实体。 全局程序集缓存存储此字符串中，但不使用它。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成结构](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [全局程序集缓存](../../../../docs/framework/app-domains/gac.md)
