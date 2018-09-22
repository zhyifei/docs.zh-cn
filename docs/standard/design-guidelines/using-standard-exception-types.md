---
title: 使用标准异常类型
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ea4a61be3a76c30c564cbf98ba3318fc6c3e7d4
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46585476"
---
# <a name="using-standard-exception-types"></a>使用标准异常类型
本部分介绍的框架和及其用法的详细信息中提供的标准异常。 列表并不详尽。 请参阅其他 Framework 异常类型的.NET Framework 参考文档的使用情况。  
  
## <a name="exception-and-systemexception"></a>异常和 SystemException  
 **X DO NOT** 引发<xref:System.Exception?displayProperty=nameWithType>或<xref:System.SystemException?displayProperty=nameWithType>。  
  
 **X DO NOT** 捕获`System.Exception`或`System.SystemException`在 framework 代码中，除非您想要重新引发。  
  
 **X AVOID** 捕捉`System.Exception`或`System.SystemException`，除非在顶级异常处理程序。  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** 引发或从其派生<xref:System.ApplicationException>。  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** 引发<xref:System.InvalidOperationException>如果此对象处于不合适的状态。  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException、 ArgumentNullException 和 ArgumentOutOfRangeException  
 **✓ DO** 引发<xref:System.ArgumentException>或如果错误的自变量传递给成员及其子类型之一。 如果适用，倾向于使用的派生程度最高的异常类型。  
  
 **✓ DO** 设置`ParamName`属性时引发的子类之一`ArgumentException`。  
  
 此属性表示导致引发异常的参数的名称。 请注意，可以使用构造函数重载之一设置该属性。  
  
 **✓ DO** 使用`value`属性 setter 的隐式值参数的名称。  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException、 IndexOutOfRangeException 和 AccessViolationException  
 **X DO NOT** 允许公开可调用 Api 显式或隐式引发<xref:System.NullReferenceException>， <xref:System.AccessViolationException>，或<xref:System.IndexOutOfRangeException>。 这些例外情况是保留和引发的执行引擎和在大多数情况下指示 bug。  
  
 应进行检查以避免引发这些异常的参数。 引发这些异常会公开您可能随时间变化的方法的实现详细信息。  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** 显式引发<xref:System.StackOverflowException>。 应仅由 CLR 显式引发异常。  
  
 **X DO NOT** 捕获`StackOverflowException`。  
  
 它几乎是不可能编写保持一致出现任意堆栈溢出的情况下的托管的代码。 通过使用探测来移动到明确定义的位置而导致堆栈溢出，而不是通过将数据备份从任意堆栈溢出，CLR 的非托管的部分保持一致。  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** 显式引发<xref:System.OutOfMemoryException>。 将仅由 CLR 基础结构引发此异常。  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException、 SEHException 和 ExecutionEngineException  
 **X DO NOT** 显式引发<xref:System.Runtime.InteropServices.COMException>， <xref:System.ExecutionEngineException>，和<xref:System.Runtime.InteropServices.SEHException>。 这些异常将仅由 CLR 基础结构引发。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
