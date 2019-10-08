---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004970"
---
# <a name="-verbose"></a>-verbose
导致编译器生成详细的状态和错误消息。  
  
## <a name="syntax"></a>语法  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>参数  
 `+` &#124; `-`  
 可选。 指定 `-verbose` 与指定 `-verbose+` 相同，这将导致编译器发出详细消息。 此选项的默认值为 `-verbose-`。  
  
## <a name="remarks"></a>备注  
 @No__t-0 选项显示编译器发出的错误总数的相关信息，报告模块正在加载哪些程序集，并显示当前正在编译的文件。  
  
> [!NOTE]
> 在 Visual Studio 开发环境中，不能使用 `-verbose` 选项;仅当从命令行进行编译时，它才可用。  
  
## <a name="example"></a>示例  
 下面的代码编译 `In.vb` 并指示编译器显示详细状态信息。  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
