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
ms.openlocfilehash: 81e4047c171e3a58f335821d64390432524b25df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574590"
---
# <a name="using-standard-exception-types"></a>使用标准异常类型
本部分介绍框架和它们的用法的详细信息提供的标准异常。 列表并不详尽。 请参阅其他 Framework 异常类型的.NET Framework 参考文档的使用情况。  
  
## <a name="exception-and-systemexception"></a>异常和 SystemException  
 **X 不**引发<xref:System.Exception?displayProperty=nameWithType>或<xref:System.SystemException?displayProperty=nameWithType>。  
  
 **X 不**捕获`System.Exception`或`System.SystemException`在 framework 代码中，除非您想要重新引发。  
  
 **请避免 x**捕捉`System.Exception`或`System.SystemException`，除非在顶级异常处理程序。  
  
## <a name="applicationexception"></a>ApplicationException  
 **X 不**引发或从其派生<xref:System.ApplicationException>。  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ 执行**引发<xref:System.InvalidOperationException>如果此对象处于不合适的状态。  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException、 ArgumentNullException 和 ArgumentOutOfRangeException  
 **✓ 执行**引发<xref:System.ArgumentException>或如果错误的自变量传递给成员及其子类型之一。 如果适用，更喜欢的派生程度最高的异常类型。  
  
 **✓ 执行**设置`ParamName`属性时引发的子类之一`ArgumentException`。  
  
 此属性表示导致引发异常的参数的名称。 请注意，可以使用构造函数重载之一设置该属性。  
  
 **✓ 执行**使用`value`属性 setter 的隐式值参数的名称。  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException、 IndexOutOfRangeException 和 AccessViolationException  
 **X 不**允许公开可调用 Api 显式或隐式引发<xref:System.NullReferenceException>， <xref:System.AccessViolationException>，或<xref:System.IndexOutOfRangeException>。 这些异常是保留并且由执行引擎引发并且在大多数情况下指示 bug。  
  
 应进行检查以避免引发这些异常的参数。 引发这些异常公开你可能随时间变化的方法的实现详细信息。  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X 不**显式引发<xref:System.StackOverflowException>。 应仅由 CLR 显式引发异常。  
  
 **X 不**捕获`StackOverflowException`。  
  
 它是几乎无法编写保持一致出现任意堆栈溢出的托管的代码。 按使用探测将移到定义完善的地方而导致堆栈溢出而不是从任意堆栈溢出退出，CLR 的非托管的部分保持一致。  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X 不**显式引发<xref:System.OutOfMemoryException>。 此异常是引发仅供 CLR 基础结构。  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException、 SEHException 和 ExecutionEngineException  
 **X 不**显式引发<xref:System.Runtime.InteropServices.COMException>， <xref:System.ExecutionEngineException>，和<xref:System.Runtime.InteropServices.SEHException>。 这些异常将会引发仅供 CLR 基础结构。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
