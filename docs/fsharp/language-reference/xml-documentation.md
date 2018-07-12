---
title: XML 文档 (F#)
description: '用于从注释生成文档，了解有关 F # 中的支持。'
ms.date: 05/16/2016
ms.openlocfilehash: 8bdea89ac810851af07d3aedbbb17d5d90a92ff8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566371"
---
# <a name="xml-documentation"></a>XML 文档

您可以生成利用三斜杠 （/ /） 的文档的代码在 F # 中的注释。 XML 注释可以在前面的代码文件 (.fs) 或签名 (.fsi) 文件中的声明。


## <a name="generating-documentation-from-comments"></a>生成文档注释
F # 中的支持从注释生成文档为相同处于其他.NET Framework 语言。 像其他.NET Framework 语言，那样[-doc 编译器选项](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04)使您能够生成 XML 文件，其中包含你可以通过将转换为文档使用 Sandcastle 等工具的信息。 通过使用适用于通常用其他.NET Framework 语言编写的程序集的设计的工具生成的文档生成基于 F # 构造的已编译形式的 Api 的一个视图。 除非专门工具支持 F #，通过这些工具生成的文档与 API 的 F # 视图不匹配。

有关如何从 XML 生成文档的详细信息，请参阅[XML 文档注释&#40;C&#35;编程指南&#41;](https://msdn.microsoft.com/library/b2s063f7)。


## <a name="recommended-tags"></a>建议的标记
有两种方式编写 XML 文档注释。 其中一个是直接在三斜杠注释中，只需编写文档，而无需使用 XML 标记。 如果这样做，则整个注释文本作为紧随的代码构造的摘要文档。 当你想要编写仅每个构造的简短摘要，请使用此方法。 另一种方法是使用 XML 标记来提供更结构化的文档。 第二种方法可分别为简短摘要、 其他备注、 每个参数和类型参数和异常引发，文档和的返回值的说明指定注释。 下表描述在 F # XML 代码注释中识别的 XML 标记。



|标记语法|描述|
|----------|-----------|
|**&lt;c&gt;***文本***&lt;/c&gt;**|指定*文本*是代码。 此标记可由文档生成器，用于以适合于代码的字体显示文本。|
|**&lt;摘要&gt;***文本*** &lt; /摘要&gt;**|指定*文本*是程序元素的简要说明。 该说明通常为一个或两个句子。|
|**&lt;备注&gt;***文本*** &lt; /remarks&gt;**|指定*文本*包含有关程序元素的补充信息。|
|**&lt;name ="***名称***"&gt;***说明***&lt;/param&gt;**|指定的名称和描述函数或方法参数。|
|**&lt;typeparam 名称 ="***名称***"&gt;***说明***&lt;/typeparam&gt;**|指定的名称和类型参数的说明。|
|**&lt;返回&gt;***文本*** &lt; /返回&gt;**|指定*文本*描述函数或方法的返回值。|
|**&lt;异常 cref ="***类型***"&gt;***说明***&lt;/exception&gt;**|指定在其下都会引发此错误的情况并可以生成的异常的类型。|
|**&lt;请参阅 cref ="***引用***"&gt;***文本*** &lt; /请参阅&gt;**|指定的内联链接到另一个程序元素。 *引用*是名称，因为它显示在 XML 文档文件。 *文本*是链接中显示的文本。|
|**&lt;另请参阅 cref ="***引用***"/&gt;**|指定到另一种类型的文档的另请参阅链接。 *引用*是名称，因为它显示在 XML 文档文件。 另请参阅通常出现在文档页的底部的链接。|
|**&lt;para&gt;***文本***&lt;/para&gt;**|指定文本的段落。 这用于分隔内的文本**备注**标记。|

## <a name="example"></a>示例

### <a name="description"></a>描述
以下是典型的 XML 文档注释中的签名文件。


### <a name="code"></a>代码
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]
    
## <a name="example"></a>示例

### <a name="description"></a>描述
下面的示例演示了备用方法，不带 XML 标记。 在此示例中，注释中的整个文本被视为摘要。 请注意，如果未显式指定 summary 标记，你不应指定其他标记，如**param**或**返回**标记。


### <a name="code"></a>代码
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]
    
## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[编译器选项](compiler-options.md)
