---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 19a70e500f6b75fd003bdb798f242cddb3926935
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964352"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib (Visual Basic)
导致编译器不自动引用标准库。  
  
## <a name="syntax"></a>语法  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a>备注  
 `-nostdlib`选项将删除对 system.web 程序集的自动引用, 并阻止编译器读取 Vbc 文件。 Dcdiag.exe 文件与 dcdiag.exe 文件位于同一目录中, 它引用常用 .NET Framework 程序集, 并导入`System`和`Microsoft.VisualBasic`命名空间。  
  
> [!NOTE]
> Mscorlib 和 Microsoft. .dll 程序集始终被引用。  
  
> [!NOTE]
> 此`-nostdlib`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="example"></a>示例  
 下面的代码编译`T2.vb`时不引用标准库。 必须将`_MYTYPE`条件编译常量设置为字符串 "Empty" 才能删除该`My`对象。  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>请参阅

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
