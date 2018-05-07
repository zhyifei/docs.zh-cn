---
title: ICorDebugRemote::CreateProcessEx 方法
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06bdc3605d981acad68a97901627f361da4061c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugremotecreateprocessex-method"></a>ICorDebugRemote::CreateProcessEx 方法
将启动在调试器下远程计算机上的进程。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
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
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRemoteTarget`  
 [in]指向[ICorDebugRemoteTarget 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)。 用于确定将在其启动该过程的远程计算机。  
  
 `lpApplicationName`  
 [in]指向一个以 null 结尾的字符串，指定要启动的进程执行的模块的指针。 该模块是在调用进程的安全上下文中执行的。  
  
 `lpCommandLine`  
 [in]为一个以 null 结尾的字符串，指定要启动的进程执行的命令行的指针。  
  
 `lpProcessAttributes`  
 [in]未使用远程调试。  
  
 `lpThreadAttributes`  
 [in]未使用远程调试。  
  
 `bInheritHandles`  
 [in]未使用远程调试。  
  
 `dwCreationFlags`  
 [in]未使用远程调试。  
  
 `lpEnvironment`  
 [in]指向新的进程的环境块的指针。  
  
 `lpCurrentDirectory`  
 [in]指向一个以 null 结尾的字符串，指定进程的当前目录的完整路径。 如果此参数为 null，则新进程将具有的相同当前的驱动器及目录作为调用进程。  
  
 `lpStartupInfo`  
 [in]未使用远程调试。  
  
 `lpProcessInformation`  
 [in]未使用远程调试。  
  
 `debuggingFlags`  
 [in]未使用远程调试。  
  
 `ppProcess`  
 [out]指向"ICorDebugProcess 接口"对象表示进程的地址的指针。  
  
## <a name="return-value"></a>返回值  
 S_OK  
 已成功启动远程计算机和返回"ICorDebugProcess 接口"上的进程进行调试。  
  
 E_FAIL（或其他 E_ 返回代码）  
 无法启动远程计算机上的进程并将"ICorDebugProcess 接口"以调试。  
  
## <a name="remarks"></a>备注  
 Silverlight 不支持混合模式调试。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 4.5、 4、 3.5 SP1  
  
## <a name="see-also"></a>请参阅  
 [ICorDebugRemote 接口](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug 接口](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
