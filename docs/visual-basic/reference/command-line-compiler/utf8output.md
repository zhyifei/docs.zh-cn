---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 789df84bb4011d1ad128c50a9c689d1217be6694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937276"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
显示使用 UTF-8 编码的编译器输出。  
  
## <a name="syntax"></a>语法  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>自变量  
 `+` &#124; `-`  
 可选。 此选项的默认值为`-utf8output-`, 这意味着编译器输出不使用 utf-8 编码。 指定 `-utf8output` 与指定 `-utf8output+` 相同。  
  
## <a name="remarks"></a>备注  
 在某些国际化配置中, 无法在控制台中正确显示编译器输出。 在这种情况下`-utf8output` , 请使用并将编译器输出重定向到文件。  
  
> [!NOTE]
> 此`-utf8output`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="example"></a>示例  
 下面的代码将`In.vb`编译并指示编译器使用 utf-8 编码显示输出。  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
