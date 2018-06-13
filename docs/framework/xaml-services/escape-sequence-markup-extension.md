---
title: '{} 转义序列的标记扩展'
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
ms.openlocfilehash: a90f6928d68eddd29762e6206769dd7f07704e4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564516"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="a0b80-102">{} 转义序列 / 标记扩展</span><span class="sxs-lookup"><span data-stu-id="a0b80-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="a0b80-103">为属性值提供 XAML 转义序列。</span><span class="sxs-lookup"><span data-stu-id="a0b80-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="a0b80-104">转义序列被解释为文本的属性中允许的后续值。</span><span class="sxs-lookup"><span data-stu-id="a0b80-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a0b80-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="a0b80-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="a0b80-106">XAML 属性元素用法</span><span class="sxs-lookup"><span data-stu-id="a0b80-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a0b80-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="a0b80-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0b80-108">*LiteralValue*</span><span class="sxs-lookup"><span data-stu-id="a0b80-108">*literalValue*</span></span>|<span data-ttu-id="a0b80-109">后面的转义序列的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="a0b80-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="a0b80-110">此字符串通常包含一个打开或关闭的大括号 （{或}）。</span><span class="sxs-lookup"><span data-stu-id="a0b80-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0b80-111">备注</span><span class="sxs-lookup"><span data-stu-id="a0b80-111">Remarks</span></span>  
 <span data-ttu-id="a0b80-112">转义序列 ({}) 以便左大括号 （{}） 可用作原义字符在 XAML 中使用。</span><span class="sxs-lookup"><span data-stu-id="a0b80-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="a0b80-113">XAML 读取器通常使用左大括号 （{}） 来表示标记扩展的入口点; 但是，他们首先检查以确定它是否是右大括号 （}） 的下一个字符。</span><span class="sxs-lookup"><span data-stu-id="a0b80-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="a0b80-114">仅当两个大括号 ({}) 相邻，它们被视为的转义序列。</span><span class="sxs-lookup"><span data-stu-id="a0b80-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="a0b80-115">如果遇到此转义序列，XAML 读取器应处理以字符串形式的字符串的其余部分。</span><span class="sxs-lookup"><span data-stu-id="a0b80-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="a0b80-116">但是，如果转义序列应用于类型转换器的成员，该字符串会被类型转换，以解释 XAML 编写器。</span><span class="sxs-lookup"><span data-stu-id="a0b80-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="a0b80-117">转义序列不是一个标记扩展，并不由类。</span><span class="sxs-lookup"><span data-stu-id="a0b80-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="a0b80-118">但是，它是 XAML 读取器 （包括自定义 XAML 读取器） 应遵循的约定。</span><span class="sxs-lookup"><span data-stu-id="a0b80-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="a0b80-119">引号 （"） 不能用作这种方式的转义序列。</span><span class="sxs-lookup"><span data-stu-id="a0b80-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="a0b80-120">如果你需要设置为非内容属性的属性值的引号，使用属性元素语法和将引号内的属性元素中，字符串形式或使用 XML 字符实体。</span><span class="sxs-lookup"><span data-stu-id="a0b80-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="a0b80-121">对于内容的属性，在引号可以是整个内容。</span><span class="sxs-lookup"><span data-stu-id="a0b80-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="a0b80-122">转义序列 ({}) 时，经常需要指定必须在 XAML 标记扩展可能出现的位置包括命名空间限定符的 XML 类型。</span><span class="sxs-lookup"><span data-stu-id="a0b80-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="a0b80-123">这包括启动的 XAML 特性值，并在标记扩展中，紧跟着等号 （=）。</span><span class="sxs-lookup"><span data-stu-id="a0b80-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="a0b80-124">下面的示例演示了 XAML 特性值的开头处显示的 XML 命名空间的转义序列。</span><span class="sxs-lookup"><span data-stu-id="a0b80-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="a0b80-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0b80-125">See Also</span></span>  
 [<span data-ttu-id="a0b80-126">XAML 的类型转换器和标记扩展</span><span class="sxs-lookup"><span data-stu-id="a0b80-126">Type Converters and Markup Extensions for XAML</span></span>](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [<span data-ttu-id="a0b80-127">XML 字符实体和 XAML</span><span class="sxs-lookup"><span data-stu-id="a0b80-127">XML Character Entities and XAML</span></span>](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
