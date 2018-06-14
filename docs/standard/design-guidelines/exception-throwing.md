---
title: 异常引发
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, throwing
- explicitly throwing exceptions
- throwing exceptions, design guidelines
ms.assetid: 5388e02b-52f5-460e-a2b5-eeafe60eeebe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a493e6591d90ce05a652e48807f63fa90764a91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573716"
---
# <a name="exception-throwing"></a>异常引发
在本部分中所述的异常引发准则需要正确定义的执行失败的含义。 执行失败每当某一成员不能执行其设计目的 （什么成员名称所暗示的）。 例如，如果`OpenFile`方法无法返回到调用方的一个打开的文件句柄，它将被认为执行失败。  
  
 大多数开发人员已经熟悉使用由零或 null 引用异常如除法用法错误。 在框架中，异常用于所有错误条件，包括执行错误。  
  
 **X 不**返回错误代码。  
  
 例外情况是报告框架中的错误的主要方式。  
  
 **✓ 执行**引发异常来报告执行失败数。  
  
 **请考虑 ✓**通过调用来终止进程`System.Environment.FailFast`（.NET Framework 2.0 功能） 而不是引发异常，如果你的代码遇到进一步执行不安全的情况。  
  
 **X 不**正常流控制，如有可能使用异常。  
  
 系统故障和具有潜在的争用情况的操作，除外 framework 设计器应设计 Api，以便用户可以编写不引发异常的代码。 例如，你可以提供了如何在调用成员，因此用户可以编写不引发异常的代码之前检查前置条件。  
  
 用于检查另一个成员的前置条件的成员通常称为测试人员，而实际执行该操作，该成员称为 doer。  
  
 有某些情况下可能带来严重的性能开销，Tester-doer 模式。 在这种情况下，应考虑所谓的重分析模式 (请参阅[异常和性能](../../../docs/standard/design-guidelines/exceptions-and-performance.md)有关详细信息)。  
  
 **请考虑 ✓**引发异常的性能影响。 每秒 100 以上 throw 率很可能会显著影响大多数应用程序的性能。  
  
 **✓ 执行**由于的成员冲突而引发的公开可调用的成员的所有异常协定 （而不是系统故障），并将它们视为协定的一部分的文档。  
  
 协定的一部分的异常应不从一个版本更改为下一步 （即，不能更改异常类型，并且不应添加新异常）。  
  
 **X 不**具有或不会引发的公共成员根据某些选项。  
  
 **X 不**具有作为返回值返回异常的公共成员或`out`参数。  
  
 返回从公共 Api 而不是引发这些异常会使无效的许多优势的基于异常的错误报告。  
  
 **请考虑 ✓**使用异常生成器方法。  
  
 很容易从不同位置引发同一异常。 若要避免代码膨胀，使用使用帮助器方法创建异常并初始化其属性。  
  
 此外，不会引发异常的成员进行内联。 移动生成器 throw 语句可能会使成员进行内联。  
  
 **X 不**异常筛选器块中引发异常。  
  
 当异常筛选器引发异常时，默认情况下，异常由 CLR，并且筛选器返回 false。 此行为是不能与区分从筛选器执行，并显式返回 false，因此很难进行调试。  
  
 **请避免 x**显式引发 finally 块中的异常。 隐式引发的异常导致调用引发的方法均可接受。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
