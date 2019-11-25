---
title: 如何：从类型库生成互操作程序集
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: f4f099dfaf5ff02edd3958d7eab9354ce727a239
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281803"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>如何：从类型库生成互操作程序集
[类型库导入程序 (Tlbexp.exe)](../tools/tlbimp-exe-type-library-importer.md) 是一个命令行工具，可将 COM 类型库中包含的组件类和接口转换为元数据。 此工具会自动为类型信息创建互操作程序集和命名空间。 类的元数据可用之后，托管客户端可创建 COM 类型的实例并调用其方法，就像它是 .NET 实例一样。 Tlbimp.exe 同时将整个类型库转换为元数据，而且无法生成类型库中定义的类型子集的类型信息。  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>从类型库生成的互操作程序集  
  
1. 使用以下命令：  
  
     tlbimp **type-library-file**\<>  
  
     添加 /out: 开关会生成具有已更改名称的互操作程序集，如 LOANLib.dll。 更改互操作程序集名称有助于将它与原始 COM DLL 区分开来，并防止因为具有重复名称而可能发生的问题。  
  
## <a name="example"></a>示例  
 以下命令在 `Loanlib` 命名空间中生成 Loanlib.dll 程序集。  
  
```console  
tlbimp Loanlib.tlb  
```  
  
 以下命令生成具有已更改名称的互操作程序集 (LOANLib.dll)。  
  
```console  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>另请参阅

- [将类型库作为程序集导入](importing-a-type-library-as-an-assembly.md)
- [向 .NET Framework 公开 COM 组件](exposing-com-components.md)
