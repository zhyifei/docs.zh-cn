---
title: Tlbexp 帮助器函数（非托管 API 参考）
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f41a233e9b5338bdb0a324ff9af267a97821d4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455868"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Tlbexp 帮助器函数（非托管 API 参考）
[类型库导出程序工具](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)(Tlbexp.exe) 加载名为 TlbRef.dll 一个动态链接库。 此 DLL 包含两个 helper 函数和程序集到类型库的转换过程中使用导出程序工具的接口。  
  
## <a name="in-this-section"></a>本节内容  
 [GetTypeLibInfo 函数](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 提供类型库的本地化和操作系统的信息。  
  
 [LoadTypeLibWithResolver 函数](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 通过使用的实现中加载类型库[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)解析任何引用类型库。  
  
 [ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 提供[ResolveTypeLib 方法](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md)，它返回的类型库的完全限定的路径。
