---
title: 成员重载
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c77f08cd573dc40083718b783ae01233ca00766
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573550"
---
# <a name="member-overloading"></a>成员重载
重载的成员表示上的相同类型的不同仅在数量或类型参数，但具有相同的名称创建两个或多个成员。 例如，如下所示，`WriteLine`方法重载：  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 方法、 构造函数和索引的属性可以具有参数，因为只有这些成员可以进行重载。  
  
 重载是一个使用最重要的技术来提高可用性和工作效率，并可重用库的可读性。 重载的参数数量，使可以提供更简单的构造函数和方法的版本。 参数类型上重载使可以使用相同的成员名称，用于执行相同操作对所选的不同类型的成员。  
  
 **✓ DO**尝试使用描述性的参数名称以指示较短的重载使用的默认值。  
  
 **X AVOID**随意更改重载中的参数名称。 如果某一重载中的参数表示相同的输入中另一个重载的参数，参数应具有相同的名称。  
  
 **X AVOID**在排序中的参数中不一致状态重载成员。 具有相同名称的参数应出现在所有重载中的同一位置。  
  
 **✓ DO**使只有最长的重载成为虚方法 （如果可扩展性是必需的）。 较短的重载应只需通过调用较长的重载。  
  
 **X DO NOT**使用`ref`或`out`修饰符来重载成员。  
  
 某些语言不能解决如下重载的调用。 此外，此类重载通常具有完全不同的语义，并且可能不应为重载，但两个单独的方法相反。  
  
 **X DO NOT**具有重载随着在相同的位置以及相似类型的参数，而使用不同的语义。  
  
 **✓ DO**允许`null`要为可选自变量传递。  
  
 **✓ DO**使用重载，而不是定义具有默认自变量的成员的成员。  
  
 默认自变量不符合 CLS。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
