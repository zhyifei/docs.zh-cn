---
title: "无法写入到输出文件 &#39;&lt;filename&gt;&#39;:&lt;错误&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords: BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d142a8c741a9f0e25b8ac3c0002d04f437bf0ca9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a>无法写入到输出文件 &#39;&lt;filename&gt;&#39;:&lt;错误&gt;
创建文件时出现问题。  
  
 无法打开输出文件以进行写入。 文件（或包含该文件的文件夹）可能由另一个进程打开以供独占使用，或者可能设置了只读特性。  
  
 文件以独占形式打开的常见情形是：  
  
-   应用程序已经在运行并使用它的文件。 若要解决此问题，请确保应用程序没有运行。  
  
-   其他应用程序已经打开了该文件。 若要解决此问题，请确保其他应用程序没有访问这些文件。 是哪个应用程序在访问你的文件并不总是很明显；在这种情况下，重新启动计算机可能是终止该应用程序的最简单的方式。  
  
 即使是项目输出文件中只有一个被标记为只读，也将会引发此异常。  
  
 **错误 ID:** BC31019  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  再次编译此程序以查看错误是否重复出现。  
  
2.  如果仍出现错误，请保存你的工作并重新启动 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]。  
  
3.  如果仍出现错误，请重新启动计算机。  
  
4.  如果错误重复出现，请重新安装 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。  
  
5.  如果在重新安装之后依然出现错误，请通知 Microsoft 产品支持服务。  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>在“文件资源管理器”中检查文件特性  
  
1.  打开你感兴趣的文件夹。  
  
2.  单击**视图**图标，然后选择**详细信息**。  
  
3.  右键单击列标题，然后选择**属性**从下拉列表。  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>更改文件或文件夹的特性  
  
1.  在**文件资源管理器**，右键单击文件或文件夹，然后选择**属性**。  
  
2.  在**属性**部分**常规**选项卡上，清除**只读**框。  
  
3.  Press **OK**.  
  
## <a name="see-also"></a>另请参阅  
 [与我们交流](/visualstudio/ide/talk-to-us)
