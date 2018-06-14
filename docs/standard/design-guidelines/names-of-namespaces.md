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
作为与其他命名准则命名命名空间时的目标足够清楚起见为创建使用 framework 立即知道的内容的命名空间是什么，可能需要程序员。 以下模板指定命名命名空间的一般规则：  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 示例如下：  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 **✓ 执行**前缀与公司名称，以避免从具有相同名称的不同公司的命名空间的命名空间名称。  
  
 **✓ 执行**命名空间名称的第二个级别使用的稳定、 独立于版本的产品名称。  
  
 **X 不**作为基础命名空间层次结构中的名称使用组织的层次结构，因为公司内的组名称可能会改变。 将组织的相关技术的组周围的命名空间的层次结构。  
  
 **✓ 执行**与期使用 PascalCasing 和单独的命名空间组件 (例如， `Microsoft.Office.PowerPoint`)。 如果你的品牌采用非传统的大小写，则应遵循由您的品牌、 定义的大小写，即使背离常用的命名空间的大小写。  
  
 **请考虑 ✓**使用复数形式的命名空间名称，在适当的位置。  
  
 例如，使用`System.Collections`而不是`System.Collection`。 品牌名称和首字母缩写词但是是此规则的例外情况。 例如，使用`System.IO`而不是`System.IOs`。  
  
 **X 不**使用该命名空间中的命名空间和类型相同的名称。  
  
 例如，不要使用`Debug`与命名空间名称，然后还提供一个名为类`Debug`同一命名空间中。 多个编译器要求是完全限定的此类类型。  
  
### <a name="namespaces-and-type-name-conflicts"></a>命名空间和类型名称冲突  
 **X 不**如引入泛型类型名称`Element`， `Node`， `Log`，和`Message`。  
  
 没有这样做将导致类型名称共同点冲突方案非常高概率。 你应限定泛型类型名称 (`FormElement`， `XmlNode`， `EventLog`， `SoapMessage`)。  
  
 有用于避免显示为不同类别的命名空间的类型名称冲突的特定准则。  
  
-   **应用程序模型命名空间**  
  
     命名空间属于单个应用程序模型非常通常用于在一起，但几乎从未与其他应用程序模型的命名空间使用它们。 例如，<xref:System.Windows.Forms?displayProperty=nameWithType>连同极少数情况下使用命名空间<xref:System.Web.UI?displayProperty=nameWithType>命名空间。 下面是一个已知应用程序模型命名空间组的列表：  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     **X 不**为单个应用程序模型中的命名空间中的类型提供相同的名称。  
  
     例如，不要添加名为的类型`Page`到<xref:System.Web.UI.Adapters?displayProperty=nameWithType>命名空间，因为<xref:System.Web.UI?displayProperty=nameWithType>命名空间已包含名为的类型`Page`。  
  
-   **基础结构命名空间**  
  
     此组包含在常见的应用程序开发过程中很少导入的命名空间。 例如，`.Design`时开发编程工具主要使用命名空间。 避免使用这些命名空间中的类型的冲突并不重要。  
  
-   **核心命名空间**  
  
     核心命名空间包括所有`System`命名空间，不包括命名空间中的，应用程序模型和基础结构命名空间。 核心命名空间包含，及其他`System`， `System.IO`， `System.Xml`，和`System.Net`。  
  
     **X 不**给予类型会冲突的名称与核心命名空间中的任何类型。  
  
     例如，永远不会使用`Stream`为类型名称。 它将与冲突<xref:System.IO.Stream?displayProperty=nameWithType>、 一个非常常用的类型。  
  
-   **技术命名空间组**  
  
     此类别包括具有相同的前两个命名空间节点的所有命名空间`(<Company>.<Technology>*`)，如`Microsoft.Build.Utilities`和`Microsoft.Build.Tasks`。 很重要属于某个单一技术类型不会彼此发生冲突。  
  
     **X 不**分配会冲突的类型名称与某个单一技术中其他类型。  
  
     **X 不**（除非该技术不应与应用程序模型一起使用） 引入技术命名空间中的类型和应用程序模型命名空间之间的类型名称冲突。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
