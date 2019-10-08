---
title: -nostdlib （Visual Basic）
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 819505df2e7d5f93302f9ed601de856e36ed7124
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005413"
---
# <a name="-nostdlib-visual-basic"></a>-nostdlib （Visual Basic）
导致编译器不自动引用标准库。  
  
## <a name="syntax"></a>语法  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a>备注  
 @No__t-0 选项将删除对 system.exception 程序集的自动引用，并阻止编译器读取 Vbc 文件。 Dcdiag.exe 文件与 dcdiag.exe 文件位于同一个目录中，它引用常用 .NET Framework 程序集，并导入 @no__t 和 @no__t 的命名空间。  
  
> [!NOTE]
> Mscorlib 和 Microsoft. .dll 程序集始终被引用。  
  
> [!NOTE]
> 在 Visual Studio 开发环境中，不能使用 `-nostdlib` 选项;仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译 `T2.vb`，但不引用标准库。 必须将 @no__t 的条件编译常量设置为字符串 "Empty" 以删除 @no__t 1 对象。  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>请参阅

- [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [自定义 My 中可用的对象](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
