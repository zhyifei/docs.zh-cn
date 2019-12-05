---
title: XamlName 语法
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: a1e7a5a03db4a24ed4d13d62899754cfe9e76b56
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837150"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="f129f-102">XamlName 语法</span><span class="sxs-lookup"><span data-stu-id="f129f-102">XamlName Grammar</span></span>
<span data-ttu-id="f129f-103">XamlName 语法是在 XAML 语言规范 [MS-CHAP] 中定义的一种特定语法，此处将在此处重现此语法。</span><span class="sxs-lookup"><span data-stu-id="f129f-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="f129f-104">从 XAML 规范</span><span class="sxs-lookup"><span data-stu-id="f129f-104">From the XAML Specification</span></span>  
 <span data-ttu-id="f129f-105">[MS-CHAP] 规范定义语法 XamlName，用于标识用于类型和属性的合法符号标识符集。</span><span class="sxs-lookup"><span data-stu-id="f129f-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="f129f-106">XamlName 类型的字符串值必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="f129f-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="f129f-107">它假定 Unicode 字符数据库中定义的以下常规类别值</span><span class="sxs-lookup"><span data-stu-id="f129f-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  

| <span data-ttu-id="f129f-108">Unicode 类别</span><span class="sxs-lookup"><span data-stu-id="f129f-108">Unicode category</span></span>   | <span data-ttu-id="f129f-109">描述</span><span class="sxs-lookup"><span data-stu-id="f129f-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="f129f-110">Lu</span><span class="sxs-lookup"><span data-stu-id="f129f-110">Lu</span></span>                 | <span data-ttu-id="f129f-111">字母，大写</span><span class="sxs-lookup"><span data-stu-id="f129f-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="f129f-112">Ll</span><span class="sxs-lookup"><span data-stu-id="f129f-112">Ll</span></span>                 | <span data-ttu-id="f129f-113">字母，小写</span><span class="sxs-lookup"><span data-stu-id="f129f-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="f129f-114">Lt</span><span class="sxs-lookup"><span data-stu-id="f129f-114">Lt</span></span>                 | <span data-ttu-id="f129f-115">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="f129f-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="f129f-116">Lm</span><span class="sxs-lookup"><span data-stu-id="f129f-116">Lm</span></span>                 | <span data-ttu-id="f129f-117">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="f129f-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="f129f-118">Lo</span><span class="sxs-lookup"><span data-stu-id="f129f-118">Lo</span></span>                 | <span data-ttu-id="f129f-119">字母，其他</span><span class="sxs-lookup"><span data-stu-id="f129f-119">Letter, Other</span></span>                 |
| <span data-ttu-id="f129f-120">Mn</span><span class="sxs-lookup"><span data-stu-id="f129f-120">Mn</span></span>                 | <span data-ttu-id="f129f-121">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="f129f-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="f129f-122">Mc</span><span class="sxs-lookup"><span data-stu-id="f129f-122">Mc</span></span>                 | <span data-ttu-id="f129f-123">标记，间距组合</span><span class="sxs-lookup"><span data-stu-id="f129f-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="f129f-124">Nd</span><span class="sxs-lookup"><span data-stu-id="f129f-124">Nd</span></span>                 | <span data-ttu-id="f129f-125">Number、Decimal</span><span class="sxs-lookup"><span data-stu-id="f129f-125">Number, Decimal</span></span>               |
| <span data-ttu-id="f129f-126">Nl</span><span class="sxs-lookup"><span data-stu-id="f129f-126">Nl</span></span>                 | <span data-ttu-id="f129f-127">数字，字母</span><span class="sxs-lookup"><span data-stu-id="f129f-127">Number, Letter</span></span>                |
 
 <span data-ttu-id="f129f-128">XAML 定义了第二个语法 DottedXamlName，用于属性和事件限定引用，还用于附加成员。</span><span class="sxs-lookup"><span data-stu-id="f129f-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="f129f-129">有关详细信息，请参阅 <xref:System.Windows.DependencyProperty> 和[XAML 概述（WPF）](../../desktop-wpf/fundamentals/xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="f129f-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
 <span data-ttu-id="f129f-130">DottedXamlName 类型的字符串值必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="f129f-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="f129f-131">备注</span><span class="sxs-lookup"><span data-stu-id="f129f-131">Remarks</span></span>  
 <span data-ttu-id="f129f-132">有关完整规范，请参阅[\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))。</span><span class="sxs-lookup"><span data-stu-id="f129f-132">For the complete specification, see [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
