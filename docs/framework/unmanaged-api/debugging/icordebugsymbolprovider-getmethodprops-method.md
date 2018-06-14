---
title: ICorDebugSymbolProvider::GetMethodProps 方法
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f52d20b9cb717d72d660bb19a0474c3e5b293ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422186"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a>ICorDebugSymbolProvider::GetMethodProps 方法
给定方法的相对虚拟地址 (RVA)，返回有关该方法属性的信息，例如该方法的元数据标记及其泛型参数信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
#### <a name="parameters"></a>参数  
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
 若要获取的方法的所需的大小`signature`数组，请将设置`cbSignature`为 0 的自变量和`signature`到**null**。 当该方法返回时，`pcbSignature` 将包含 `signature` 数组所需的字节数。  
  
> [!NOTE]
>  此方法仅适用于 .NET Native。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [GetTypeProps 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)  
 [ICorDebugSymbolProvider 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
