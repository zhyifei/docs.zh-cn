---
title: -filealign
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26ff29f00f00d3ea5dbbd0bbf01df4d7858771d0
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-filealign"></a>-filealign
指定输出文件各节的对齐位置。  
  
## <a name="syntax"></a>语法  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>自变量  
 `number`  
 必须的。 一个值，指定输出文件中的各节的对齐方式。 有效值为 512、1024、2048、4096 和 8192。 这些值以字节为单位。  
  
## <a name="remarks"></a>备注  
 你可以使用`-filealign`选项以指定输出文件中的各节的对齐方式。 节是包含代码或数据的可移植可执行文件 (PE) 文件中的连续内存块。 `-filealign`选项，可以编译为非标准的对齐方式与应用程序; 大多数开发人员不需要使用此选项。  
  
 每个部分在的倍数的边界上对齐`-filealign`值。 没有固定的默认值。 如果`-filealign`未指定，则编译器在编译时将选取默认值。  
  
 通过指定节的大小，你可以更改输出文件的大小。 修改节的大小可能对将在较小设备上运行的程序有用。  
  
> [!NOTE]
>  `-filealign`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
