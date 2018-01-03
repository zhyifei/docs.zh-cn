---
title: /out (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53b77dec53be1d97c5f2526cb117933a2b8fe046
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="out-visual-basic"></a>/out (Visual Basic)
指定输出文件的名称。  
  
## <a name="syntax"></a>语法  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`filename`|必须的。 编译器创建输出文件的名称。 如果文件名包含空格，则将名称括在双引号 ("")。|  
  
## <a name="remarks"></a>备注  
 指定的完整名称和要创建的文件扩展名。 如果不这样做，.exe 文件将从源代码文件包含其名称`Sub Main`过程中和.dll 文件的第一个源代码文件采用其名称。  
  
 如果指定一个不带扩展名为.exe 或.dll 的文件名称，编译器会自动添加扩展，具体取决于指定的值`/target`编译器选项。  
  
|若要在 Visual Studio 集成的开发环境中设置 /out|  
|---|  
|1.在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“应用程序”  选项卡。<br />3.修改中的值**程序集名称**框。|  
  
## <a name="example"></a>示例  
 下面的代码编译`T2.vb`并创建输出文件`T2.exe`。  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
