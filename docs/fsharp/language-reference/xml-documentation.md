---
title: XML 文档 (F#)
description: 了解用于从注释F#生成文档的中的支持。
ms.date: 05/16/2016
ms.openlocfilehash: b89ab4117f4dd71126f8e203f4a5271ab3c30021
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630818"
---
# <a name="xml-documentation"></a>XML 文档

可以在中生成三斜杠 (///) 代码注释中F#的文档。 XML 注释可以在代码文件 (fs) 或签名 (fsi.exe) 文件中的声明之前。

## <a name="generating-documentation-from-comments"></a>从注释生成文档

F#用于从注释生成文档的支持与其他 .NET Framework 语言相同。 与其他 .NET Framework 语言一样, [-doc 编译器选项](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04)使你能够生成一个 XML 文件, 该文件包含可通过使用[DocFX](https://dotnet.github.io/docfx/)或[Sandcastle](https://github.com/EWSoftware/SHFB)等工具转换为文档的信息。 使用与用其他 .NET Framework 语言编写的程序集一起使用而设计的工具所生成的文档通常会生成基于编译的F#构造形式的 api 视图。 除非工具特别支持F#, 否则这些工具生成的文档与 API 的F#视图不匹配。

有关如何从 xml 生成文档的详细信息, 请参阅[xml 文档注释&#40;C&#35;编程指南&#41;](https://msdn.microsoft.com/library/b2s063f7)。

## <a name="recommended-tags"></a>建议的标记

可以通过两种方法来编写 XML 文档注释。 一种方式是仅在三斜杠注释中直接编写文档, 而无需使用 XML 标记。 如果执行此操作, 整个注释文本将被视为紧随其后的代码构造的摘要文档。 如果只想编写每个构造的简短摘要, 请使用此方法。 另一种方法是使用 XML 标记来提供更多结构化文档。 第二种方法允许您为简短摘要指定单独的注释、附加备注、每个参数和类型参数的文档以及引发的异常以及对返回值的说明。 下表描述了在 xml 代码注释中F#识别的 xml 标记。

|标记语法|描述|
|----------|-----------|
|**\<c\>** _text_ **\</c\>**|指定*文本*为代码。 文档生成器可以使用此标记以适用于代码的字体显示文本。|
|**\<summary\>** _text_ **\</summary\>**|指定*文本*为程序元素的简短说明。 描述通常是一两个句子。|
|**备注文本\>/remarks \<**  **\<\>**|指定*文本*包含有关程序元素的补充信息。|
|**\<param name="** _name_ **"\>** _description_ **\</param\>**|指定函数或方法参数的名称和说明。|
|**\<typeparam name="** _name_ **"\>** _description_ **\</typeparam\>**|指定类型参数的名称和说明。|
|**\<returns\>** _text_ **\</returns\>**|指定*文本*描述函数或方法的返回值。|
|**\<exception cref="** _type_ **"\>** _description_ **\</exception\>**|指定可以生成的异常的类型以及引发此异常的情况。|
|**\>**  **请参阅\> cref=\<** "reference" text/see  **\<**|指定指向其他程序元素的内联链接。 *引用*是显示在 XML 文档文件中的名称。 *文本*是链接中显示的文本。|
|**\>** seealso cref = "reference"/  **\<**|指定另一种类型的文档的链接。 *引用*是显示在 XML 文档文件中的名称。 另请参阅链接通常显示在文档页的底部。|
|**\<para\>** _text_ **\</para\>**|指定文本段落。 用于分隔**备注**标记内的文本。|

## <a name="example"></a>示例

### <a name="description"></a>描述

下面是签名文件中的典型 XML 文档注释。

### <a name="code"></a>代码

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="example"></a>示例

### <a name="description"></a>描述

下面的示例显示了不带 XML 标记的替代方法。 在此示例中, 注释中的整个文本都被视为一个摘要。 请注意, 如果未显式指定摘要标记, 则不应指定其他标记, 如**param**或**返回**标记。

### <a name="code"></a>代码

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="see-also"></a>请参阅

- [F# 语言参考](index.md)
- [编译器选项](compiler-options.md)
