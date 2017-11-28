---
title: "ICorDebugCode::CreateBreakpoint 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 214d032129613230b8c55cdd286ea637227a626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodecreatebreakpoint-method"></a>ICorDebugCode::CreateBreakpoint 方法
在此代码段中指定的偏移量处创建断点。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a>参数  
 `offset`  
 [in]若要创建断点送的偏移量。  
  
 `ppBreakpoint`  
 [out]指向一个表示断点"ICorDebugFunctionBreakpoint"对象的地址的指针。  
  
## <a name="remarks"></a>备注  
 断点处于活动状态之前，它必须添加到此进程对象中。  
  
 如果此代码为 Microsoft 中间语言 (MSIL) 代码，并且没有在实时 (JIT)-将在 JIT 编译代码以及应用已编译的本机版本的代码，该断点。 （相同如果为 true 的代码都是 JIT 编译更高版本。）  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 
