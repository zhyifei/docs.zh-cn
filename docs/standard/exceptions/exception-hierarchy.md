---
title: "异常层次结构 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "例外情况之外类型"
  - "运行时异常"
  - "基异常"
  - "ApplicationException 类"
  - "公共语言运行时异常"
  - "COM 互操作性，异常"
  - "例外情况之外，层次结构"
ms.assetid: f7d68675-be06-40fb-a555-05f0c5a6f66b
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# 异常层次结构
有两种类型的异常：由执行程序生成的异常和由公共语言运行时生成的异常。 另外，还有由应用程序或运行时引发的异常的层次结构。  
  
 <xref:System.Exception?displayProperty=fullName>类是异常的基类。 多个异常类都继承直接从<xref:System.Exception>，其中包括<xref:System.ApplicationException>和<xref:System.SystemException>。 这两个类构成几乎所有运行时异常的基础。  
  
 直接从派生的大多数异常<xref:System.Exception>向其中添加任何功能和任何新成员。 例如， <xref:System.InvalidCastException>类层次结构是，如下所示︰  
  
 <xref:System.Object><xref:System.Exception> <xref:System.SystemException> <xref:System.InvalidCastException>  
  
 运行时会引发的相应派生的类<xref:System.SystemException>中发生错误时。 这些错误是失败的运行时检查（如数组超出界限错误）导致的，它们可在任何方法的执行过程中发生。 如果您正在设计的应用程序创建新的异常，应派生从这些异常<xref:System.Exception>类。 不建议您捕获<xref:System.SystemException>，也不是良好编程习惯引发<xref:System.SystemException>应用程序中。  
  
 最严重异常 — 那些由运行时或者在不可恢复的条件，则引发 — 包括<xref:System.ExecutionEngineException>， <xref:System.StackOverflowException>，和<xref:System.OutOfMemoryException>。  
  
 互操作异常派生自<xref:System.SystemException>和得以进一步扩展，通过<xref:System.Runtime.InteropServices.ExternalException>。 例如， <xref:System.Runtime.InteropServices.COMException>是 COM 互操作期间引发的异常，并且派生<xref:System.Runtime.InteropServices.ExternalException>。 <xref:System.ComponentModel.Win32Exception>和<xref:System.Runtime.InteropServices.SEHException>也派生自<xref:System.Runtime.InteropServices.ExternalException>。  
  
## <a name="hierarchy-of-runtime-exceptions"></a>运行时异常层次结构  
 运行时都有一组基本的异常派生自<xref:System.SystemException>执行单个指令时引发。 下表按层次结构列出了运行时提供的标准异常以及派生类的创建条件。  
  
|异常类型|基类型|描述|示例|  
|--------------------|---------------|-----------------|-------------|  
|[异常](../../../docs/standard/exceptions/exception-class-and-properties.md)|<xref:System.Object>|所有异常的基类。|无（使用此异常的派生类）。|  
|<xref:System.SystemException>|<xref:System.Exception>|所有运行时生成的错误的基类。|无（使用此异常的派生类）。|  
|<xref:System.IndexOutOfRangeException>|<xref:System.SystemException>|仅当错误地对数组进行索引时，才由运行时引发。|在数组的有效范围外对数组进行索引：<br /><br /> `var i = arr[arr.Length + 1];`<br /><br /> `Dim i = arr(arr.Length + 1)`|  
|<xref:System.NullReferenceException>|<xref:System.SystemException>|仅当引用 null 对象时，才由运行时引发。|`object o = null; string s = o.ToString();`<br /><br /> `Dim o As Object = Nothing Dim s As String = o.ToString()`|  
|<xref:System.AccessViolationException>|<xref:System.SystemException>|仅在访问无效内存时由运行时引发。|当与非托管代码或不安全的托管代码互操作时或者使用无效指针时发生。|  
|<xref:System.InvalidOperationException>|<xref:System.SystemException>|当处于无效状态时，由方法引发。|调用枚举器的`GetNext`方法后从基础集合中移除一个项。|  
|<xref:System.ArgumentException>|<xref:System.SystemException>|所有自变量异常的基类。|无（使用此异常的派生类）。|  
|<xref:System.ArgumentNullException>|<xref:System.ArgumentException>|由不允许参数为 null 的方法引发。|`String s = null; int i = "Calculate".IndexOf(s);`<br /><br /> `Dim s As String = Nothing Dim i As Integer = "Calculate".IndexOf(s)`|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.ArgumentException>|由验证自变量是否位于给定范围内的方法引发。|`String s = "string"; s = s.Substring(s.Length + 1);`<br /><br /> `Dim s As String = "string" s = s.Substring(s.Length + 1)`|  
|<xref:System.Runtime.InteropServices.ExternalException>|<xref:System.SystemException>|在运行时的外部环境中发生的异常或针对这类环境的异常的基类。|无（使用此异常的派生类）。|  
|<xref:System.Runtime.InteropServices.COMException>|<xref:System.Runtime.InteropServices.ExternalException>|封装 COM HRESULT 信息的异常。|在 COM 互操作中使用。|  
|<xref:System.Runtime.InteropServices.SEHException>|<xref:System.Runtime.InteropServices.ExternalException>|封装 Win32 结构化异常处理信息的异常。|在非托管代码互操作中使用。|  
  
## <a name="see-also"></a>另请参阅  
 [异常类和属性](../../../docs/standard/exceptions/exception-class-and-properties.md)   
 [异常处理基础知识](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [异常的最佳做法](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [异常](../../../docs/standard/exceptions/index.md)