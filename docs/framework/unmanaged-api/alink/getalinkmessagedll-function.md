---
title: "GetALinkMessageDll 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16657c62d66db1570ad379ff5d42a75aaf3ea2a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getalinkmessagedll-function"></a>GetALinkMessageDll 函数
查找并加载 DLL 的消息。 如果无法找到或加载 DLL 的消息，则返回 0。 消息 DLL 应在其名称是一个语言 ID，一个子目录或当前目录中。  
  
## <a name="syntax"></a>语法  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a>惠?  
 **标头：** alink.h  
  
 **库**: alink.dll  
  
## <a name="see-also"></a>请参阅  
 [Al.exe（程序集链接器）](../../../../docs/framework/tools/al-exe-assembly-linker.md)
