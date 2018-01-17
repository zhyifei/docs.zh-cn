---
title: "大小写约定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b36f230c9a5f8653f3e252d26fe6464bb9cac4bb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="capitalization-conventions"></a>大小写约定
简单的方法来使用此章布局中的准则种情况下，当一致地应用生成标识符的类型、 成员和参数易于阅读。  
  
## <a name="capitalization-rules-for-identifiers"></a>标识符的大小写规则  
 若要区分标识符中的单词，将在标识符中的每个单词的第一个字母都大写。 不使用下划线来区分的单词，或其实，标识符中任意位置。 有两种适当的方法，以使其大写标识符，根据使用的标识符：  
  
-   PascalCasing  
  
-   camelcasing 大小写约定  
  
 用于除参数名称的所有标识符的 PascalCasing 约定转换成大写 （其中包括通过的长度的两个字母的首字母缩写词） 的每个单词的第一个字符，如下面的示例中所示：  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 一种特殊情况由两个字母首字母缩写词在其中两个字母都大写，如以下标识符中所示：  
  
 `IOStream`  
  
 Camelcasing 大小写约定使用的约定，仅为参数名称转换成大写除第一个字，每个单词的第一个字符，如下面的示例中所示。 如该示例还演示，开始混合使用大小写的标识符的两个字母缩写词都小写。  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 **✓ 执行**PascalCasing 用于所有的公共成员、 类型和命名空间名称，包含多个单词。  
  
 **✓ 执行**camelcasing 大小写约定用于参数名称。  
  
 下表描述了不同类型的标识符的大小写规则。  
  
|标识符|大小写|示例|  
|----------------|------------|-------------|  
|命名空间|Pascal|`namespace System.Security { ... }`|  
|类型|Pascal|`public class StreamReader { ... }`|  
|接口|Pascal|`public interface IEnumerable { ... }`|  
|方法|Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|属性|Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|事件|Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|字段|Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|枚举值|Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|参数|Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a>利用复合词和常用术语  
 大多数复合字词被视为单个字的大小写的目的。  
  
 **X 不**利用所谓关闭窗体复合词中的每个单词。  
  
 这些是编写为单个字词，如终结点的组合词。 为了大小写规则，将关闭格式的复合词视为单个单词。 使用当前字典来确定是否在关闭窗体中编写的组合词。  
  
|Pascal|Camel|不|  
|------------|-----------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## <a name="case-sensitivity"></a>区分大小写  
 可以在 CLR 运行的语言不要求支持区分大小写，尽管某些作用。 即使你的语言支持它，不这样做可能会访问你的 framework 的其他语言。 因此，任何 Api 时从外部访问，不能依赖于用例单独来区分这两个名称相同的上下文中。  
  
 **X 不**假定所有编程语言不区分大小写。 它们不是。 名称不能通过大小写来区分。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
