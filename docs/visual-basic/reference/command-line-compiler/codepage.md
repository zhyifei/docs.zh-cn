---
title: -代码页 (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 3a5974a910303f847679f18c23e00cfaa00caa2c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962615"
---
# <a name="-codepage-visual-basic"></a>-代码页 (Visual Basic)
指定要用于编译中所有源代码文件的代码页。  
  
## <a name="syntax"></a>语法  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`id`|必需。 编译器使用指定的`id`代码页来解释源文件的编码。|  
  
## <a name="remarks"></a>备注  
 若要编译使用特定编码保存的源代码, 可以使用`-codepage`指定应使用的代码页。 选项`-codepage`适用于编译中的所有源代码文件。 有关详细信息, 请参阅[.NET Framework 中的字符编码](../../../standard/base-types/character-encoding.md)。  
  
 如果`-codepage`源代码文件是使用当前 ANSI 代码页、Unicode 或 utf-8 (带有签名) 保存的, 则不需要此选项。 默认情况下, Visual Studio 会将所有源代码文件连同当前 ANSI 代码页一起保存, 除非用户在**编码**对话框中指定了另一编码。 Visual Studio 使用 "**编码**" 对话框打开使用其他代码页保存的源代码文件。  
  
> [!NOTE]
> 此`-codepage`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
