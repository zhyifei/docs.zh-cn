---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: fda75383435fdff718d1d50bc8583afc9858e7e2
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276482"
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
|`id`|必须的。 编译器使用指定的代码页`id`解释源代码文件的编码。|  
  
## <a name="remarks"></a>备注  
 若要编译源代码保存使用特定的编码，可以使用`-codepage`以指定应使用的代码页。 `-codepage`选项适用于编译中的所有源代码文件。 有关详细信息，请参阅[.NET Framework 中的字符编码](../../../standard/base-types/character-encoding.md)。  
  
 `-codepage`如果源代码文件已保存签名中使用当前 ANSI 代码页、 Unicode 或 utf-8，则不需要选项。 Visual Studio 将保存所有源代码文件的当前 ANSI 代码页与默认情况下，除非用户指定在另一种编码**编码**对话框。 Visual Studio 将使用**编码**对话框以打开用不同的代码页保存的源代码文件。  
  
> [!NOTE]
>  `-codepage`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
