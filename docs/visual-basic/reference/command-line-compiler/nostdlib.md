---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 1c3c70b24de5163ca004b41a21017205a19d9730
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583373"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
使编译器不会自动引用标准库。  
  
## <a name="syntax"></a>语法  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>备注  
 `-nostdlib`选项删除自动对 System.dll 程序集引用，并可阻止编译器读取 Vbc.rsp 文件。 Vbc.rsp 文件，位于 Vbc.exe 文件所在的同一目录中，引用常用的.NET Framework 程序集并导入`System`和`Microsoft.VisualBasic`命名空间。  
  
> [!NOTE]
>  始终引用 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的程序集。  
  
> [!NOTE]
>  `-nostdlib`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。  
  
## <a name="example"></a>示例  
 下面的代码编译`T2.vb`而不引用标准库。 必须设置`_MYTYPE`到字符串"Empty"若要删除的条件编译常量`My`对象。  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>请参阅

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
