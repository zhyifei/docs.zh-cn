---
title: "无法获取日志的流"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrApplicationLog_ExhaustedPossibleStreamNames
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dba511ecd2a5c050fc2c037ac437e38715609e95
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="unable-to-obtain-a-stream-for-the-log"></a>无法获取日志的流
无法获取日志的流。 基于的潜在文件名\<名称 > 已被占用。  
  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>类不能创建新的日志文件，因为所有潜在的日志文件名称基于\<名称 > 已被占用。  
  
 具有过多的日志文件可能表明应用程序存在结构问题。 有关详细信息，请参阅 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 类的文档。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  将 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> 属性设置为 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Daily> 或 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption.Weekly> ，以便在日志文件名中包含日期戳。  
  
2.  将现有日志存档后将其从计算机中删除，以允许 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 对象创建新日志。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>  
 [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)  
 [My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
