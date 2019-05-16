---
title: JSON 和 XML 之间的映射
ms.date: 03/30/2017
ms.assetid: 22ee1f52-c708-4024-bbf0-572e0dae64af
ms.openlocfilehash: ef5eaac8fc75149ac518ce322808a84bbab5506b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636440"
---
# <a name="mapping-between-json-and-xml"></a>JSON 和 XML 之间的映射
<xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory> 生成的读取器和编写器通过 JavaScript 对象表示法 (JSON) 内容提供 XML API。 JSON 使用 JavaScript 的对象文字子集对数据进行编码。 读取器和编写器生成的此工厂时也可使用 JSON 内容时使用的 Windows Communication Foundation (WCF) 应用程序由发送或接收<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>或<xref:System.ServiceModel.WebHttpBinding>。

使用 JSON 内容进行初始化时，JSON 读取器的行为方式与文本 XML 读取器通过 XML 实例执行的方式相同。 对文本 XML 读取器的调用序列生成某个 XML 实例时，JSON 编写器写出 JSON 内容。 本主题中描述此 XML 实例和 JSON 内容之间的映射以供在高级方案中使用。

在内部，JSON 表示为 XML infoset 时由 WCF 处理。 通常情况下无需关心此内部表示形式，如映射是一个仅逻辑：JSON 通常并不以物理方式是在内存中转换为 XML 或从 XML 转换为 JSON。 该映射意味着 XML API 用于访问 JSON 内容。

当 WCF 使用 JSON 时，通常的方案是，<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>自动插入由<xref:System.ServiceModel.Description.WebScriptEnablingBehavior>行为，或由<xref:System.ServiceModel.Description.WebHttpBehavior>时相应的行为。 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 了解 JSON 和 XML infoset 之间的映射，其行为就像它直接处理 JSON 那样。 （通过了解 XML 符合下面的映射，可以将 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 与任何 XML 读取器或编写器一起使用。）

在高级方案中，可能需要直接访问下面的映射。 希望以自定义方式序列化和反序列化 JSON 而不依赖于 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 时，或者直接为包含 JSON 的消息处理 <xref:System.ServiceModel.Channels.Message> 类型时，会出现这些方案。 JSON-XML 映射也用于消息日志记录。 在 WCF 中使用的消息日志记录功能，当 JSON 消息记录为 XML 根据下一节中所述的映射。

为阐明映射的概念，下面的示例采用一个 JSON 文档。

```json
{"product":"pencil","price":12}
```

若要使用前面提到的读取器之一读取此 JSON 文档，请使用与读取以下 XML 文档所用相同的 <xref:System.Xml.XmlDictionaryReader> 调用序列。

```xml
<root type="object">
    <product type="string">pencil</product>
    <price type="number">12</price>
</root>
```

此外，如果在示例中的 JSON 消息是由 WCF 接收并记录，则会看到在前面的日志中的 XML 片段。

