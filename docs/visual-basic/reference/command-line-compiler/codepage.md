---
title: -代码页（Visual Basic）
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: e4cdc27ab021fe055f157b78946538f2b76870e1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002369"
---
# <a name="-codepage-visual-basic"></a>-代码页（Visual Basic）
指定要用于编译中所有源代码文件的代码页。  
  
## <a name="syntax"></a>语法  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>参数  
  
|术语|定义|  
|---|---|  
|`id`|必需。 编译器使用 `id` 指定的代码页来解释源文件的编码。|  
  
## <a name="remarks"></a>备注  
 若要编译使用特定编码保存的源代码，可以使用 `-codepage` 来指定应使用的代码页。 @No__t-0 选项适用于编译中的所有源代码文件。 有关详细信息，请参阅[.NET Framework 中的字符编码](../../../standard/base-types/character-encoding.md)。  
  
 如果源代码文件是使用当前 ANSI 代码页、Unicode 或 UTF-8 （带有签名）保存的，则不需要 `-codepage` 选项。 默认情况下，Visual Studio 会将所有源代码文件连同当前 ANSI 代码页一起保存，除非用户在**编码**对话框中指定了另一编码。 Visual Studio 使用 "**编码**" 对话框打开使用其他代码页保存的源代码文件。  
  
> [!NOTE]
> 在 Visual Studio 开发环境中，不能使用 `-codepage` 选项;仅当从命令行进行编译时，它才可用。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
