---
title: XAML 中 xml:lang 的处理
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b5a06adbb7cb874bc09899118f13b91fbec7a85e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432706"
---
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="37ab6-102">XAML 中 xml:lang 的处理</span><span class="sxs-lookup"><span data-stu-id="37ab6-102">xml:lang Handling in XAML</span></span>

<span data-ttu-id="37ab6-103">该`xml:lang`属性是一个 XML 定义的属性，用于声明 XML 中元素的语言和文化信息。</span><span class="sxs-lookup"><span data-stu-id="37ab6-103">The `xml:lang` attribute is an XML-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="37ab6-104">此属性的相同含义在 XAML 中持续存在；但有一些其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="37ab6-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="37ab6-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="37ab6-105">XAML Attribute Usage</span></span>

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a><span data-ttu-id="37ab6-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="37ab6-106">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="37ab6-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="37ab6-107">*rfc3066lang*</span></span>|<span data-ttu-id="37ab6-108">派生自 [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) 标准的字符串，并标识一种语言或语言-地区。</span><span class="sxs-lookup"><span data-stu-id="37ab6-108">A string that is derived from the [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="37ab6-109">当为后者时，将由一个连字符分隔语言和区域。</span><span class="sxs-lookup"><span data-stu-id="37ab6-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="37ab6-110">请参阅 <xref:System.Windows.Markup.XmlLanguage> ，以了解有关值和格式的更多信息。</span><span class="sxs-lookup"><span data-stu-id="37ab6-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|

## <a name="remarks"></a><span data-ttu-id="37ab6-111">备注</span><span class="sxs-lookup"><span data-stu-id="37ab6-111">Remarks</span></span>

<span data-ttu-id="37ab6-112">中`xml:lang`[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]的属性的定义派生自`xml:lang`万维网联盟 （W3C） 对 XML 的定义。</span><span class="sxs-lookup"><span data-stu-id="37ab6-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the World Wide Web Consortium (W3C) for XML.</span></span> <span data-ttu-id="37ab6-113">语言和区域性信息可能由元素根据其实现以不同方式进行处理；但是， [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 属性没有默认的 `xml:lang` 处理方式。</span><span class="sxs-lookup"><span data-stu-id="37ab6-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>

<span data-ttu-id="37ab6-114">`xml:lang` 属性的默认值是属性级空字符串。</span><span class="sxs-lookup"><span data-stu-id="37ab6-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>

<span data-ttu-id="37ab6-115">当由作用于 `xml:lang` 值的系统进行解释时， `xml:lang` 属性效果和属性值通常永久保留到子元素中。</span><span class="sxs-lookup"><span data-stu-id="37ab6-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>

<span data-ttu-id="37ab6-116">当由 .NET XAML 服务的 XAML`xml:lang`编写器解释<xref:System.Windows.Markup.XmlLanguage>时<xref:System.Globalization.CultureInfo>，值可以在基础对象表示形式中创建或对象;但是，该行为取决于为其`xml:lang`指定的值是否为这些类的有效构造。</span><span class="sxs-lookup"><span data-stu-id="37ab6-116">When interpreted by XAML writers of .NET XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>

<span data-ttu-id="37ab6-117">通过将 `xml:lang` 应用到属性，框架可以在 XML 中创建框架定义属性和 <xref:System.Windows.Markup.XmlLangPropertyAttribute> 含义之间的关联。</span><span class="sxs-lookup"><span data-stu-id="37ab6-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>

## <a name="wpf-usage-nodes"></a><span data-ttu-id="37ab6-118">WPF 使用情况节点</span><span class="sxs-lookup"><span data-stu-id="37ab6-118">WPF Usage Nodes</span></span>

<span data-ttu-id="37ab6-119">对于身为 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement>派生类的元素，可以使用等效 <xref:System.Windows.FrameworkElement.Language%2A> 依赖项属性取代 `xml:lang` 属性。</span><span class="sxs-lookup"><span data-stu-id="37ab6-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="37ab6-120">默认情况下，如果未通过属性或通过处理 <xref:System.Windows.FrameworkElement.Language%2A> 属性来另外设置 `xml:lang` 属性，则它使用“en-US”。</span><span class="sxs-lookup"><span data-stu-id="37ab6-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="37ab6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="37ab6-121">See also</span></span>

- [<span data-ttu-id="37ab6-122">WPF 的全球化</span><span class="sxs-lookup"><span data-stu-id="37ab6-122">Globalization for WPF</span></span>](../../framework/wpf/advanced/globalization-for-wpf.md)
