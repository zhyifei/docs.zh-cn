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
ms.openlocfilehash: fef2652f591e713140c651a9cb0df1ea9e6236c8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005598"
---
# <a name="-filealign"></a>-filealign
指定输出文件各节的对齐位置。  
  
## <a name="syntax"></a>语法  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a>参数  
 `number`  
 必需。 一个值，该值指定输出文件中各节的对齐方式。 有效值为 512、1024、2048、4096 和 8192。 这些值以字节为单位。  
  
## <a name="remarks"></a>备注  
 您可以使用 `-filealign` 选项来指定输出文件中各节的对齐方式。 节是可移植可执行（PE）文件中包含代码或数据的连续内存块。 `-filealign` 选项允许你使用非标准对齐方式编译应用程序;大多数开发人员不需要使用此选项。  
  
 每个部分都在一个边界上对齐，该边界是 `-filealign` 值的倍数。 没有固定的默认值。 如果未指定 `-filealign`，编译器将在编译时选取默认值。  
  
 通过指定节大小，可以更改输出文件的大小。 修改节的大小可能对将在较小设备上运行的程序有用。  
  
> [!NOTE]
> `-filealign` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)
