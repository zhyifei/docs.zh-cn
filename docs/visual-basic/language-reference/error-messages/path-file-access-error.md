---
title: 路径文件访问错误
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c86d46c884617be152a5954426e9ddd6ef61651
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="pathfile-access-error"></a>路径/文件访问错误
在文件访问或磁盘访问操作中，操作系统无法获得路径和文件名称之间的连接。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保文件规范的格式正确。 文件名称可以包含是完全限定 （绝对） 路径或相对路径。 完全限定的路径 （如果路径为另一个驱动器上） 开头的驱动器名称并列出文件的根的显式路径。 任何不是完全限定的路径是相对于当前的驱动器和目录。  
  
2.  请确保没有尝试保存将替换现有只读文件的文件。 如果出现这种情况，更改了目标文件的只读属性，或使用不同的文件名保存文件。  
  
3.  请确保你没有尝试打开只读文件中顺序`Output`或`Append`模式。 如果出现这种情况，打开中的文件`Input`模式或更改文件的只读属性。  
  
4.  请确保不尝试更改[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]数据库或文档中的项目。  
  
## <a name="see-also"></a>另请参阅  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)
