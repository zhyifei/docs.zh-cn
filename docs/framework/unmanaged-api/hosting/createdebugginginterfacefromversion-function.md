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
ms.openlocfilehash: e23dfb86c2129a02a0ca95de8c89d8294e97ad81
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136839"
---
# <a name="createdebugginginterfacefromversion-function"></a>CreateDebuggingInterfaceFromVersion 函数
基于指定的版本信息创建[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)对象。  
  
 此函数在 .NET Framework 4 中已过时。 相反，若要获取公共语言运行时（CLR）2.0 的接口，请使用[ICLRRuntimeInfo：： GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)方法并指定类标识符 CLSID_CLRDebuggingLegacy 和 Interface 标识符 IID_ICorDebug。 若要获取 CLR 4 或更高版本的接口，请调用[CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md)函数并指定类标识符 CLSID_CLRDebugging 和 Interface 标识符 IID_ICLRDebugging。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a>参数  
 `iDebuggerVersion`  
 中调试器所需 `ICorDebug` 的版本。 有关有效值，请参阅[CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)枚举。  
  
 `szDebuggeeVersion`  
 中与要调试的应用程序或进程关联的公共语言运行时版本。 有关检索此值的信息，请参阅[GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)或[GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)方法。  
  
 `ppCordb`  
 弄接收指向 `ICorDebug` 对象的指针的位置。  
  
## <a name="return-value"></a>返回值  
 除以下值外，此方法还返回 Winerror.h 文件中定义的标准 COM 错误代码。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`szDebuggeeVersion` 或 `ppCordb` 为 null，或者版本字符串不正确。|  
  
## <a name="remarks"></a>备注  
 `szDebuggeeVersion` 参数将映射到 Mscordbi.dll 的相应版本。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscoree.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
