---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: db6b047f521d8ef44d2bd1b70b654a4233ebb1a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347916"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib （Visual Basic）
导致编译器不自动引用标准库。  
  
## <a name="syntax"></a>语法  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>备注  
 `-nostdlib` 选项删除对 System.web 程序集的自动引用，并阻止编译器读取 Vbc 文件。 Dcdiag.exe 文件与 dcdiag.exe 文件位于同一个目录中，引用常用 .NET Framework 程序集并导入 `System` 和 `Microsoft.VisualBasic` 命名空间。  
  
> [!NOTE]
> Mscorlib 和 Microsoft. .dll 程序集始终被引用。  
  
> [!NOTE]
> `-nostdlib` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译 `T2.vb`，而不引用标准库。 必须将 `_MYTYPE` 条件编译常量设置为字符串 "Empty" 以删除 `My` 对象。  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>另请参阅

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
