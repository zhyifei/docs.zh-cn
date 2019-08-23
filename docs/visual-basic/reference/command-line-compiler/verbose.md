---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 5b3899462af7c4aa8e0f77377a8d7485975f9867
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937263"
---
# <a name="-verbose"></a>-verbose
导致编译器生成详细的状态和错误消息。  
  
## <a name="syntax"></a>语法  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a>自变量  
 `+` &#124; `-`  
 可选。 指定`-verbose`与指定`-verbose+`的相同, 这将导致编译器发出详细消息。 此选项的默认值为`-verbose-`。  
  
## <a name="remarks"></a>备注  
 `-verbose`选项显示编译器发出的错误总数的相关信息, 报告模块正在加载哪些程序集, 并显示当前正在编译的文件。  
  
> [!NOTE]
> 此`-verbose`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="example"></a>示例  
 下面的代码将`In.vb`编译并指示编译器显示详细状态信息。  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
- [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
