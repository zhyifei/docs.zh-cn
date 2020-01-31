---
title: ICorDebugRemoteTarget 接口
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: bab6b7f683b5563cf362366dfb007f83caeee12d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791934"
---
# <a name="icordebugremotetarget-interface"></a>ICorDebugRemoteTarget 接口
介绍能够让开发人员在公共语言运行时 (CLR) 环境中调试基于 Silverlight 的应用程序的方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ICorDebugRemoteTarget::GetHostName 方法](icordebugremotetarget-gethostname-method.md)|返回远程计算机的主机名或 IP 地址。|  
  
## <a name="remarks"></a>备注  
 在 Windows 95、Windows 98、Windows ME 或非 x86 平台（例如 IA-64 和 AMD64）上，不支持混合模式（即托管和本机代码）调试。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl .idl  
  
 **库：** ： corguids.lib  
  
 **.NET Framework 版本：** 3.5 SP1  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugRemote 接口](icordebugremote-interface.md)
- [ICorDebug 接口](icordebug-interface.md)
- [调试接口](debugging-interfaces.md)
