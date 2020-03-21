---
title: CreateDebuggingInterfaceFromVersion 函数
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176443"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion 函数
根据指定的版本信息创建[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)对象。  
  
 此功能在 .NET 框架 4 中已过时。 相反，要获取通用语言运行时 （CLR） 2.0 的接口，请使用[ICLRRuntimeinfo：getInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)方法，并指定类标识符CLSID_CLRDebuggingLegacy和接口标识符IID_ICorDebug。 要获取 CLR 4 或更高版本的接口，请调用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数，并指定类标识符CLSID_CLRDebugging和接口标识符IID_ICLRDebugging。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a>parameters  
 `iDebuggerVersion`  
 [在]`ICorDebug`调试器预期的版本。 有关有效值，请参阅[CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)枚举。  
  
 `szDebuggeeVersion`  
 [在]与要调试的应用程序或进程关联的通用语言运行时版本。 有关检索此值的信息，请参阅[获取从进程](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)获取版本或[获取请求运行时版本](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)的方法。  
  
 `ppCordb`  
 [出]接收指向`ICorDebug`对象的指针的位置。  
  
## <a name="return-value"></a>返回值  
 此方法返回 WinError.h 文件中定义的标准 COM 错误代码以及以下值。  
  
|返回代码|说明|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`szDebuggeeVersion`或`ppCordb`为 null，或者版本字符串不正确。|  
  
## <a name="remarks"></a>备注  
 参数`szDebuggeeVersion`映射到相应的 MSCorDbi.dll 版本。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** MSCorEE.h  
  
 **库：** MSCorEE.dll  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
