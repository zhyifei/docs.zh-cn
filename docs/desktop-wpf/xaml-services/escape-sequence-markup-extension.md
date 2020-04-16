---
title: '{}转义序列 - 标记扩展'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432964"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="d36dc-102">{}转义序列/标记扩展</span><span class="sxs-lookup"><span data-stu-id="d36dc-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="d36dc-103">为属性值提供 XAML 转义序列。</span><span class="sxs-lookup"><span data-stu-id="d36dc-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="d36dc-104">转义序列允许将属性中的后续值解释为文本。</span><span class="sxs-lookup"><span data-stu-id="d36dc-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="d36dc-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="d36dc-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="d36dc-106">XAML 属性元素用法</span><span class="sxs-lookup"><span data-stu-id="d36dc-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="d36dc-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="d36dc-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="d36dc-108">*字面值*</span><span class="sxs-lookup"><span data-stu-id="d36dc-108">*literalValue*</span></span>|<span data-ttu-id="d36dc-109">转义序列后面的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="d36dc-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="d36dc-110">通常，此字符串包含打开或关闭大括号 （\* 或 |）。</span><span class="sxs-lookup"><span data-stu-id="d36dc-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="d36dc-111">备注</span><span class="sxs-lookup"><span data-stu-id="d36dc-111">Remarks</span></span>

<span data-ttu-id="d36dc-112">转义序列{}（ ） 用于使打开大括号 （\*） 可用作 XAML 中的字面字符。</span><span class="sxs-lookup"><span data-stu-id="d36dc-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="d36dc-113">XAML 读取器通常使用开放大括号 （*） 来表示标记扩展的入口点;但是，他们首先检查下一个字符以确定它是否是右大括号 （*）。</span><span class="sxs-lookup"><span data-stu-id="d36dc-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="d36dc-114">只有当两个大括号 （{}） 相邻时， 它们才被视为转义序列.</span><span class="sxs-lookup"><span data-stu-id="d36dc-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="d36dc-115">如果遇到转义序列，XAML 读取器应作为字符串处理字符串的其余部分。</span><span class="sxs-lookup"><span data-stu-id="d36dc-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="d36dc-116">但是，如果转义序列应用于具有类型转换器的成员，则当 XAML 编写器解释该字符串时，该字符串可能会进行类型转换。</span><span class="sxs-lookup"><span data-stu-id="d36dc-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="d36dc-117">转义序列不是标记扩展，并且不由类支持。</span><span class="sxs-lookup"><span data-stu-id="d36dc-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="d36dc-118">但是，XAML 读取器（包括自定义 XAML 读取器）应遵守的约定。</span><span class="sxs-lookup"><span data-stu-id="d36dc-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="d36dc-119">引号 （"） 不能以这种方式用作转义序列。</span><span class="sxs-lookup"><span data-stu-id="d36dc-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="d36dc-120">如果需要将引号设置为非内容属性的属性值，请使用属性元素语法并将引号作为字符串放在属性元素中，或使用 XML 字符实体。</span><span class="sxs-lookup"><span data-stu-id="d36dc-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="d36dc-121">对于内容属性，引号可以是整个内容。</span><span class="sxs-lookup"><span data-stu-id="d36dc-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="d36dc-122">指定必须包含命名{}空间限定符的位置的 XML 类型时，经常需要转义序列 （ ） 。</span><span class="sxs-lookup"><span data-stu-id="d36dc-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="d36dc-123">此位置包括 XAML 属性值的开头，以及等于符号 （\*） 之后的标记扩展中。</span><span class="sxs-lookup"><span data-stu-id="d36dc-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="d36dc-124">下面的示例显示出现在 XAML 属性值开头的 XML 命名空间的转义序列。</span><span class="sxs-lookup"><span data-stu-id="d36dc-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="d36dc-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="d36dc-125">See also</span></span>

- [<span data-ttu-id="d36dc-126">XAML 的类型转换器和标记扩展</span><span class="sxs-lookup"><span data-stu-id="d36dc-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="d36dc-127">XML 字符实体和 XAML</span><span class="sxs-lookup"><span data-stu-id="d36dc-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
