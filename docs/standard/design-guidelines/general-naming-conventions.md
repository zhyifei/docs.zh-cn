---
title: 通用命名约定
ms.date: 10/22/2008
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
ms.openlocfilehash: ef4a8f571a67477739bbc59d3103ba78dea47177
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635922"
---
# <a name="general-naming-conventions"></a>通用命名约定

本节介绍与单词选择相关的一般命名约定、有关使用缩写和首字母缩略词的指南，以及如何避免使用特定于语言的名称的建议。

## <a name="word-choice"></a>字选择
 ✔️选择易于读的标识符名称。

 例如，名为 的属性`HorizontalAlignment`比`AlignmentHorizontal`更具英语可读性。

 ✔️确实倾向于可读性而不是简洁性。

 属性名称`CanScrollHorizontally`优于`ScrollableX`（对 X 轴的模糊引用）。

 ❌请勿使用下划线、连字符或任何其他非字母数字字符。

 ❌请勿使用匈牙利符号。

 ❌使用与广泛使用的编程语言的关键字冲突的标识符。

 根据通用语言规范 （CLS） 的规则 4，所有兼容的语言都必须提供一种机制，允许访问使用该语言的关键字作为标识符的命名项。 例如，在这种情况下，C# 使用 + 符号作为转义机制。 但是，最好避免使用常见关键字，因为使用具有转义序列的方法比没有它的方法要困难得多。

## <a name="using-abbreviations-and-acronyms"></a>使用缩写和缩略词
 ❌请勿将缩写或缩略用作标识符名称的一部分。

 例如，使用`GetWindow`而不是`GetWin`。

 ❌不要使用任何未被广泛接受的首字母缩略词，即使它们是，也不得在必要时使用。

## <a name="avoiding-language-specific-names"></a>避免特定于语言的名称
 ✔️使用语义上有趣的名称，而不是特定于语言的关键字来输入类型名称。

 例如，`GetLength`比`GetInt`越好的名称。

 ✔️ DO 使用泛型 CLR 类型名称，而不是特定于语言的名称，在标识符在其类型之外没有语义含义的极少数情况下。

 例如，转换<xref:System.Int64>到 的方法应命名为`ToInt64`，而不是`ToLong`（因为<xref:System.Int64>是特定于 C# 的别名`long`的 CLR 名称）。 下表使用 CLR 类型名称（以及 C#、Visual Basic 和C++的相应类型名称）提供了几种基本数据类型。

|C#|Visual Basic|C++|CLR|
|---------|------------------|-----------|---------|
|sbyte |**SByte**|**char**|**SByte**|
|byte |**Byte**|**unsigned char**|**Byte**|
|**short**|**短**|**short**|**Int16**|
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|
|**Int**|**整数**|**Int**|**Int32**|
|**uint**|**UInt32**|**unsigned int**|**UInt32**|
|**长**|**Long**|**__int64**|**Int64**|
|**乌龙**|**UInt64**|unsigned __int64****|**UInt64**|
|**浮动**|**单精度**|**浮动**|**单精度**|
|**double**|**双精度**|**double**|**双精度**|
|**bool**|**布尔值**|**bool**|**布尔值**|
|**char**|**Char**|**wchar_t**|**Char**|
|**string**|**字符串**|**字符串**|**字符串**|
|**对象**|**Object**|**Object**|**Object**|

 ✔️ DO 使用公共名称，如`value``item`或 ，而不是重复类型名称，在标识符没有语义含义且参数类型并不重要的罕见情况下。

## <a name="naming-new-versions-of-existing-apis"></a>命名现有 API 的新版本
 ✔️在现有 API 的新版本创建时，请使用与旧 API 类似的名称。

 这有助于突出显示 API 之间的关系。

 ✔️喜欢添加后缀而不是前缀来指示现有 API 的新版本。

 这将有助于在浏览文档或使用 IntelliSense 时发现。 API 的旧版本将组织在新 API 附近，因为大多数浏览器和 IntelliSense 都按字母顺序显示标识符。

 ✔️考虑使用全新但有意义的标识符，而不是添加后缀或前缀。

 ✔️使用数字后缀来指示现有 API 的新版本，特别是如果 API 的现有名称是唯一有意义的名称（即，如果它是行业标准），并且添加任何有意义的后缀（或更改名称）不是适当的选项。

 ❌请勿使用标识符的"Ex"（或类似）后缀来区分它与同一 API 的早期版本。

 ✔️在引入使用 64 位整数（长整数）而不是 32 位整数的 API 版本时，请使用"64"后缀。 仅当存在现有的 32 位 API 时，才需要采用此方法;不要为只有 64 位版本的全新 API 执行此操作。

 *部分&copy;2005， 2009 微软公司.保留所有权利。*

 *经 Pearson 教育公司许可，从[框架设计指南：可重用的约定、习语和模式 .NET 库重新打印，第二版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)由 Krzysztof Cwalina 和 Brad Abrams 出版，由艾迪森-韦斯利专业公司作为微软 Windows 开发系列的一部分于 2008 年 10 月 22 日出版。*

## <a name="see-also"></a>请参阅

- [框架设计准则](../../../docs/standard/design-guidelines/index.md)
- [命名指南](../../../docs/standard/design-guidelines/naming-guidelines.md)
- [EditorConfig 适用的 .NET 命名约定](/visualstudio/ide/editorconfig-naming-conventions)
