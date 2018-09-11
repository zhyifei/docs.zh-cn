---
title: XML 文档 (F#)
description: '用于从注释生成文档，了解有关 F # 中的支持。'
ms.date: 05/16/2016
ms.openlocfilehash: 1a4cb132e65b630821e5eb2b39276c1de99aff80
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2018
ms.locfileid: "44360789"
---
# <a name="xml-documentation"></a>XML 文档

您可以生成三斜杠 （/ /） 从文档代码在 F # 中的注释。 XML 注释之前可以放置在代码文件 (.fs) 或签名 (.fsi) 文件中的声明。

## <a name="generating-documentation-from-comments"></a>从注释生成文档

F # 中支持从注释生成文档是相同的其他.NET Framework 语言中。 如其他.NET Framework 语言中所示[-doc 编译器选项](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04)能够生成一个包含你可以通过将转换为文档使用 Sandcastle 等工具的信息的 XML 文件。 通过使用适用于与通常用其他.NET Framework 语言编写的程序集一起使用的设计的工具生成的文档生成基于 F # 构造的已编译形式的 Api 的一个视图。 除非专门工具支持 F #，这些工具生成的文档与 API 的 F # 视图不匹配。

有关如何从 XML 生成文档的详细信息，请参阅[XML 文档注释&#40;C&#35;编程指南&#41;](https://msdn.microsoft.com/library/b2s063f7)。

## <a name="recommended-tags"></a>建议的标记

有两种方法编写 XML 文档注释。 一个是直接在三斜杠注释中，只需编写文档，而无需使用 XML 标记。 如果执行此操作时，整个注释文本被视为紧跟在后面的代码构造的摘要文档。 如果想要编写仅为每个构造的简短摘要，请使用此方法。 另一种方法是使用 XML 标记来提供更结构化的文档。 第二种方法，可分别为简短摘要、 其他备注、 每个参数和类型参数和异常抛出，文档和返回值的说明指定注释。 下表描述在 F # XML 代码注释中识别的 XML 标记。

|标记语法|描述|
|----------|-----------|
|**&lt;c&gt;***文本***&lt;/c&gt;**|指定的*文本*是代码。 文档生成器可以使用此标记适用于代码的字体显示文本。|
|**&lt;摘要&gt;***文本*** &lt; /摘要&gt;**|指定的*文本*是程序元素的简要说明。 说明通常是一个或两个句子。|
|**&lt;备注&gt;***文本*** &lt; /m a k&gt;**|指定的*文本*包含有关程序元素的补充信息。|
|**&lt;参数名称 ="***名称***"&gt;***说明***&lt;/param&gt;**|指定的名称和描述函数或方法参数。|
|**&lt;typeparam 名称 ="***名称***"&gt;***说明***&lt;/typeparam&gt;**|指定的名称和类型参数的说明。|
|**&lt;返回&gt;***文本***&lt;/returns&gt;**|指定的*文本*描述函数或方法的返回值。|
|**&lt;异常 cref ="***类型***"&gt;***说明***&lt;/exception&gt;**|指定可以生成的异常以及在其下引发的环境类型。|
|**&lt;cref ="***引用***"&gt;***文本***&lt;看到&gt;**|指定的内联链接到另一个程序元素。 *引用*是出现在 XML 文档文件的名称。 *文本*是链接中所示的文本。|
|**&lt;seealso cref ="***引用***"/&gt;**|指定指向另一种类型的文档的另请参阅链接。 *引用*是出现在 XML 文档文件的名称。 另请参阅链接通常出现在文档页的底部。|
|**&lt;para&gt;***文本***&lt;/para&gt;**|指定文本的段落。 这用于分隔中的文本**备注**标记。|

## <a name="example"></a>示例

### <a name="description"></a>描述

以下是典型的 XML 文档注释中的签名文件。

### <a name="code"></a>代码

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>示例

### <a name="description"></a>描述

下面的示例演示的替代方法，而无需 XML 标记。 在此示例中，在注释中的整个文本被视为摘要。 请注意，如果未显式指定摘要的标记，则应不指定其他标记，如**param**或**返回**标记。

### <a name="code"></a>代码

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [编译器选项](compiler-options.md)
