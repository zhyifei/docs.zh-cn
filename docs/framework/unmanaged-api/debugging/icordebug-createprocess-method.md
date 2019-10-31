---
title: ICorDebug::CreateProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
ms.openlocfilehash: 8812a98b0f28dd1336903dc34682f638a291f53b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110999"
---
# <a name="icordebugcreateprocess-method"></a>ICorDebug::CreateProcess 方法
在调试器的控制下启动进程及其主线程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `lpApplicationName`  
 中指向以 null 结尾的字符串的指针，该字符串指定由已启动的进程执行的模块。 该模块在调用进程的安全上下文中执行。  
  
 `lpCommandLine`  
 中指向以 null 结尾的字符串的指针，该字符串指定由已启动的进程执行的命令行。 应用程序名称（例如 "SomeApp"）必须是第一个参数。  
  
 `lpProcessAttributes`  
 中一个指针，指向 Win32 `SECURITY_ATTRIBUTES` 结构，该结构指定进程的安全说明符。 如果 `lpProcessAttributes` 为 null，则进程将获取默认安全描述符。  
  
 `lpThreadAttributes`  
 中指向 Win32 `SECURITY_ATTRIBUTES` 结构的指针，该结构指定进程的主线程的安全说明符。 如果 `lpThreadAttributes` 为 null，则线程将获取默认安全描述符。  
  
 `bInheritHandles`  
 中设置为 "`true`"，以指示调用进程中的每个可继承句柄由启动的进程继承，或 `false` 以指示不继承句柄。 继承句柄与原始句柄具有相同的值和访问权限。  
  
 `dwCreationFlags`  
 中[Win32 进程创建标志](https://go.microsoft.com/fwlink/?linkid=69981)的按位组合，用于控制优先级类和已启动进程的行为。  
  
 `lpEnvironment`  
 中指向新进程的环境块的指针。  
  
 `lpCurrentDirectory`  
 中指向以 null 结尾的字符串的指针，该字符串指定进程的当前目录的完整路径。 如果此参数为 null，则新进程将与调用进程具有相同的当前驱动器和目录。  
  
 `lpStartupInfo`  
 中指向 Win32 `STARTUPINFOW` 结构的指针，该结构指定窗口工作站、桌面、标准句柄和已启动进程的主窗口的外观。  
  
 `lpProcessInformation`  
 中指向 Win32 `PROCESS_INFORMATION` 结构的指针，该结构指定有关要启动的进程的标识信息。  
  
 `debuggingFlags`  
 中指定调试选项的 CorDebugCreateProcessFlags 枚举的值。  
  
 `ppProcess`  
 弄指向表示进程的 ICorDebugProcess 对象地址的指针。  
  
## <a name="remarks"></a>备注  
 此方法的参数与 Win32 `CreateProcess` 方法的参数相同。  
  
 若要启用非托管混合模式调试，请将 `dwCreationFlags` &#124;设置为 DEBUG_PROCESS DEBUG_ONLY_THIS_PROCESS。 如果只想使用托管调试，请不要设置这些标志。  
  
 如果调试器和要调试的进程（附加进程）共享单个控制台，并且如果使用互操作调试，则附加的进程可以保存控制台锁并在调试事件时停止。 然后，调试器会阻止任何使用控制台的尝试。 若要避免此问题，请在 `dwCreationFlags` 参数中设置 CREATE_NEW_CONSOLE 标志。  
  
 Win9x 和非 x86 平台（如基于 IA-64 和 AMD64 的平台）不支持互操作调试。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
