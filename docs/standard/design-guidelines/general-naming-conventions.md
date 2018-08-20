---
title: 通用命名约定
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 207227b3e5c52b7c6e0f704543379874f3708c03
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338099"
---
# <a name="general-naming-conventions"></a>通用命名约定
本部分介绍与单词选择相关的一般命名约定、缩略词和首字母缩写词的使用准则以及有关如何避免使用特定于语言的名称的建议。  
  
## <a name="word-choice"></a>选词  
 **✓ DO** 选择易读的标识符名称。  
  
 例如，名为的属性`HorizontalAlignment`是英语-可读性比`AlignmentHorizontal`。  
  
 **✓ DO** 可读性比简洁性更。  
  
 属性名称`CanScrollHorizontally`优于`ScrollableX`（对 x 轴的晦涩引用）。  
  
 **X DO NOT** 使用下划线、 连字符或任何其他非字母数字字符。  
  
 **X DO NOT** 使用匈牙利语表示法。  
  
 **X AVOID** 使用广泛与关键字冲突的标识符使用编程语言。  
  
 根据规则 4 的公共语言规范 (CLS)，所有符合语言必须提供一种机制，允许访问将该语言关键字用作标识符的命名项。 C# 中，例如，使用 @ 符号作为转义机制在此情况下。 但是，它仍是一个好办法避免常见的关键字，因为它是要使用的方法与另一个没有它比转义序列困难得多。  
  
## <a name="using-abbreviations-and-acronyms"></a>使用缩写和首字母缩写词  
 **X DO NOT** 缩写用作标识符名称的一部分。  
  
 例如，使用`GetWindow`而非`GetWin`。  
  
 **X DO NOT** 使用并不被广泛接受，即使它们是，仅在必要时任何首字母缩写词。  
  
## <a name="avoiding-language-specific-names"></a>避免特定于语言的名称  
 **✓ DO** 使用类型名称在语义上是有意义的名称，而不是特定于语言的关键字。  
  
 例如，`GetLength`是更好的名称比`GetInt`。  
  
 **✓ DO** 在极少数情况下在标识符的语义含义仅限于其类型中使用泛型的 CLR 类型名称，而不是使用语言特定的名称。  
  
 例如，将转换为方法<xref:System.Int64>应该被命名为`ToInt64`，而不`ToLong`(因为<xref:System.Int64>是 C# 的 CLR 名称-特定别名`long`)。 下表列出了几种使用 CLR 类型名称 （以及相应的类型名称为 C#、 Visual Basic 和 c + +） 的基本数据类型。  
  
|C#|Visual Basic|C++|CLR|  
|---------|------------------|-----------|---------|  
|**sbyte**|**SByte**|**char**|**SByte**|  
|**byte**|**Byte**|**unsigned char**|**Byte**|  
|**short**|**Short**|**short**|**Int16**|  
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|  
|**int**|**Integer**|**int**|**Int32**|  
|**uint**|**UInt32**|**unsigned int**|**UInt32**|  
|**long**|**Long**|**__int64**|**Int64**|  
|**ulong**|**UInt64**|unsigned __int64|**UInt64**|  
|**float**|**单精度**|**float**|**单精度**|  
|**double**|**双精度**|**double**|**双精度**|  
|**bool**|**布尔值**|**bool**|**布尔值**|  
|**char**|**Char**|**wchar_t**|**Char**|  
|**string**|**字符串**|**字符串**|**字符串**|  
|**object**|**对象**|**对象**|**对象**|  
  
 **✓ DO** 使用公用名，如`value`或`item`，而不是重复的类型名称，在极少数的情况下当的标识符具有任何语义含义和参数的类型并不重要。  
  
## <a name="naming-new-versions-of-existing-apis"></a>为现有 API 的新版本命名  
 **✓ DO** 时创建的现有 API 的新版本使用类似于旧 API 的名称。  
  
 这有助于突出显示 Api 之间的关系。  
  
 **✓ DO** 喜欢添加一个后缀，而不是以指示现有 API 的新版本的前缀。  
  
 这将帮助发现浏览文档，或使用 IntelliSense。 将新的 Api，接近组织旧版本的 API，因为大多数浏览器和 IntelliSense 按字母顺序显示标识符。  
  
 **✓ CONSIDER** 使用全新，但有意义标识符，而不添加一个后缀或前缀。  
  
 **✓ DO** 使用数字后缀指示新版本的现有 API，特别是当 API 的现有名称是 （即，如果它是一种行业标准） 有意义的唯一名称，而且如果添加任何有意义后缀 （或更改名称） 不是应用程序ropriate 选项。  
  
 **X DO NOT** 使用"Ex"（或类似） 的标识符，以区别于相同的 API 的早期版本的后缀。  
  
 **✓ DO** 引入 api，而不是一个 32 位整数的 64 位整数 （长整型） 上运行的版本时，使用"64"后缀。 只需现有的 32 位 API 存在; 时采用此方法不执行操作的使用仅 64 位版本的全新 Api。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
