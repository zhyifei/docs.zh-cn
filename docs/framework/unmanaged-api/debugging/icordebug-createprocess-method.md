---
title: "ICorDebug::CreateProcess 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CreateProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16e45f3bad92914ce8c7fb0044534789a7a28b2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcreateprocess-method"></a>ICorDebug::CreateProcess 方法
将启动一个进程和调试器的控制之下其主线程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateProcess (  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `lpApplicationName`  
 [in]指向一个以 null 结尾的字符串，指定要启动的进程执行的模块的指针。 该模块是在调用进程的安全上下文中执行的。  
  
 `lpCommandLine`  
 [in]为一个以 null 结尾的字符串，指定要启动的进程执行的命令行的指针。 应用程序名称 (例如，"SomeApp.exe") 必须是第一个参数。  
  
 `lpProcessAttributes`  
 [in]指向 Win32`SECURITY_ATTRIBUTES`结构，它指定进程的安全描述符。 如果`lpProcessAttributes`是 null，则进程获取默认安全描述符。  
  
 `lpThreadAttributes`  
 [in]指向 Win32`SECURITY_ATTRIBUTES`结构，它指定进程的主线程的安全描述符。 如果`lpThreadAttributes`是 null，则该线程将获取默认安全描述符。  
  
 `bInheritHandles`  
 [in]设置为`true`以指示的启动过程中，将继承调用进程中的每个可继承句柄或`false`以指示句柄不会继承。 继承句柄具有相同的值和访问权限作为原始句柄。  
  
 `dwCreationFlags`  
 [in]按位组合[Win32 进程创建标志](http://go.microsoft.com/fwlink/?linkid=69981)控制的优先级类和启动进程的行为。  
  
 `lpEnvironment`  
 [in]指向新的进程的环境块的指针。  
  
 `lpCurrentDirectory`  
 [in]指向一个以 null 结尾的字符串，指定进程的当前目录的完整路径。 如果此参数为 null，则新进程将具有的相同当前的驱动器及目录作为调用进程。  
  
 `lpStartupInfo`  
 [in]指向 Win32`STARTUPINFOW`结构，它指定窗口工作站、 桌面、 标准句柄，和已启动的进程的主窗口的外观。  
  
 `lpProcessInformation`  
 [in]指向 Win32`PROCESS_INFORMATION`结构，它指定有关要启动的过程的标识信息。  
  
 `debuggingFlags`  
 [in]CorDebugCreateProcessFlags 枚举指定的调试选项的值。  
  
 `ppProcess`  
 [out]ICorDebugProcess 对象表示进程的地址指针。  
  
## <a name="remarks"></a>备注  
 此方法的参数是不同于 Win32`CreateProcess`方法。  
  
 若要启用非托管的混合模式调试，设置`dwCreationFlags`到 DEBUG_PROCESS &#124;DEBUG_ONLY_THIS_PROCESS。 如果你想要使用仅托管调试，则不要设置这些标志。  
  
 如果调试器和进程要调试 （附加的进程） 共享单个控制台中，并且如果使用互操作调试，则可能会附加进程保持控制台锁定并在调试事件处停止。 然后，调试器将阻止使用控制台的任何尝试。 若要避免此问题，在设置 CREATE_NEW_CONSOLE 标志`dwCreationFlags`参数。  
  
 不支持 Win9x 和非 x86 平台，例如-基于 IA-64 和 AMD64 基于平台进行互操作调试。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
