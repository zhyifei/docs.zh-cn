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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967695"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a>Tlbexp 帮助器函数（非托管 API 参考）
[类型库导出程序工具](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) 加载一个名为“TlbRef.dll”的动态链接库。 此 DLL 包含两个 helper 函数和导出程序工具在程序集到类型库转换过程中使用的接口。  
  
## <a name="in-this-section"></a>本节内容  
 [GetTypeLibInfo 函数](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 提供类型库的本地化和操作系统信息。  
  
 [LoadTypeLibWithResolver 函数](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 通过使用 [ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)的实现来加载类型库，以解析任何引用的类型库。  
  
 [ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 提供 [ResolveTypeLib 方法](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md)，这会返回一个类型库的完全限定的路径。
