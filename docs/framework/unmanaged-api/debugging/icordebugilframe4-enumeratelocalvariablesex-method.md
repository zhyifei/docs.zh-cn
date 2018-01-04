---
title: "ICorDebugILFrame4::EnumerateLocalVariablesEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c82ecd9045deb772e31e549bf1050f85b148fd0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a>ICorDebugILFrame4::EnumerateLocalVariablesEx 方法
[仅在 .NET Framework 4.5.2 及更高版本中受支持]  
  
 获取帧中局部变量的枚举，并且（可选）包括在探查器 ReJIT 检测中添加的变量。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `flags`  
 [in][ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)枚举成员，用于指定在探查器 ReJIT 检测中添加的变量包含在帧。  
  
 `ppValueEnum`  
 [out]指向的地址是此帧中局部变量的枚举器的"ICorDebugValueEnum"对象的指针。  
  
## <a name="remarks"></a>备注  
 此方法类似于是[EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)方法，但它还可以访问在探查器 ReJIT 检测中添加的变量。 设置`flags`到`ILCODE_ORIGINAL_IL`等效于调用[icordebugilframe:: Enumeratelocalvariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)。 将 `flags` 设置为 `ILCODE_REJIT_IL` 使调试器能够访问在探查器 ReJIT 检测中添加的局部变量。 如果未检测到中间语言 (IL)，则枚举为空且该方法将返回 `S_OK`。  
  
 由于某些局部变量可能未处于活动状态，因此枚举器可能不包括正在运行的方法中的所有局部变量。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugILFrame4 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ReJIT: 操作方法指南](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
