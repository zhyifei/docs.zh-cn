---
title: "ICorDebugProcess2::GetVersion 方法"
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
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 nterface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae9c80a65908d6ec1514ce64845217bd7b5c7805
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getversion-method"></a>ICorDebugProcess2::GetVersion 方法
获取在此进程中运行公共语言运行时 (CLR) 的版本号。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetVersion (  
    [out] COR_VERSION     *version  
);  
```  
  
#### <a name="parameters"></a>参数  
 `version`  
 [out]指向存储运行时的版本号 COR_VERSION 结构的指针。  
  
## <a name="remarks"></a>备注  
 `GetVersion`方法返回错误代码，如果已在进程中不加载任何运行时。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
