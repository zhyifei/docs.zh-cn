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
本节介绍与单词选择相关的通用命名约定，使用缩写和首字母缩写词的指南，以及有关如何避免使用特定于语言的名称的建议。 
  
## <a name="word-choice"></a>选词  
 **✓ 务必**选择易读的标识符名称。  
  
 例如，名为`HorizontalAlignment`的属性比`AlignmentHorizontal`更具英语可读性。  
  
 **✓ 务必** 使可读性优先于简洁性。  
  
 属性名称`CanScrollHorizontally`优于`ScrollableX`（对 x 轴的模糊引用）。  
  
 **X 不要**使用下划线、 连字符或任何其他非字母数字字符。  
  
 **X 不要**使用匈牙利表示法。  
  
 **X 避免**使用与广泛应用的编程语言关键字冲突的标识符。  
  
 根据公共语言规范（CLS）的规则4，所有兼容语言必须提供允许访问使用该语言的关键字作为标识符的命名项的机制。 例如，C#在这种情况下使用@符号作为转义机制。 但是，避免使用常用关键字仍然是一个好主意，因为使用带有转义序列的方法比没有它要困难得多。 
  
## <a name="using-abbreviations-and-acronyms"></a>使用缩写和首字母缩写词  
 **X 不要**使用缩写作为标识符名称的一部分。  
  
 例如，使用`GetWindow`而非`GetWin`。  
  
 **X 不要**使用任何不被广泛接受的缩写词，即使它们是，也仅在必要时使用。  
  
## <a name="avoiding-language-specific-names"></a>避免特定于语言的名称  
 **✓ 务必**对类型名称使用语义上有意义的名称，而不是特定于语言的关键字。  
  
 例如，`GetLength`是更好的名称比`GetInt`。  
  
 **✓ 务必**在标识符除类型外没有语义含义的极少数情况下，使用通用CLR类型名称，而不是特定于语言的名称。  
  
 例如，转换为<xref:System.Int64>的方法应该被命名为`ToInt64`，而不`ToLong`(因为对C#特定别名`long`来说，<xref:System.Int64>是相应的 CLR 名称)。 下表列出了几种使用 CLR 类型名称 （以及C#、 Visual Basic 和 C++ 的相应类型名称） 的基本数据类型。  
  
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
  
 **✓ 务必**在标识符没有语义含义且参数类型不重要的极少数情况下，请使用常用名称，例如`value`或`item`，而不是重复类型名称。  
  
## <a name="naming-new-versions-of-existing-apis"></a>命名现有的 API 的新版本  
 **✓ 务必**在创建现有API的新版本时，使用与旧API类似的名称。
  
 这有助于突出 API 之间的关系。  
  
 **✓ 务必**倾向添加后缀而不是前缀来指示现有API的新版本。
  
 这有助于在浏览文档或使用IntelliSense时更容易发现。 旧版本的API将靠近新API进行组织，因为大多数浏览器和IntelliSense都按字母顺序显示标识符。 
  
 **✓ 考虑**使用全新但有意义的标识符，而不添加一个后缀或前缀。  
  
 **✓ 务必**使用数字后缀来指示现有API的新版本，特别是如果API的现有名称是唯一有意义的名称（即，如果它是行业标准）并且添加任何有意义的后缀（或更改其名称）不是一个合适的选择。
  
 **X 不要**使用"Ex"（或类似）后缀作为标识符，以区别于同一 API 的早期版本。  
  
 **✓ 务必**在引入以64位整数（长整数）而不是32位整数运行的API版本时，使用“64”后缀。 您只需要在现有的32位API存在时采用这种方法; 不要对只有64位版本的全新API应用该方法。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*
  
 *由 Pearson Education, Inc 许可，转载自[Framework 设计准则： 可重用.NET 库的约定、 惯用法和模式 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者 Krzysztof Cwalina 和 Brad Abrams，由Addison Wesley Professional 于 2008 年 10 月 22 日发布，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
