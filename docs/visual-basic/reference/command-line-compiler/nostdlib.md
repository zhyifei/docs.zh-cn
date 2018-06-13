---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3764409f13a00f6d8a050bfbdd0f59e537a5ded3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652713"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
使编译器不会自动引用标准库。  
  
## <a name="syntax"></a>语法  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>备注  
 `-nostdlib`选项中移除自动对 System.dll 程序集引用，可防止编译器读取 Vbc.rsp 文件。 Vbc.rsp 文件，它位于 Vbc.exe 文件所在的同一目录中，引用常用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]程序集和导入`System`和`Microsoft.VisualBasic`命名空间。  
  
> [!NOTE]
>  始终引用 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的程序集。  
  
> [!NOTE]
>  `-nostdlib`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译`T2.vb`而不引用标准库。 必须设置`_MYTYPE`条件编译常量为字符串"Empty"，以删除`My`对象。  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
