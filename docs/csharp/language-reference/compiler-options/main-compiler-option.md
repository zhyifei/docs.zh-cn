---
title: "-main（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a6dca6e62dbf69783babf2e16dc4e7c36c6705c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="main-c-compiler-options"></a>/main（C# 编译器选项）
如果多个类包含 **Main** 方法，此选项将指定包含程序入口点的类。  
  
## <a name="syntax"></a>语法  
  
```console  
/main:class  
```  
  
## <a name="arguments"></a>自变量  
 `class`  
 此类型包含 **Main** 方法。  
  
## <a name="remarks"></a>备注  
 如果编译包含具有 [Main](../../../csharp/programming-guide/main-and-command-args/index.md) 方法的多个类型，则可以指定哪个类型包含你想用作程序入口点的 **Main** 方法。  
  
 此选项用于编译 .exe 文件。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项  
  
1.  打开项目的“属性”页。  
  
2.  单击“应用程序”属性页。  
  
3.  修改“启动对象”属性。  
  
     若要以编程方式设置此编译器选项，请参阅 <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>。  
  
## <a name="example"></a>示例  
 编译 `t2.cs` 和 `t3.cs`，指出 **Main** 方法可在 `Test2` 中找到：  
  
```console  
csc t2.cs t3.cs /main:Test2  
```  
  
## <a name="see-also"></a>另请参阅  
 [C# 编译器选项](../../../csharp/language-reference/compiler-options/index.md)  
 [管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)
