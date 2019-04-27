---
title: USER_THREAD 结构
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11551221732e454e48111d48d60ca9b72f7f9b66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914701"
---
# <a name="userthread-structure"></a>USER_THREAD 结构
提供给关于线程调试程序的信息。 有关详细信息，请参阅[INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`pSidBuffer`|线程缓冲区的地址。|  
|`dwSidLen`|线程缓冲区，以字节为单位的长度。|  
|`dwTid`|线程 id。|  
  
## <a name="requirements"></a>要求  
 **标头：** ProtocolNotify2.idl  
  
## <a name="see-also"></a>请参阅

- [SetNotifyFilter 方法](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md)
- [诊断符号存储区结构](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
