---
title: "常量和枚举 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fd298cc504f9e4faf5205e53ebbf2ee355a21b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="constants-and-enumerations-visual-basic"></a>常量和枚举 (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]提供了大量预定义的常量和枚举的开发人员。 常数存储中保持不变的应用程序的执行中的值。 枚举提供了使用相关常量集以及将常量值与名称相关联的一个便捷方法。  
  
## <a name="constants"></a>常量  
  
### <a name="conditional-compilation-constants"></a>条件编译常量  
 下表列出可用于条件编译的预定义的常量。  
  
|**常量**|**描述**|  
|---|---|  
|`CONFIG`|对应的当前设置的字符串**活动解决方案配置**框中**Configuration Manager**。|  
|`DEBUG`|A`Boolean`可以在中设置的值**项目属性**对话框。 默认情况下，项目的调试配置定义`DEBUG`。 当`DEBUG`定义，<xref:System.Diagnostics.Debug>类方法将生成输出复制到**输出**窗口。 当未定义时，<xref:System.Diagnostics.Debug>类方法不进行编译，不生成任何调试输出。|  
|`TARGET`|表示对项目或命令行中的设置的输出类型的字符串**target**选项。 可能值`TARGET`是：<br /><br /> -"winexe"Windows 应用程序。<br />-"exe"控制台应用程序。<br />-类库的"库"。<br />-"模块"模块。<br />- **Target**可能在中设置选项[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]集成的开发环境。 有关详细信息，请参阅[/target (Visual Basic 中)](../../visual-basic/reference/command-line-compiler/target.md)。|  
|`TRACE`|A`Boolean`可以在中设置的值**项目属性**对话框。 默认情况下，项目的所有配置都定义`TRACE`。 当`TRACE`定义，<xref:System.Diagnostics.Trace>类方法将生成输出复制到**输出**窗口。 当未定义时，<xref:System.Diagnostics.Trace>类方法将不会被编译，但未`Trace`生成输出。|  
|`VBC_VER`|一个数字，表示[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]版本，请在*主要*。*次要*格式。 版本的版本号[!INCLUDE[vbprvblong](~/includes/vbprvblong-md.md)]为 8.0。|  
  
### <a name="print-and-display-constants"></a>打印和显示常量  
 当你调用输出，并显示函数时，你可以代替实际值在代码中使用以下常量。  
  
|**常量**|**描述**|  
|---|---|  
|`vbCrLf`|回车/换行字符组合。|  
|`vbCr`|回车符。|  
|`vbLf`|换行符字符。|  
|`vbNewLine`|换行字符。|  
|`vbNullChar`|Null 字符。|  
|`vbNullString`|不同于零长度字符串 ("");用来调用外部过程。|  
|`vbObjectError`|错误号。 用户定义的错误号应大于此值。 例如: <br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|制表符。|  
|`vbBack`|退格符。|  
|`vbFormFeed`|未在 Microsoft Windows 中使用。|  
|`vbVerticalTab`|Microsoft Windows 中不很有用。|  
  
## <a name="enumerations"></a>枚举  
 下表列出并描述由提供的枚举[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。  
  
|枚举|描述|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|指示要在调用时，可用于所调用的程序的窗口样式<xref:Microsoft.VisualBasic.Interaction.Shell%2A>函数。|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|指示如何调用音频方法时播放声音。|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|指示要时调用，检查角色类型<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>方法。|  
|<xref:Microsoft.VisualBasic.CallType>|指示的调用时要调用的过程的类型<xref:Microsoft.VisualBasic.Interaction.CallByName%2A>函数。|  
|<xref:Microsoft.VisualBasic.CompareMethod>|指示如何比较字符串时调用比较函数。|  
|<xref:Microsoft.VisualBasic.DateFormat>|指示如何显示日期时调用<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>函数。|  
|<xref:Microsoft.VisualBasic.DateInterval>|指示当调用与日期相关的函数时如何确定日期间隔并设置其格式。|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|指定要从中删除一个目录包含文件或目录时应采取的操作。|  
|<xref:Microsoft.VisualBasic.DueDate>|指示何时付款调用财务方法时。|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|指示是否分隔文本字段或固定宽度。|  
|<xref:Microsoft.VisualBasic.FileAttribute>|指示要在调用文件访问函数时使用的文件属性。|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|指示调用与日期相关的函数时使用的每周的第一天。|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|指示要在调用与日期相关的函数时使用的年份的第一周。|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|指示在消息框上按下了哪个按钮，由 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 函数返回。|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|指示调用 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 函数时显示的按钮。|  
|<xref:Microsoft.VisualBasic.OpenAccess>|指示如何在调用文件访问函数时打开文件。|  
|<xref:Microsoft.VisualBasic.OpenMode>|指示如何在调用文件访问函数时打开文件。|  
|<xref:Microsoft.VisualBasic.OpenShare>|指示如何在调用文件访问函数时打开文件。|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|指定是否应永久删除文件或在置于回收站。|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|指定是否搜索所有或仅顶级目录。|  
|<xref:Microsoft.VisualBasic.TriState>|指示`Boolean`值或调用数字格式的函数时是否应使用默认值。|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|指定应该是什么如果用户单击这样做**取消**执行操作的过程。|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|指定复制、 删除或移动文件或目录时显示进度对话框。|  
|<xref:Microsoft.VisualBasic.VariantType>|指示返回的变体对象的类型<xref:Microsoft.VisualBasic.Information.VarType%2A>函数。|  
|<xref:Microsoft.VisualBasic.VbStrConv>|指示调用 <xref:Microsoft.VisualBasic.Strings.StrConv%2A> 函数时要执行的转换类型。|  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 语言参考](../../visual-basic/language-reference/index.md)  
 [Visual Basic](../../visual-basic/index.md)  
 [常量概述](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [枚举概述](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