## <a name="mapping-between-json-and-the-xml-infoset"></a>JSON 和 XML Infoset 之间的映射
正式情况下，映射是之间 JSON 中所述[RFC 4627](https://go.microsoft.com/fwlink/?LinkId=98808) （除非有某些限制宽松和某些添加其他限制） 和 XML 信息集 （以及不是文本 XML） 中所述[XML 信息设置](https://go.microsoft.com/fwlink/?LinkId=98809)。 请参阅本主题的定义面向*信息项*和 [方括号] 中的字段。

空 JSON 文档映射到一个空白的 XML 文档，而空 XML 文档映射到空 JSON 文档。 在 XML 到 JSON 的映射上不允许前导空白和，文档之后尾随的空白区域。

映射是在文档信息项 (DII) 或元素信息项 (EII) 和 JSON 之间定义的。 EII 或 DII 的 [文档元素] 属性称为根 JSON 元素。 请注意此映射不支持文档片段（具有多个根元素的 XML）。

示例:以下文档：

```xml
<?xml version="1.0"?>
<root type="number">42</root>`
```

和下面的元素：

```xml
<root type="number">42</root>
```

都具有到 JSON 的映射。 <`root`> 元素是根 JSON 元素，这两种情况。

此外，在使用 DII 的情况下，应该考虑以下内容：

- [子级] 列表中的某些项不得存在。 读取从 JSON 映射的 XML 时，不要依赖于此事实。

- [子级] 列表不包含注释信息项。

- [子级] 列表不包含 DTD 信息项。

- [子级] 列表不包含个人信息 (PI) 信息项 (`<?xml…>`声明不被视为 PI 信息项)

- [符号] 集为空。

- [未分析的实体] 集为空。

示例:以下文档具有未映射到 JSON 因为 [子级] 包含 PI 和注释。

```xml
<?xml version="1.0"?>
<!--comment--><?pi?>
<root type="number">42</root>
```

根 JSON 元素的 EII 具有以下特征：

- [本地名称] 具有值“root”。

- [命名空间名称] 没有值。

- [前缀] 没有值。

- [子级] 可能包含 EII（表示内部元素，将进一步描述）或 CII（字符信息项，将进一步描述）或这两者都不包含，但不能同时包含这两者。

- [属性] 可能包含以下可选的属性信息项 (AII)

- JSON 类型属性（“type”），将进一步描述。 此属性用于保留已映射 XML 中的 JSON 类型（字符串、数字、boolean、对象、数组或 null）。

- 数据协定名称属性 ("\_\_类型")，将进一步描述。 仅当 JSON 类型属性也存在且其 [正常化值] 为“object”时，此属性才能存在。 此属性由 `DataContractJsonSerializer` 用来保留数据协定类型信息 - 例如，在序列化派生类型和期望基类型的多态情况下。 如果未使用 `DataContractJsonSerializer`，则大多数情况下忽略此属性。

- [范围内命名空间] 包含"xml"的绑定到`http://www.w3.org/XML/1998/namespace`如 infoset 规范要求。

- [子级]、[属性] 和 [范围内命名空间] 不得具有除前面指定的之外的任何项，[命名空间属性] 不得具有成员，但是在读取从 JSON 映射的 XML 时不依赖于这些事实。

示例:以下文档具有未映射到 JSON 因为 [命名空间属性] 不为空。

```xml
<?xml version="1.0"?>
<root xmlns:a="myattributevalue">42</root>
```

JSON 类型属性的 AII 具有以下特征：

- [命名空间名称] 没有值。
- [前缀] 没有值。
- [本地名称] 为“type”。
- [正常化值] 是下面部分中描述的可能类型值之一。
- [已指定] 为 `true`。
- [属性类型] 没有值。
- [引用] 没有值。

数据协定名称属性的 AII 具有以下特征：

- [命名空间名称] 没有值。
- [前缀] 没有值。
- [本地名称] 是"\_\_类型"（两个下划线，然后"键入"）。
- [正常化值] 是任何有效的 Unicode 字符串 – 此字符串到 JSON 的映射将在下面的部分中进行描述。
- [已指定] 为 `true`。
- [属性类型] 没有值。
- [引用] 没有值。

根 JSON 元素中包含的内部元素或其他内部元素具有以下特征：

- [本地名称] 可能具有任何值，将进一步描述。
- [命名空间名称]、[前缀]、[子级]、[属性]、[命名空间属性] 和 [范围内命名空间] 遵循与根 JSON 元素相同的规则。

在根 JSON 元素和内部元素中，JSON 类型属性定义到 JSON 的映射和可能的 [子级] 及其解释。 该属性的 [正常化值] 区分大小写和必须为小写，不能包含空格。

|[正常化值] 的 JSON 类型属性的 AII|对应 EII 的已允许 [子级]|映射到 JSON|
|---------------------------------------------------------|---------------------------------------------------|---------------------|
|`string`（或缺少 JSON 类型 AII）<br /><br /> `string` 与缺少 JSON 类型 AII 相同，使 `string` 成为默认值。<br /><br /> 因此，`<root> string1</root>` 映射到 JSON `string`“string1”。|0 个或多个 Cii|JSON `string`（JSON RFC，第 2.5 节）。 每个 `char` 是对应于来自 CII 的 [字符代码] 的字符。 如果没有 CII，则它映射到空 JSON `string`。<br /><br /> 示例:下面的元素映射到 JSON 片段：<br /><br /> `<root type="string">42</root>`<br /><br /> JSON 片段是“42”。<br /><br /> 在 XML 到 JSON 的映射上，必须转义的字符映射到转义符，所有其他字符都映射到未转义的字符。 "/"字符是特殊字符 – 即使它不一定要经过转义 (写出为"\\/")。<br /><br /> 示例:下面的元素映射到 JSON 片段。<br /><br /> `<root type="string">the "da/ta"</root>`<br /><br /> JSON 片段是" \\"da\\/ta\\""。<br /><br /> 在 JSON 到 XML 的映射上，任何转义符和未转义的字符都正确映射到对应的 [字符代码]。<br /><br /> 示例:JSON 片段"\u0041BC"映射到下面的 XML 元素。<br /><br /> `<root type="string">ABC</root>`<br /><br /> 字符串可以由未映射到 XML 的空白区域 (如 JSON rfc 第 2 节中的 ws) 括起来。<br /><br /> 示例:JSON 片段"ABC"，（有第一个双引号之前的空格），将映射到下面的 XML 元素。<br /><br /> `<root type="string">ABC</root>`<br /><br /> 在 XML 中的任何空白区域将映射到 JSON 中的空白区域。<br /><br /> 示例:下面的 XML 元素映射到 JSON 片段。<br /><br /> `<root type="string">  A BC      </root>`<br /><br /> JSON 片段是“ A BC ”。|
|`number`|1 个或多个 CII|JSON `number` (JSON RFC，第 2.4 节)，可能是括在空白区域。 数字/空白组合中的每个字符是对应于 CII 的 [字符代码] 的字符。<br /><br /> 示例:下面的元素映射到 JSON 片段。<br /><br /> `<root type="number">    42</root>`<br /><br /> JSON 片段是    42<br /><br /> （保留空白）。|
|`boolean`|4 或 5 个 Cii (对应于`true`或`false`)，可能由其他空白 Cii。|对应于字符串“true”的 CII 序列被映射到文字 `true`，而对应于字符串“false”的 CII 序列被映射到文字 `false`。 周围的空白区域将被保留。<br /><br /> 示例:下面的元素映射到 JSON 片段。<br /><br /> `<root type="boolean"> false</root>`<br /><br /> JSON 片段是 `false`。|
|`null`|都不允许。|文字 `null`。 在 JSON 到 XML 的映射，`null`可能由未映射到 XML 的空白区域 (第 2 节中的 ws) 括起来。<br /><br /> 示例:下面的元素映射到 JSON 片段。<br /><br /> `<root type="null"/>`<br /><br /> 或<br /><br /> `<root type="null"></root>`<br /><br /> :<br /><br /> 在这两种情况下 JSON 片段都是 `Null`。|
|`object`|0 个或多个 EII。|如 JSON RFC 第 2.2 节中的 `begin-object`（左花括号），后跟每个 EII 的成员记录，将进一步说明。 如果存在多个 EII，则在成员记录之间存在值分隔符（逗号）。 所有这一切后跟 end-object（右花括号）。<br /><br /> 示例:下面的元素映射到 JSON 片段。<br /><br /> `<root type="object">`<br /><br /> `<type1 type="string">aaa\</type1>`<br /><br /> `<type2 type="string">bbb\</type2>`<br /><br /> `</root >`<br /><br /> JSON 片段是 `{"type1":"aaa","type2":"bbb"}`。<br /><br /> 如果在 XML 到 JSON 的映射上存在数据协定类型属性，则在开头插入其他成员记录。 其名称是数据协定类型属性的 [本地名称] ("\_\_类型")，且其值的 [正常化值] 的属性。 相反，在 JSON 到 XML 的映射，如果第一个成员记录的名称是数据协定类型属性的 [本地名称] (即，"\_\_类型")，相应的数据协定类型属性是存在在映射 XML 中，但不存在对应的 EII。 请注意，此成员记录必须首先出现在 JSON 对象中才能应用此特殊映射。 这与通常的 JSON 处理（成员记录的顺序是不重要的）相背离。<br /><br /> 示例:<br /><br /> 下面的 JSON 片段映射到 XML。<br /><br /> `{"__type":"Person","name":"John"}`<br /><br /> XML 是下面的代码。<br /><br /> `<root type="object" __type="Person">   <name type="string">John</name> </root>`<br /><br /> 请注意， \_\_类型 AII 存在，但没有任何\_\_键入 EII。<br /><br /> 但是，如果保留 JSON 中的顺序，如下面的示例所示。<br /><br /> {"name":"John","\_\_type":"Person"}<br /><br /> 则显示对应的 XML。<br /><br /> `<root type="object">   <name type="string">John</name>   <__type type="string">Person</__type> </root>`<br /><br /> 也就是说，\_类型 （_t） 不再具有特殊含义，映射到 EII 像往常一样，不是 AII。<br /><br /> 映射到 JSON 值时，AII 的 [正常化值] 的转义/未转义规则与在此表的“string”行中指定的 JSON 字符串的相同。<br /><br /> 示例:<br /><br /> `<root type="object" __type="\abc" />`<br /><br /> 前面的示例可以映射到下面的 JSON。<br /><br /> `{"__type":"\\abc"}`<br /><br /> 不能在 XML 到 JSON 的映射，第一个 EII 的 [本地名称]"\_\_类型"。<br /><br /> 空白 (`ws`) 则永远不生成的 XML 到 JSON 的映射的对象和在 JSON 到 XML 的映射上忽略。<br /><br /> 示例:下面的 JSON 片段映射到一个 XML 元素。<br /><br /> `{ "ccc" : "aaa", "ddd" :"bbb"}`<br /><br /> 在下面的代码中显示了 XML 元素。<br /><br /> `<root type="object">    <ccc type="string">aaa</ccc>    <ddd type="string">bbb</bar> </root >`|
|array|0 个或多个 EII|如 JSON RFC 第 2.3 节中的 begin-array（左花括号），后跟每个 EII 的数组记录，将进一步描述。 如果存在多个 EII，则在数组记录之间存在值分隔符（逗号）。 所有这一切后跟 end-array。<br /><br /> 示例:下面的 XML 元素映射到 JSON 片段。<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`<br /><br /> JSON 片段是 ["aaa","bbb"]<br /><br /> 空白 (`ws`) 则永远不生成的 XML 到 JSON 的映射的数组，并在 JSON 到 XML 的映射上忽略。<br /><br /> 示例:JSON 片段。<br /><br />`["aaa", "bbb"]`<br /><br /> 它映射到的 XML 元素。<br /><br /> `<root type="array"/>    <item type="string">aaa</item>    <item type="string">bbb</item> </root >`|

成员记录的工作原理如下：

- 内部元素的 [本地名称] 映射到 `string` 的 `member` 部分，如 JSON RFC 第 2.2 节所定义。

示例:下面的元素映射到 JSON 片段。

`<root type="object"/>`

`<myLocalName type="string">aaa</myLocalName>`

`</root >`

将显示下面的 JSON 片段。

`{"myLocalName":"aaa"}`

- 在 XML 到 JSON 的映射上，对必须在 JSON 中转义的字符进行转义，而不对其他字符进行转义。 但是，对“/”字符进行转义，尽管它不是必须转义的字符（在 JSON 到 XML 的映射上不必对它进行转义）。 这是支持 JSON 中 `DateTime` 数据的 ASP.NET AJAX 格式所必需的。

- 在 JSON 到 XML 的映射上，提取所有字符（如有必要，则包括未转义的字符）以构成一个生成 [本地名称] 的 `string`。

- 按照 `JSON Type Attribute`，内部元素 [子级] 映射到第 2.2 节中的值，就像 `Root JSON Element` 那样。 允许 EII 的多级嵌套（包括数组中的嵌套）。

示例:下面的元素映射到 JSON 片段。

```xml
<root type="object">
    <myLocalName1 type="string">myValue1</myLocalName1>
    <myLocalName2 type="number">2</myLocalName2>
    <myLocalName3 type="object">
        <myNestedName1 type="boolean">true</myNestedName1>
        <myNestedName2 type="null"/>
    </myLocalName3>
</root >
```

下面的 JSON 片段是它映射到的内容。

`{"myLocalName1":"myValue1","myLocalName2":2,"myLocalName3":{"myNestedName1":true,"myNestedName2":null}}`

> [!NOTE]
> 在前面的映射中没有 XML 编码步骤。 因此，WCF 仅支持 JSON 文档，其中键名称中的所有字符都是 XML 元素名称中的有效字符。 例如，JSON 文档 {"<":"a"} 不支持，因为 < 不是有效的 XML 元素名称。

相反的情况（字符在 XML 中有效而在 JSON 中无效）不会导致任何问题，因为上述映射包括 JSON 转义/取消转义步骤。

数组记录的工作原理如下：

- 内部元素的 [本地名称] 是“item”。

- 按照 JSON 类型属性，内部元素的 [子级] 映射到第 2.3 节中的值，Root JSON 元素也是这样。 允许 EII 的多级嵌套（包括对象内的嵌套）。

示例:下面的元素映射到 JSON 片段。

```xml
<root type="array"/>
    <item type="string">myValue1</item>
    <item type="number">2</item>
    <item type="array">
    <item type="boolean">true</item>
    <item type="null"/></item>
</root >
```

下面是 JSON 片段。

`["myValue1",2,[true,null]]`

## <a name="see-also"></a>请参阅

- <xref:System.Runtime.Serialization.Json.JsonReaderWriterFactory>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>
- [独立 JSON 序列化](stand-alone-json-serialization.md)
