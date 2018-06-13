---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5f257fce67d8e348b69404411c12ded785cfd68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652124"
---
# <a name="-verbose"></a>-verbose
使编译器生成详细的状态和错误消息。  
  
## <a name="syntax"></a>语法  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>自变量  
 `+` &#124; `-`  
 可选。 指定`-verbose`等同于指定`-verbose+`，这将导致编译器发出详细消息。 此选项的默认值是`-verbose-`。  
  
## <a name="remarks"></a>备注  
 `-verbose`选项显示有关由编译器发出的错误总数的信息，报告正在加载哪些程序集由模块，并显示当前正在编译的文件。  
  
> [!NOTE]
>  `-verbose`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译`In.vb`和指示编译器显示详细状态信息。  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
