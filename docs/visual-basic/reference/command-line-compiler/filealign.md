---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 2893c1760a856a7d736e9c03ba33d9771722b5b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929474"
---
# <a name="-filealign"></a>-filealign
指定输出文件各节的对齐位置。  
  
## <a name="syntax"></a>语法  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>自变量  
 `number`  
 必需。 一个值, 该值指定输出文件中各节的对齐方式。 有效值为 512、1024、2048、4096 和 8192。 这些值以字节为单位。  
  
## <a name="remarks"></a>备注  
 您可以使用`-filealign`选项指定输出文件中各节的对齐方式。 节是可移植可执行 (PE) 文件中包含代码或数据的连续内存块。 `-filealign`选项允许你使用非标准对齐方式编译应用程序; 大多数开发人员不需要使用此选项。  
  
 每个部分在作为`-filealign`值的倍数的边界上对齐。 没有固定的默认值。 如果`-filealign`未指定, 编译器将在编译时选取默认值。  
  
 通过指定节大小, 可以更改输出文件的大小。 修改节的大小可能对将在较小设备上运行的程序有用。  
  
> [!NOTE]
> 此`-filealign`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
