---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 383b6adae94c27efdd236de31ddfa8d16a6d4648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-codepage-visual-basic"></a>-codepage (Visual Basic)
指定要用于编译中所有源代码文件的代码页。  
  
## <a name="syntax"></a>语法  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`id`|必须的。 编译器使用指定的代码页`id`解释的源文件的编码。|  
  
## <a name="remarks"></a>备注  
 若要编译使用特定的编码保存的源代码，可以使用`-codepage`可指定应使用的代码页。 `-codepage`选项适用于在你编译中所有源代码文件。 有关详细信息，请参阅[.NET Framework 中的字符编码](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9)。  
  
 `-codepage`如果源代码文件已保存使用具有签名的当前 ANSI 代码页、 Unicode 或 utf-8，则不需要选项。 Visual Studio 将保存所有源代码文件的当前 ANSI 代码页与默认情况下，除非用户指定，在另一种编码**编码**对话框。 Visual Studio 将使用**编码**对话框以打开用不同的代码页保存的源代码文件。  
  
> [!NOTE]
>  `-codepage`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
