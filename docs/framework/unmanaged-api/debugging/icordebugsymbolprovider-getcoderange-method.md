---
title: ICorDebugSymbolProvider::GetCodeRange 方法
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: dbe042641cadae182efac30502a70631be359bbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791644"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a>ICorDebugSymbolProvider::GetCodeRange 方法
给定方法的相对虚拟地址 (RVA)，获取该方法的起始地址和大小。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a>参数  
 `codeRva`  
 [in] 方法中的相对虚拟地址 (RVA)。  
  
 `pCodeStartAddress`  
 [out] 指向该方法的起始地址的指针。  
  
 `pCodeSize`  
 指向方法代码大小（该方法的代码的字节数）的指针。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugSymbolProvider 接口](icordebugsymbolprovider-interface.md)
- [调试接口](debugging-interfaces.md)
