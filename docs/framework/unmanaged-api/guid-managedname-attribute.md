---
title: "GUID_ManagedName 特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GUID_ManagedName
api_location: alink.dll
api_type: COM
f1_keywords: GUID_ManagedName
helpviewer_keywords: GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 116a9e38b9885f0d0a5afc8f4915b9ce2b50f1dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="guidmanagedname-attribute"></a>GUID_ManagedName 特性
定义指定的组件对象模型 (COM) 库的管理的命名空间名称的自定义接口属性。  
  
## <a name="syntax"></a>语法  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a>参数  
 `value`  
 库管理的命名空间名称。  
  
## <a name="definition"></a>定义  
 `GUID_ManagedName`在定义 Cor.h，如下所示：  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>备注  
 自定义接口特性定义的类型库中的对象的元数据。  
  
 使用<xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType>或<xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType>可从该属性检索托管的名称。  
  
 有关详细信息，请参阅[接口属性](/cpp/windows/interface-attributes)Visual c + + 参考文档。  
  
## <a name="example"></a>示例  
 下面的示例演示库定义使用`GUID_ManagedName`属性。  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** Cor.h
