---
title: -reference
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
ms.openlocfilehash: 8b57affa05c77d8ed20bfead7de767a8dd994241
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348582"
---
# <a name="-reference-visual-basic"></a>-reference （Visual Basic）
使编译器使指定程序集中的类型信息可供当前正在编译的项目使用。  
  
## <a name="syntax"></a>语法  
  
```console  
-reference:fileList  
```

或

```console
-r:fileList  
```  
  
## <a name="arguments"></a>参数  
  
|术语|Definition|  
|---|---|  
|`fileList`|必需。 程序集文件名的逗号分隔列表。 如果文件名包含空格，则将名称括在引号内。|  
  
## <a name="remarks"></a>备注  
 导入的文件必须包含程序集元数据。 仅公共类型在程序集外可见。 [-Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)选项从模块导入元数据。  
  
 如果引用本身引用另一个程序集（程序集 B）的程序集（程序集 A），则需要在以下情况下引用程序集 B：  
  
- 程序集 A 中的类型继承自程序集 B 中的类型或实现程序集 B 中的接口。  
  
- 调用具有程序集 B 中的返回类型或参数类型的字段、属性、事件或方法。  
  
 使用[-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)可指定一个或多个程序集引用所在的目录。  
  
 为了使编译器能够识别程序集中的类型（而不是模块），必须强制解析该类型。 如何执行此操作的一个示例是定义类型的实例。 其他方法可用于解析编译器的程序集中的类型名称。 例如，如果从程序集中的某个类型继承，则该类型名称将在编译器中是已知的。  
  
 默认情况下，将使用用于引用常用 .NET Framework 程序集的 Vbc 响应文件。 如果你不希望编译器使用 Vbc，请使用 `-noconfig`。  
  
 `-reference` 的缩写形式是 `/r`。  
  
## <a name="example"></a>示例  
 以下命令将源文件 `Input.vb` 和引用程序集从 `Metad1.dll` 和 `Metad2.dll` 编译为生成 `Out.exe`。  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [-target （Visual Basic）](../../../visual-basic/reference/command-line-compiler/target.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
