---
title: "-target:library（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /dll
helpviewer_keywords:
- -target compiler options [C#], /target:library
- target compiler options [C#], /target:library
- /target compiler options [C#], /target:library
ms.assetid: c5670e88-2126-47c1-8d1c-217923837d17
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e66e2edd86dc4a1302b23dab07226a5d56cb79b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="targetlibrary-c-compiler-options"></a>/target:library（C# 编译器选项）
**/target:library** 选项导致编译器创建动态链接库 (DLL) 而不是可执行文件 (EXE)。  
  
## <a name="syntax"></a>语法  
  
```console  
/target:library  
```  
  
## <a name="remarks"></a>备注  
 将创建具有 .dll 扩展名的 DLL。  
  
 除非使用 [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) 选项指定，否则输出文件的名称采用第一个输入文件的名称。  
  
 在命令行中进行指定时，**/out** 或 **/target:module** 选项上所有文件都用于创建 .dll 文件。  
  
 生成 .dll 文件时，不需要 [ Main ](../../../csharp/programming-guide/main-and-command-args/index.md) 方法。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项  
  
1.  打开项目的“属性”页。  
  
2.  单击“应用程序”属性页。  
  
3.  修改“输出类型”属性。  
  
 有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>。  
  
## <a name="example"></a>示例  
 通过创建 `in.dll` 编译 `in.cs`：  
  
```console  
csc /target:library in.cs  
```  
  
## <a name="see-also"></a>另请参阅  
 [/target （C# 编译器选项）](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [C# 编译器选项](../../../csharp/language-reference/compiler-options/index.md)
