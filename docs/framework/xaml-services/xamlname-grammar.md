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
ms.openlocfilehash: a39d25f03583ab9020878b7a659bc99489231ff9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458884"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="5b435-102">XamlName 语法</span><span class="sxs-lookup"><span data-stu-id="5b435-102">XamlName Grammar</span></span>
<span data-ttu-id="5b435-103">XamlName 语法是在 XAML 语言规范 [MS-CHAP] 中定义的一种特定语法，此处将在此处重现此语法。</span><span class="sxs-lookup"><span data-stu-id="5b435-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>  
  
## <a name="from-the-xaml-specification"></a><span data-ttu-id="5b435-104">从 XAML 规范</span><span class="sxs-lookup"><span data-stu-id="5b435-104">From the XAML Specification</span></span>  
 <span data-ttu-id="5b435-105">[MS-CHAP] 规范定义语法 XamlName，用于标识用于类型和属性的合法符号标识符集。</span><span class="sxs-lookup"><span data-stu-id="5b435-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>  
  
 <span data-ttu-id="5b435-106">XamlName 类型的字符串值必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="5b435-106">String values that are of type XamlName must conform to the following grammar:</span></span>  
  
```xaml  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
```  
  
 <span data-ttu-id="5b435-107">它假定 Unicode 字符数据库中定义的以下常规类别值</span><span class="sxs-lookup"><span data-stu-id="5b435-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>  

| <span data-ttu-id="5b435-108">Unicode 类别</span><span class="sxs-lookup"><span data-stu-id="5b435-108">Unicode category</span></span>   | <span data-ttu-id="5b435-109">描述</span><span class="sxs-lookup"><span data-stu-id="5b435-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="5b435-110">Lu</span><span class="sxs-lookup"><span data-stu-id="5b435-110">Lu</span></span>                 | <span data-ttu-id="5b435-111">字母，大写</span><span class="sxs-lookup"><span data-stu-id="5b435-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="5b435-112">Ll</span><span class="sxs-lookup"><span data-stu-id="5b435-112">Ll</span></span>                 | <span data-ttu-id="5b435-113">字母，小写</span><span class="sxs-lookup"><span data-stu-id="5b435-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="5b435-114">Lt</span><span class="sxs-lookup"><span data-stu-id="5b435-114">Lt</span></span>                 | <span data-ttu-id="5b435-115">字母，首字母大写</span><span class="sxs-lookup"><span data-stu-id="5b435-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="5b435-116">Lm</span><span class="sxs-lookup"><span data-stu-id="5b435-116">Lm</span></span>                 | <span data-ttu-id="5b435-117">字母，修饰符</span><span class="sxs-lookup"><span data-stu-id="5b435-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="5b435-118">Lo</span><span class="sxs-lookup"><span data-stu-id="5b435-118">Lo</span></span>                 | <span data-ttu-id="5b435-119">字母，其他</span><span class="sxs-lookup"><span data-stu-id="5b435-119">Letter, Other</span></span>                 |
| <span data-ttu-id="5b435-120">Mn</span><span class="sxs-lookup"><span data-stu-id="5b435-120">Mn</span></span>                 | <span data-ttu-id="5b435-121">标记，非间距</span><span class="sxs-lookup"><span data-stu-id="5b435-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="5b435-122">Mc</span><span class="sxs-lookup"><span data-stu-id="5b435-122">Mc</span></span>                 | <span data-ttu-id="5b435-123">标记，间距组合</span><span class="sxs-lookup"><span data-stu-id="5b435-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="5b435-124">Nd</span><span class="sxs-lookup"><span data-stu-id="5b435-124">Nd</span></span>                 | <span data-ttu-id="5b435-125">Number、Decimal</span><span class="sxs-lookup"><span data-stu-id="5b435-125">Number, Decimal</span></span>               |
| <span data-ttu-id="5b435-126">Nl</span><span class="sxs-lookup"><span data-stu-id="5b435-126">Nl</span></span>                 | <span data-ttu-id="5b435-127">数字，字母</span><span class="sxs-lookup"><span data-stu-id="5b435-127">Number, Letter</span></span>                |
 
 <span data-ttu-id="5b435-128">XAML 定义了第二个语法 DottedXamlName，用于属性和事件限定引用，还用于附加成员。</span><span class="sxs-lookup"><span data-stu-id="5b435-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="5b435-129">有关详细信息，请参阅 <xref:System.Windows.DependencyProperty> 和[XAML 概述（WPF）](../../desktop-wpf/fundamentals/xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="5b435-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../../desktop-wpf/fundamentals/xaml.md).</span></span>  
  
 <span data-ttu-id="5b435-130">DottedXamlName 类型的字符串值必须符合以下语法：</span><span class="sxs-lookup"><span data-stu-id="5b435-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>  
  
```xaml  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## <a name="remarks"></a><span data-ttu-id="5b435-131">备注</span><span class="sxs-lookup"><span data-stu-id="5b435-131">Remarks</span></span>  
 <span data-ttu-id="5b435-132">有关完整规范，请参阅[\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525)。</span><span class="sxs-lookup"><span data-stu-id="5b435-132">For the complete specification, see [\[MS-XAML\]](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>
