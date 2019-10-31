---
title: ICorDebugSymbolProvider：： GetMethodProps 方法
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: 811106216e1e454ddf342af1578f74c80ba2acc9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138828"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a>ICorDebugSymbolProvider：： GetMethodProps 方法
给定方法的相对虚拟地址 (RVA)，返回有关该方法属性的信息，例如该方法的元数据标记及其泛型参数信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `codeRVA`  
 [in] 方法中有关要检索哪些信息的相对虚拟地址。  
  
 `pMethodToken`  
 [out] 指向方法元数据标记的指针。  
  
 `pcGenericParams`  
 [out] 指向与此方法关联的泛型参数个数的指针。  
  
 `cbSignature`  
 [in] `signature` 数组的大小。 请参见“备注”部分。  
  
 `pcbSignature`  
 [out] 指向返回的 `signature` 数组的大小的指针。  
  
 `signature`  
 [out] 保存所有泛型参数的 typespec 签名的缓冲区。  
  
## <a name="remarks"></a>备注  
 若要获取方法的 `signature` 数组的所需大小，请将 `cbSignature` 参数设置为0，并将 `signature` 设置为**null**。 当该方法返回时，`pcbSignature` 将包含 `signature` 数组所需的字节数。  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅

- [GetTypeProps 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)
- [ICorDebugSymbolProvider 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
