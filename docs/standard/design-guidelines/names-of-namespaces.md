---
title: 命名空间的名称
ms.date: 03/30/2017
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e0b6c5ac60474cfe984b3802e880eb58b017722
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576427"
---
# <a name="names-of-namespaces"></a>命名空间的名称
与其他命名准则一样，命名命名空间时的目的是为使用框架的程序员创建足够的明确性，能够立即知道命名空间的内容可能是什么。 以下模板指定了命名命名空间的一般规则：  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 示例如下：  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ 要**在名称空间名称前加上公司名称，以防止来自不同公司的名称空间具有相同的名称。
  
 **✓ 要**在命名空间名称的第二级使用稳定的，与版本无关的产品名称。
  
 **X 不要**使用组织层次结构作为命名空间层次结构中名称的基础，因为公司内的组名称往往是短期的。 围绕相关技术组组织命名空间的层次结构。
  
 **✓ 要**使用 PascalCasing，并使用句点分隔命名空间组件（例如，`Microsoft.Office.PowerPoint`）。 如果您的品牌使用非传统的大小写，则应遵循您的品牌定义的外壳，即使它不符合正常的命名空间大小写。
  
 **✓ 考虑**在适当的位置使用复数形式的命名空间名称。  
  
 例如，使用`System.Collections`而不是`System.Collection`。 然而，品牌名称和首字母缩写词是此规则的例外情况。 例如，使用`System.IO`而不是`System.IOs`。  
  
 **X 不要**对命名空间和该命名空间中的类型使用相同的名称。  
  
 例如，不要将`Debug`用作命名空间名称，然后在同一命名空间中提供一个名为`Debug`的类。 一些编译器要求这些类型是完全限定的。  
  
### <a name="namespaces-and-type-name-conflicts"></a>命名空间和类型名称冲突  
 **X 不要**引入泛型类型名称，如`Element`， `Node`， `Log`，和`Message`等。  
  
 一般情况下，这样做很可能会导致类型名称冲突。 您应该限定泛型类型名称（`FormElement`， `XmlNode`， `EventLog`， `SoapMessage`）。
  
 针对不同类别的命名空间，存在避免类型名称冲突的特定准则。
  
-   **应用程序模型命名空间**  
  
     属于单个应用程序模型的命名空间经常一起使用，但它们几乎从不与其他应用程序模型的命名空间一起使用。 例如，<xref:System.Windows.Forms?displayProperty=nameWithType>命名空间很少与<xref:System.Web.UI?displayProperty=nameWithType>命名空间一起使用。 以下是一个众所周知的应用程序模型命名空间组的列表：
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X 不要**在单个应用程序模型中为名称空间中的类型指定相同的名称。  
  
     例如，不要在<xref:System.Web.UI.Adapters?displayProperty=nameWithType>命名空间中添加名为`Page`的类型，因为<xref:System.Web.UI?displayProperty=nameWithType>命名空间已包含名为`Page`的类型。  
  
-   **基础架构命名空间**  
  
     该组包含在开发常见应用程序期间很少导入的命名空间。 例如，`.Design`命名空间主要用于开发编程工具。 避免与这些命名空间中的类型发生冲突并不重要。
  
-   **核心命名空间**  
  
     核心命名空间包括所有`System`命名空间，不包括应用程序模型命名空间和基础架构命名空间。 核心命名空间包含 `System`， `System.IO`， `System.Xml`，和`System.Net`等等。
  
     **X 不要**给出与核心命名空间中任何类型冲突的类型名称。  
  
     例如，永远不要将`Stream`作为类型名称。 它将与<xref:System.IO.Stream?displayProperty=nameWithType>冲突，这是一个非常常用的类型。  
  
-   **技术命名空间组**  
  
     此类别包括具有相同前两个命名空间节点（`<Company>.<Technology> *`）的所有命名空间，例如`Microsoft.Build.Utilities`和`Microsoft.Build.Tasks`。 重要的是属于单一技术的类型不会相互冲突  
  
     **X 不要**指定与单一技术中的其他类型冲突的类型名称。
  
     **X 不要**在技术名称空间和应用程序模型名称空间中的类型之间引入类型名称冲突（除非该技术不打算与应用程序模型一起使用）。
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*
  
 *由 Pearson Education, Inc 许可，转载自[Framework 设计准则： 可重用.NET 库的约定、 惯用法和模式 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者 Krzysztof Cwalina 和 Brad Abrams，由Addison Wesley Professional 于 2008 年 10 月 22 日发布，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
