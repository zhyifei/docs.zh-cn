---
title: /utf8output (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23c7c308865a6b6afb07443a42090fff3d9e2efb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="utf8output-visual-basic"></a>/utf8output (Visual Basic)
显示使用 UTF-8 编码的编译器输出。  
  
## <a name="syntax"></a>语法  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a>参数  
 `+` &#124; `-`  
 可选。 此选项的默认值是`/utf8output-`，这意味着编译器输出不使用 utf-8 编码。 指定`/utf8output`等同于指定`/utf8output+`。  
  
## <a name="remarks"></a>备注  
 某些国际配置中，在编译器输出不能在控制台中正确显示。 在这种情况下，使用`/utf8output`和编译器输出重定向到一个文件。  
  
> [!NOTE]
>  `/utf8output`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`和指示编译器显示输出使用 utf-8 编码。  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
