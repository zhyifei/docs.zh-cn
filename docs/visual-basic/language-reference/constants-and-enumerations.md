---
title: 常量和枚举
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- constants [Visual Basic]
- constants [Visual Basic], list of
ms.assetid: 309c0ad5-83e4-4f96-99ea-83cd95107417
ms.openlocfilehash: e47fd1c606f7d4cd0cf2fa6398beaa183ed95076
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838151"
---
# <a name="constants-and-enumerations-visual-basic"></a>常量和枚举 (Visual Basic)

Visual Basic 为开发人员提供了许多预定义的常量和枚举。 常量存储在应用程序的整个执行过程中保持不变的值。 枚举提供了使用相关常量集以及将常量值与名称相关联的一个便捷方法。  
  
## <a name="constants"></a>常量  
  
### <a name="conditional-compilation-constants"></a>条件编译常量  

 下表列出了可用于条件编译的预定义常量。  
  
|**常量**|**描述**|  
|---|---|  
|`CONFIG`|与**Configuration Manager**中 "**活动解决方案配置**" 框的当前设置相对应的字符串。|  
|`DEBUG`|可在 "**项目属性**" 对话框中设置的 `Boolean` 值。 默认情况下，项目的调试配置定义 `DEBUG`。 定义 `DEBUG` 时，<xref:System.Diagnostics.Debug> 类方法将生成输出到 "**输出**" 窗口。 如果未定义此方法，则不会编译 <xref:System.Diagnostics.Debug> 类方法，也不会生成任何调试输出。|  
|`TARGET`|一个字符串，表示项目的输出类型或命令行 **/target**选项的设置。 `TARGET` 的可能值为：<br /><br /> -Windows 应用程序的 "winexe"。<br />-适用于控制台应用程序的 "exe"。<br />-类库的 "库"。<br />-模块的 "module"。<br />-可在 Visual Studio 集成开发环境中设置 **/target**选项。 有关详细信息，请参阅[-target （Visual Basic）](../../visual-basic/reference/command-line-compiler/target.md)。|  
|`TRACE`|可在 "**项目属性**" 对话框中设置的 `Boolean` 值。 默认情况下，项目的所有配置都定义 `TRACE`。 定义 `TRACE` 时，<xref:System.Diagnostics.Trace> 类方法将生成输出到 "**输出**" 窗口。 如果未定义此方法，则不会编译 <xref:System.Diagnostics.Trace> 类方法，也不会生成任何 `Trace` 输出。|  
|`VBC_VER`|一个表示 Visual Basic 版本的数字，以*主*。*小*格式。|  
  
### <a name="print-and-display-constants"></a>打印和显示常量  

 调用打印和显示功能时，可以在代码中使用以下常量来替换实际值。  
  
|**常量**|**描述**|  
|---|---|  
|`vbCrLf`|回车符/换行符的组合。|  
|`vbCr`|回车符。|  
|`vbLf`|换行符。|  
|`vbNewLine`|换行符。|  
|`vbNullChar`|空字符。|  
|`vbNullString`|与零长度字符串（""）不同;用于调用外部过程。|  
|`vbObjectError`|错误号。 用户定义的错误号应大于此值。 例如：<br /><br /> `Err.Raise(Number) = vbObjectError + 1000`|  
|`vbTab`|制表符。|  
|`vbBack`|Backspace 字符。|  
|`vbFormFeed`|不在 Microsoft Windows 中使用。|  
|`vbVerticalTab`|在 Microsoft Windows 中不起作用。|  
  
## <a name="enumerations"></a>枚举  

 下表列出并描述了 Visual Basic 提供的枚举。  
  
|枚举|描述|  
|---|---|  
|<xref:Microsoft.VisualBasic.AppWinStyle>|指示在调用 <xref:Microsoft.VisualBasic.Interaction.Shell%2A> 函数时用于所调用程序的窗口样式。|  
|<xref:Microsoft.VisualBasic.AudioPlayMode>|指示如何在调用音频方法时播放声音。|  
|<xref:Microsoft.VisualBasic.ApplicationServices.BuiltInRole>|指示调用 <xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A> 方法时要检查的角色的类型。|  
|<xref:Microsoft.VisualBasic.CallType>|指示在调用 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A> 函数时要调用的过程的类型。|  
|<xref:Microsoft.VisualBasic.CompareMethod>|指示在调用比较函数时如何比较字符串。|  
|<xref:Microsoft.VisualBasic.DateFormat>|指示在调用 <xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A> 函数时如何显示日期。|  
|<xref:Microsoft.VisualBasic.DateInterval>|指示当调用与日期相关的函数时如何确定日期间隔并设置其格式。|  
|<xref:Microsoft.VisualBasic.FileIO.DeleteDirectoryOption>|指定要删除的目录包含文件或目录时应执行的操作。|  
|<xref:Microsoft.VisualBasic.DueDate>|指示在调用财务方法时付款何时到期。|  
|<xref:Microsoft.VisualBasic.FileIO.FieldType>|指示文本字段是分隔的还是固定宽度的。|  
|<xref:Microsoft.VisualBasic.FileAttribute>|指示在调用文件访问函数时要使用的文件特性。|  
|<xref:Microsoft.VisualBasic.FirstDayOfWeek>|指示在调用与日期相关的函数时要使用的一周中的第一天。|  
|<xref:Microsoft.VisualBasic.FirstWeekOfYear>|指示在调用与日期相关的函数时要使用的一年中的第一周。|  
|<xref:Microsoft.VisualBasic.MsgBoxResult>|指示在消息框上按下了哪个按钮，由 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 函数返回。|  
|<xref:Microsoft.VisualBasic.MsgBoxStyle>|指示调用 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 函数时显示的按钮。|  
|<xref:Microsoft.VisualBasic.OpenAccess>|指示在调用文件访问函数时如何打开文件。|  
|<xref:Microsoft.VisualBasic.OpenMode>|指示在调用文件访问函数时如何打开文件。|  
|<xref:Microsoft.VisualBasic.OpenShare>|指示在调用文件访问函数时如何打开文件。|  
|<xref:Microsoft.VisualBasic.FileIO.RecycleOption>|指定文件是应永久删除还是放入回收站。|  
|<xref:Microsoft.VisualBasic.FileIO.SearchOption>|指定是搜索所有还是只搜索顶级目录。|  
|<xref:Microsoft.VisualBasic.TriState>|指示 `Boolean` 值或在调用数字格式设置函数时是否应使用默认值。|  
|<xref:Microsoft.VisualBasic.FileIO.UICancelOption>|指定当用户在操作过程中单击 "**取消**" 时应执行的操作。|  
|<xref:Microsoft.VisualBasic.FileIO.UIOption>|指定在复制、删除或移动文件或目录时是否显示进度对话框。|  
|<xref:Microsoft.VisualBasic.VariantType>|指示 <xref:Microsoft.VisualBasic.Information.VarType%2A> 函数返回的变量对象的类型。|  
|<xref:Microsoft.VisualBasic.VbStrConv>|指示调用 <xref:Microsoft.VisualBasic.Strings.StrConv%2A> 函数时要执行的转换类型。|  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 语言参考](../../visual-basic/language-reference/index.md)
- [常量概述](../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [枚举概述](../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
