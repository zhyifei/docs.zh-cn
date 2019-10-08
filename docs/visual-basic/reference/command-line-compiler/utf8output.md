---
title: -utf8output （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: adcb518cbe8397549c3ae3b3a8ca9f0ecf9dc38e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004666"
---
# <a name="-utf8output-visual-basic"></a>-utf8output （Visual Basic）
显示使用 UTF-8 编码的编译器输出。  
  
## <a name="syntax"></a>语法  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>参数  
 `+` &#124; `-`  
 可选。 此选项的默认值为 `-utf8output-`，这意味着编译器输出不使用 UTF-8 编码。 指定 `-utf8output` 与指定 `-utf8output+` 相同。  
  
## <a name="remarks"></a>备注  
 在某些国际化配置中，无法在控制台中正确显示编译器输出。 在这种情况下，请使用 `-utf8output` 并将编译器输出重定向到文件。  
  
> [!NOTE]
> 在 Visual Studio 开发环境中，不能使用 `-utf8output` 选项;仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译 `In.vb` 并指示编译器使用 UTF-8 编码显示输出。  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
