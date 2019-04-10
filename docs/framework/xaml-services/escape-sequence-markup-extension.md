---
title: '{} 转义序列-标记扩展'
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
ms.openlocfilehash: 9f6743dd8a82891ac2233978550e5679130de0be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182061"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="bd215-102">{} 转义序列/标记扩展</span><span class="sxs-lookup"><span data-stu-id="bd215-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="bd215-103">为属性值提供 XAML 转义序列。</span><span class="sxs-lookup"><span data-stu-id="bd215-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="bd215-104">转义序列允许后续值中的属性将被解释为文本。</span><span class="sxs-lookup"><span data-stu-id="bd215-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="bd215-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="bd215-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="bd215-106">XAML 属性元素用法</span><span class="sxs-lookup"><span data-stu-id="bd215-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="bd215-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="bd215-107">XAML Values</span></span>  
  
|||  
|-|-|  
|*<span data-ttu-id="bd215-108">literalValue</span><span class="sxs-lookup"><span data-stu-id="bd215-108">literalValue</span></span>*|<span data-ttu-id="bd215-109">后面的转义序列的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="bd215-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="bd215-110">此字符串通常包含一个打开或关闭的大括号 （{或}）。</span><span class="sxs-lookup"><span data-stu-id="bd215-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd215-111">备注</span><span class="sxs-lookup"><span data-stu-id="bd215-111">Remarks</span></span>  
 <span data-ttu-id="bd215-112">转义序列 ({}) 使用，以便可以作为 XAML 中的文字字符使用左大括号 （{}）。</span><span class="sxs-lookup"><span data-stu-id="bd215-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="bd215-113">XAML 读取器通常使用左大括号 （{}） 来表示标记扩展的入口点; 但是，它们首先检查以确定它是否是右大括号 （}） 的下一个字符。</span><span class="sxs-lookup"><span data-stu-id="bd215-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="bd215-114">仅当两个大括号 ({}) 相邻情况是它们被视为一个转义序列。</span><span class="sxs-lookup"><span data-stu-id="bd215-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="bd215-115">如果遇到转义序列时，XAML 读取器应作为字符串处理字符串的其余部分。</span><span class="sxs-lookup"><span data-stu-id="bd215-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="bd215-116">但是，如果转义序列应用于成员具有的类型转换器，该字符串会被类型转换时解释由 XAML 编写器。</span><span class="sxs-lookup"><span data-stu-id="bd215-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="bd215-117">转义序列不是标记扩展，且不支持由类。</span><span class="sxs-lookup"><span data-stu-id="bd215-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="bd215-118">但是，它是 XAML 读取器 （包括自定义 XAML 读取器） 应遵循的约定。</span><span class="sxs-lookup"><span data-stu-id="bd215-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="bd215-119">引号 （"） 不能用作转义序列以这种方式。</span><span class="sxs-lookup"><span data-stu-id="bd215-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="bd215-120">如果您需要将英文引号连用设置为非内容属性的属性值，使用属性元素语法和属性元素内的字符串将引号或使用 XML 字符实体。</span><span class="sxs-lookup"><span data-stu-id="bd215-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="bd215-121">内容属性，英文引号连用可以是整个内容。</span><span class="sxs-lookup"><span data-stu-id="bd215-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="bd215-122">转义序列 ({}) 时，经常需要指定在 XAML 标记扩展可能出现的位置中必须包含命名空间限定符的 XML 类型。</span><span class="sxs-lookup"><span data-stu-id="bd215-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="bd215-123">这包括开始的 XAML 属性值和在标记扩展中，紧等号 （=）。</span><span class="sxs-lookup"><span data-stu-id="bd215-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="bd215-124">下面的示例显示了 XAML 特性值的开头处显示的 XML 命名空间的转义序列。</span><span class="sxs-lookup"><span data-stu-id="bd215-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="bd215-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd215-125">See also</span></span>

- [<span data-ttu-id="bd215-126">XAML 的类型转换器和标记扩展</span><span class="sxs-lookup"><span data-stu-id="bd215-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions-for-xaml.md)
- [<span data-ttu-id="bd215-127">XML 字符实体和 XAML</span><span class="sxs-lookup"><span data-stu-id="bd215-127">XML Character Entities and XAML</span></span>](xml-character-entities-and-xaml.md)
