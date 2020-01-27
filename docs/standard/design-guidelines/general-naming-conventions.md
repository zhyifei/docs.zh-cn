---
title: 일반 명명 규칙
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
ms.openlocfilehash: f8576790a2be08c623807e236d156e0e7f93dd14
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741588"
---
# <a name="general-naming-conventions"></a>일반 명명 규칙
本部分介绍与单词选择相关的一般命名约定、缩略词和首字母缩写词的使用准则以及有关如何避免使用特定于语言的名称的建议。

## <a name="word-choice"></a>Word 选项
 ✔️选择易于阅读的标识符名称。

 例如，在英语中，属性名称 `HorizontalAlignment` 比 `AlignmentHorizontal` 更具可读性。

 ✔️提高可读性比简洁。

 属性名称 `CanScrollHorizontally` 优于 `ScrollableX`（对 x 轴的指代显得模糊）。

 ❌ 不使用下划线、连字符或任何其他非字母数字字符。

 ❌ 不使用匈牙利表示法。

 ❌ 避免使用与广泛使用的编程语言的关键字冲突的标识符。

 根据公共语言规范 (CLS) 规则 4，所有兼容语言均须提供一种机制，通过该机制能够访问将该语言的关键字用作标识符的命名项。 例如，C# 使用 @ 符号作为转义机制。 但是，仍然建议避免使用常用关键字，因为使用应用转义序列的方法比使用不应用转译序列的方法要困难得多。

## <a name="using-abbreviations-and-acronyms"></a>使用缩写和首字母缩写
 ❌ 不要使用缩写或缩写作为标识符名称的一部分。

 例如，使用 `GetWindow` 而不是 `GetWin`。

 ❌ 不要使用任何未被广泛接受的首字母缩写词，甚至在需要时也是如此。

## <a name="avoiding-language-specific-names"></a>避免特定于语言的名称
 ✔️确实使用有语义的名称，而不是类型名称的特定于语言的关键字。

 例如，`GetLength` 比 `GetInt` 更适合用作名称。

 在极少数情况下，如果标识符没有超出其类型的语义含义，则✔️使用泛型 CLR 类型名称，而不是特定于语言的名称。

 例如，转换为 <xref:System.Int64> 的方法应命名为 `ToInt64`，而不是 `ToLong`（因为 <xref:System.Int64> 是特定于 C# 的别名 `long` 的 CLR 名称）。 下表列出了几种使用 CLR 类型名称（以及 C#、Visual Basic 和 C++ 的对应类型名称）的基本数据类型。

|C#|Visual Basic|C++|CLR|
|---------|------------------|-----------|---------|
|**sbyte**|**SByte**|**char**|**SByte**|
|**byte**|**Byte**|**unsigned char**|**Byte**|
|**short**|**Short**|**short**|**Int16**|
|**ushort**|**UInt16**|**unsigned short**|**UInt16**|
|**int**|**Integer**|**int**|**Int32**|
|**uint**|**UInt32**|**unsigned int**|**UInt32**|
|**long**|**Long**|**__int64**|**Int64**|
|**ulong**|**UInt64**|**unsigned __int64**|**UInt64**|
|**float**|**Single**|**float**|**Single**|
|**double**|**double**|**double**|**double**|
|**bool**|**Boolean**|**bool**|**Boolean**|
|**char**|**Char**|**wchar_t**|**Char**|
|**string**|**String**|**String**|**String**|
|**object**|**개체**|**개체**|**개체**|

 ✔️使用公用名，如 `value` 或 `item`，而不是重复类型名称，在极少数情况下，标识符没有语义含义，并且参数的类型并不重要。

## <a name="naming-new-versions-of-existing-apis"></a>为现有 API 的新版本命名
 创建现有 API 的新版本时，✔️使用类似于旧 API 的名称。

 这有助于体现 API 之间的关系。

 ✔️确实更喜欢添加后缀（而非前缀）来指示现有 API 的新版本。

 这有助于在浏览文档或使用 IntelliSense 时更易发现所需内容。 旧版 API 的组织方式与新版 API 接近，因为大多数浏览器和 IntelliSense 都按字母顺序显示标识符。

 ✔️考虑使用全新但有意义的标识符，而不是添加后缀或前缀。

 ✔️使用数字后缀来指示现有 API 的新版本，尤其当 API 的现有名称是有意义的唯一名称（即，如果它是行业标准），并且添加任何有意义的后缀（或更改名称）不是合适的 opti基于.

 ❌ 不要使用标识符的 "Ex" （或类似的）后缀来区分它与早期版本的同一 API。

 当引入对64位整数（长整数）而不是32位整数运行的 Api 版本时，✔️确实使用 "64" 后缀。 只需在存在 32 位 API 时采用此方法；不要对只有 64 位版本的全新 API 应用此方法。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
