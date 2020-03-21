---
title: ICorDebugSymbolProvider::GetCodeRange 方法
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: 81babade2ba499ce9326c664e83fa582abbd216f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178472"
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
  
## <a name="parameters"></a>parameters  
 `codeRva`  
 [in] 方法中的相对虚拟地址 (RVA)。  
  
 `pCodeStartAddress`  
 [out] 指向该方法的起始地址的指针。  
  
 `pCodeSize`  
 指向方法代码大小（该方法的代码的字节数）的指针。  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugSymbolProvider 接口](icordebugsymbolprovider-interface.md)
- [调试接口](debugging-interfaces.md)
